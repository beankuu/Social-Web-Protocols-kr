[목차로 돌아가기](SocialWebProtocolsContents.md)

## 6. Delivery

A user or application may wish to push a notification to another user that the receiver has not explicitly asked for. For example to send a message or some new information; because they have linked to (replied, liked, bookmarked, reposted, etc) their content; because they have linked to (tagged, addressed) the user directly; to make the recipient aware of a change in state of some document or resource on the Web. The Social Web Working Group specifications contain several mechanisms for carrying out delivery; they are listed here from general to specialised.

>Note: Delivery vs subscription
>
>We need to leave it open for users to refuse content they have not explicitly [subscribed](https://www.w3.org/TR/social-web-protocols/#subscribing) to, ie. nothing else should rely on implementation of delivery.

### 6.1 Targeting and discovery

The target of a notification is usually the addressee or the subject, as referenced by a URL. The target may also a resource which has previously requested notifications through a [subscription](https://www.w3.org/TR/social-web-protocols/#subscribing) request. Once you have determined your target, you need to discover where to send the notification for that particular target. Discovery is fetching the target URL and looking for a link to an endpoint which will accept the type of notification you want to send (read on, for all of your exciting options).

Bear in mind that many potential targets will not be configured to receive notifications at all. To avoid overloading unsuspecting servers with discovery-related requests, your application should employ a "back-off" strategy when carrying out discovery multiple times to targets on the same domin. This could involve increasing the period of time between subsequent requests, or caching unsuccessful discovery attempts so those domains can be avoided in future. You may wish to send a `User-Agent` header with a reference to the notification mechanism you are using so that recipient servers can find out more about the purpose of your requests.

Your application should also respect relevant cache control and retry headers returned by the target server.

### 6.2 Generic notifications

**[[LDN](https://www.w3.org/TR/social-web-protocols/#bib-LDN)]** is a federation protocol for sending, receiving and consuming notifications which may contain any content, and be triggered by any person or process. Senders, receivers and consumers can all be on different domains. This is a suitable notification mechanism when:

- Notifications need to be identifiable with their own URLs and exposed by the receiver for other applications to discover and re-use.
- Notifications are represented as a JSON-LD payload (ie. a 'fat ping').
- You need to advertise constraints on the type or contents of notifications accepted by a receiver.

[[LDN](https://www.w3.org/TR/social-web-protocols/#bib-LDN)] functionality is divided between senders, receivers and consumers. The endpoint to which notifications are sent is the `inbox`. Any resource (a user profile, blog post, document) can advertise its `inbox` so that it may be discovered through an HTTP `Link` header or the document body in any RDF syntax (including JSON-LD or HTML+RDFa). To this Inbox, senders make a `POST` request containing the JSON-LD (or other RDF syntax per [[Accept-Post](https://www.w3.org/TR/social-web-protocols/#bib-Accept-Post)] negotation with the receiver) payload of the notification. The receiver returns a URL from which the notification data can be retrieved, and also adds this URL to a list which is returned upon a `GET` request to the Inbox (see [3. Reading](https://www.w3.org/TR/social-web-protocols/#reading)). Consumers can retrieve this Inbox listing, and from there the individual notifications, as JSON-LD (optionally content negotiated to another RDF syntax). An obvious type of consumer is a script which displays notifications in a human-readable way.

>Note: LDP compatibility
>
>An existing [[LDP](https://www.w3.org/TR/social-web-protocols/#bib-LDP)] implementation can serve as an [[LDN](https://www.w3.org/TR/social-web-protocols/#bib-LDN)] receiver out of the box; publishers simply advertise any `ldp:Container` as the `inbox` for a resource.

The payload of notifications is deliberately left open so that LDN may be used in a wide variety of use cases. However, receivers with particular purposes are likely to want to constrain the types of notifications they accept. They can do this transparently (such that senders are able to attempt to conform, rather than having their requests rejected opaquely) by advertising data shapes constraints such as [[SHACL](https://www.w3.org/TR/social-web-protocols/#bib-SHACL)]. Advertisement of such constraints also allows consumers to understand the types of notifications in the Inbox before attempting to retrieve them. Receivers may reject notifications on the basis of internal, undisclosed constraints, and may also access control the Inbox for example by requiring an `Authorization` header from both senders and consumers.

[[WebSub](https://www.w3.org/TR/social-web-protocols/#bib-WebSub)] publishers deliver content to their hub, and hubs to their subscribers using HTTP `POST` requests. The body of the request is left to the discretion of the sender in the first case, and in the latter case must match the Content-Type of and contain contents from the `topic` URL.

### 6.3 Activity notifications

**[[Activitypub](https://www.w3.org/TR/social-web-protocols/#bib-Activitypub)]** uses [[LDN](https://www.w3.org/TR/social-web-protocols/#bib-LDN)] to send notifications with some specific constraints. These are:

- The notification payload *MUST* be a single ActivityStreams 2.0 Activity.
- The notification payload *MUST* be compact JSON-LD.
- The receiver *MUST* verify the notification by fetching its source from the origin server.
- All notification `POST` requests are authenticated.

[[Activitypub](https://www.w3.org/TR/social-web-protocols/#bib-Activitypub)] specifies how to define the target(s) to which a notification is to be sent (a pre-requisite to [[LDN](https://www.w3.org/TR/social-web-protocols/#bib-LDN)] sending), via the [[activitystreams-vocabulary](https://www.w3.org/TR/social-web-protocols/#bib-activitystreams-vocabulary)] audience targeting and object linking properties.

[[Activitypub](https://www.w3.org/TR/social-web-protocols/#bib-Activitypub)] also defines side-effects that must be carried out by the server as a result of notification receipt. These include:

- Creating, updating or deleting new objects upon receipt of `Create`, `Update` and `Delete` activities.
- Reversing the side-effects of prior activities upon receipt of the `Undo` activity.
- Updating specialised collections for `Follow`, `Like` and `Block` activities.
- Updating any other collections upon receipt of `Add` and `Remove` activities.
- Carrying out further delivery to propagate activities through the network in the case of federated servers.

>Note: The inbox property
>
>ActivityPub actor profiles are linked to their inboxes via the `https://www.w3.org/ns/activitystreams#inbox` property. This is an alias (in the AS2 JSON-LD context) for LDN's `http://www.w3.org/ns/ldp#inbox`. Applications using a full JSON-LD processor to parse these documents will see these terms as one and the same. Applications doing naive string matching on terms may wish to note that if you find an `ldp:inbox` it will accept `POST` requests in the same way as an `as:inbox`.

### 6.4 Mentioning

**[[Webmention](https://www.w3.org/TR/social-web-protocols/#bib-Webmention)]** provides an API for sending and receiving notifications when a relationship is created (or updated, or deleted) between two documents. A webmention sender is triggered by the creation (or modification) of content which includes the URL of another document. It works when the two documents are on different domains, thus serving as a federation protocol. This is a suitable notification mechanism when:

- You have a document (source) which contains the URL of another document (target).
- The owner of the endpoint has access to view the source (so the request can be verified).
- The only data you need to send over the wire are the URLs of the source and target documents (ie. a 'thin ping').

There are no constraints on the syntax of the source and target documents. Discovery of the [[Webmention](https://www.w3.org/TR/social-web-protocols/#bib-Webmention)] endpoint (a script which can process incoming webmentions) is through a link relation (`rel="webmention"`), either in the HTTP `Link` header or HTML body of the target. This endpoint does not need to be on the same domain as the target, so webmention receiving can be delegated to a third party.

Webmentions are verified by the server dereferencing the source and parsing it to check for the existence of the target URL. If the target URL isn't found, the webmention *MUST* be rejected.

Webmention uses `x-www-form-urlencoded` for the source and target as parameters in an HTTP POST request. Beyond verification, it is not specified what the receiver should do upon receipt of a Webmention. What the webmention endpoint should return on a `GET` request is also left unspecified.

#### 6.4.1 Updates and deletes

In practice, Webmention receivers tend to fetch and store the webmention source. It is often displayed, for example as a reply underneath the target blog post.

If a Webmention is received and this is the first time this `source` and `target` combination has been seen by the receiver, this indicates a relationship between the `source` and `target` has been created. If the receiver has seen these values before, the receiver can fetch and parse the `source` to determine what has changed; either the content of the `source` has been updated (in which case the receiver can update local copies of the content, if it stored them in the first place), or the entire source has been deleted (expect a `410 Gone` response).

### 6.5 Delivery interop

This section describes how implementations of Webmention, ActivityPub and LDN may create bridging code in order to send and receive notifications from the others.

#### 6.5.1 Webmention as AS2 / ActivityPub

A webmention may be represented as a persistent resource with the ActivityStreams 2.0 vocabulary. This could come in handy if a **Webmention sender** mentions a user known to be running an ActivityPub federated server, and wants a generic (ie. not ActivityPub specific) way of notifying about this. In this case, the sender can use an AS2 payload and deliver the notification per [6.5.3 Webmention to LDN](https://www.w3.org/TR/social-web-protocols/#wm-to-ldn).

>Example 1
>
>```json
>{
>  "@context": "https://www.w3.org/ns/activitystreams#",
>  "type": "Relationship",
>  "subject": "https://waterpigs.example/post-by-barnaby",
>  "object": "https://aaronpk.example/post-by-aaron"
>}
>```

A receiver or sender may want to augment this representation with the relationship between the two documents, and any other pertinent data. In the receiver's case, this could be gathered when they parse the source during the verification process. For example:

>Example 2
>
>```json
>{
>  "@context": "https://www.w3.org/ns/activitystreams#",
>  "type": "Relationship",
>  "subject": {
>- "id": "https://waterpigs.example/post-by-barnaby",
>- "name": "Hi Aaron, great post."
>  },
>  "object": {
>- "id": "https://aaronpk.example/post-by-aaron",
>- "name": "Aaron's first post."
>  },
>  "relationship": "inReplyTo"
>}
>```

#### 6.5.2 LDN to Webmention

**Webmention receivers** wishing to also accept LDN `POST`s at their Webmention endpoint must:

- Advertise the webmention endpoint via `rel="http://www.w3.org/ns/ldp#inbox"` in addition to `rel="webmention"` (in the `Link` header, HTML body or JSON body of a target).
- Accept `POST` requests with the Content-Type `application/ld+json`. Expect the body of the request to be:

    >Example 3
    >
    >```json
    >{
    >  "@context": "http://www.w3.org/ns/webmention#",
    >  "@id": "",
    >  "source": { "@id": "https://waterpigs.example/post-by-barnaby" },
    >  "target": { "@id": "https://aaronpk.example/post-by-aaron" }
    >}
    >```

- Use the `source->@id` and `target->@id` values as the `source` and `target` of the Webmention, and proceed with verification.
- If returning a `201 Created`, it *MUST* return a `Location` header with a URL from which the contents of the request posted can be retrieved. `202 Accepted` is still fine.
- Note than when verifying the source, there's a good chance you can request/parse it as RDF.

**LDN senders** wishing to send to Webmention endpoints basically just need to implement Webmention sending. The Webmention endpoint is at `rel="webmention"` (either in an HTTP `Link` header or HTML `<link>` element).

Note that Webmention endpoints will only verify a received notification if the `source` is publicly retrievable and contains the URL of the `target`.

#### 6.5.3 Webmention to LDN

**LDN receivers** wishing to also accept Webmentions to their Inbox *MUST*:

- Advertise the Inbox via `rel="webmention"` in addition to `rel="http://www.w3.org/ns/ldp#inbox"` (in the `Link` header, HTML body or JSON body of a target).
- Accept `POST` requests with a content type `application/x-www-form-urlencoded`. Convert these requests from:
    >Example 4
    >
    >```lang-none
    >source=https://waterpigs.example/post-by-barnaby&
    >target=https://aaronpk.example/post-by-aaron
    >```

    to:

    >Example 5
    >
    >```json
    >{
    >  "@context": "http://www.w3.org/ns/webmention#",
    >  "@id": "",
    >  "source": { "@id": "https://waterpigs.example/post-by-barnaby" },
    >  "target": { "@id": "https://aaronpk.example/post-by-aaron" }
    >}
    >```

- and proceed per [[LDN](https://www.w3.org/TR/social-web-protocols/#bib-LDN)]; receivers *MAY* add other triples at their discretion.
- Receivers *MUST* return a 201 Created with a Location header or 202 Accepted.
- Receivers *MUST* verify the request by retrieving the source document and checking a link to the target document is present. If the Webmention is not verified, recievers *MUST NOT* keep it.

**Webmention senders** wishing to send to LDN Inboxes need to send a JSON-LD payload. Discover the Inbox endpoint through a relation of `http://www.w3.org/ns/ldp#inbox` between the `target` and the Inbox. A typical Webmention can be represented as JSON-LD per [this example](https://www.w3.org/TR/social-web-protocols/#wm-json), or as ActivityStreams 2.0 JSON per [this example](https://www.w3.org/TR/social-web-protocols/#wm-as2).

>Note: Bridging services
>
>Look out for Webmention-ActivityPub bridges as services. These will provide endpoints to do the heavy lifting of the spec you don't want to implement yourself. You can use these endpoints as your Webmention or Inbox endpoint respectively. Brainstorming and implementations of such bridges can be found on the [Social Web Community Group](https://www.w3.org/wiki/SocialCG) and the [IndieWeb community](https://indieweb.org/bridge#ActivityPub).