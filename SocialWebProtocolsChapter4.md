[목차로 돌아가기](SocialWebProtocolsContents.md)

## 4. Publishing

Publishing in this context refers to modifying the outgoing feed associated with a particular profile. This incorporates creating new content, as well as updating or deleting existing content. Content generated through a client (such as a web form, mobile app, sensor, smart device) is created when it is sent to a server for processing, where it is typically stored and usually published (either publicly or to a restricted audience), in human- and/or machine-readable forms. Clients and servers may independently support creating, updating and deleting; there are no dependencies between them.

>Note: Other kinds of publishing
>
>While delivering notifications or responding to subscription requests may trigger creating (or updating or deleting) something on the receiving end, the intent is different. These cases are called out as side effects in subscription and delivery where appropriate.

For notes about authentication and authorization between clients and servers, see [7.2 Authentication, authorization, and access control](https://www.w3.org/TR/social-web-protocols/#auth)

The two specifications recommended by the Social Web Working Group for publishing are [[Activitypub](https://www.w3.org/TR/social-web-protocols/#bib-Activitypub)] and [[Micropub](https://www.w3.org/TR/social-web-protocols/#bib-Micropub)]. They use similar high level mechanisms, but differ in requirements around both the vocabularies and content types of data.

ActivityPub contains a client-to-server API for creating ActivityStreams 2.0 objects and activities, and specifies additional responsibilities for clients around addressing objects, and for servers around the side-effects of certain types of objects.

Micropub provides a basic client-to-server API for creating blog-post-type content and is intended as a quickstart for content creation, on top of which more complex (but optional) actions can be layered. Micropub also provides a media endpoint for uploading files.

>Note: REST
>
>Neither ActivityPub nor Micropub define APIs for publishing based on HTTP verbs. If you're looking for something more RESTful, you may like the Linked Data Platform [[LDP](https://www.w3.org/TR/social-web-protocols/#bib-LDP)].

### 4.1 Creating

The publishing endpoint of **[[Activitypub](https://www.w3.org/TR/social-web-protocols/#bib-Activitypub)]** is the `outbox`. Clients are assumed to have the URL of a (ideally authenticated) profile as a starting point, and discover the value of the `https://www.w3.org/ns/activitystreams#outbox` property found at the profile URL (which should be available as JSON). The client then makes an HTTP POST request with an ActivityStreams 2.0 activity or object as a JSON payload with a content type of `application/ld+json; profile="https://www.w3.org/ns/activitystreams"`. The URL of the created resource is generated at the discretion of the server, and returned in the `Location` HTTP header. This is an appropriate protocol to use when:

- You want to send/receive a JSON or JSON-LD payload.
- Your data is described with [[activitystreams-core](https://www.w3.org/TR/social-web-protocols/#bib-activitystreams-core)] and [[activitystreams-vocabulary](https://www.w3.org/TR/social-web-protocols/#bib-activitystreams-vocabulary)] (optionally extensible via JSON-LD).
- You want servers to carry out a known set of actions upon content creation.

Side-effects of creating content with ActivityPub are for the most part adding things to various different collections collections (likes, follows, etc); but also include requirements about blocking users, and a hook to enable federated servers.

The publishing endpoint for **[[Micropub](https://www.w3.org/TR/social-web-protocols/#bib-Micropub)]** is the `micropub` endpoint. Clients discover this from a profile URL via a `rel="micropub"` link (in an HTTP `Link` header, or an HTML `<link>` element). Clients make a `x-www-form-urlencoded` POST request containing the key-value pairs for the attributes of the object being created. The URL of the created resource is generated at the discretion of the server, and returned in the `Location` HTTP header. Clients and servers must support attributes from the Microformats2 [[h-entry](https://www.w3.org/TR/social-web-protocols/#bib-h-entry)] vocabulary. Micropub also defines four reserved attributes (`access_token`, h, `action` and `url`) as well as reserves any attribute prefixed with `mp-`; these are used as commands to the server. Any additional key names sent outside of these vocabularies may be ignored by the server.

Micropub requests may alternatively be sent as a JSON payload, the syntax of which is derived from [[microformats2-parsing](https://www.w3.org/TR/social-web-protocols/#bib-microformats2-parsing)].

This is an appropriate protocol to use when:

- You want to send/receive a form-encoded or JSON payload.
- Your data is described with the [[h-entry](https://www.w3.org/TR/social-web-protocols/#bib-h-entry)] syntax and vocabulary.
- You can rely on out-of-band agreements between clients and servers for vocabulary extensibility.

### 4.2 Updating

Content is updated when a client sends changes to attributes (additions, removals, replacements) to an existing object.

**[[Activitypub](https://www.w3.org/TR/social-web-protocols/#bib-Activitypub)]** clients send an HTTP `POST` request to the `outbox` containing an ActivityStreams 2.0 `Update` activity. The `object` of the activity is an existing object, including its `id`, and the fields to update should be nested. If a partial representation of an object is sent, omitted fields are _not_ deleted by the server. In order to delete specific fields, the client can assign them a `null` value.

In the case of ActivityPub federated servers, updates should be propagated to the `inbox`es of recipients of the original objects. However, when a federated server passes an `Update` activity to another server's `inbox`, the recipient must assume this is the complete object to be replaced; partial updates are not performed server-to-server.

An `Undo` with the `object` of the previous `Update` can be used to revert changes.

**[[Micropub](https://www.w3.org/TR/social-web-protocols/#bib-Micropub)]** clients perform updates as JSON POST requests, using the `"action": "update"` directive, as well as a `replace`, `add` or `delete` property containing the updates to make, to the Micropub endpoint. `replace` replaces all values of the specified property; if the property does not exist already, it is created. `add` adds new values to the specified property without changing the existing ones; if the property does not exist already, it is created. `delete` removes the specified property; you can also remove properties by value by specifying the value.

If a server also implements [[Webmention](https://www.w3.org/TR/social-web-protocols/#bib-Webmention)] it should propagate the updates to anyone who received Webmentions for the original.

If a server also implements [[WebSub](https://www.w3.org/TR/social-web-protocols/#bib-WebSub)], and the updated resource is part of a `topic`, the server should notify the hub of an update to the topic URL.

### 4.3 Deleting

Content is deleted when a client sends a request to delete an existing object.

**[[Activitypub](https://www.w3.org/TR/social-web-protocols/#bib-Activitypub)]** clients delete an object by sending an HTTP POST request containing an ActivityStreams 2.0 `Delete` activity to the `outbox` of the authenticated user. Servers must either _replace_ the `object` of this activity with a tombstone and return a `410 Gone` status code, or return a `404 Not Found`, from its URL.

An `Undo` with the `object` of the previous `Delete` may be used to restore the object.

**[[Micropub](https://www.w3.org/TR/social-web-protocols/#bib-Micropub)]** delete requests are two key-value pairs, JSON: `"action": "delete"` and `"url": url-to-be-deleted`, sent to the Micropub endpoint. Posts may be resotred with `"action": "undelete"`.

As with [updating](https://www.w3.org/TR/social-web-protocols/#updating), servers implementing ActivityPub federation, Webmention or WebSub should propagate deletes accordingly.