[목차로 돌아가기](SocialWebProtocolsContents.md)

## 3. Reading

If you are a content publisher, this section is about how you should publish your content. If you are a content consumer, this is what you should expect to consume.

### 3.1 Content representation

**ActivityStreams 2.0** is the recommended syntax ([[activitystreams-core](https://www.w3.org/TR/social-web-protocols/#bib-activitystreams-core)]) and vocabulary ([[activitystreams-vocabulary](https://www.w3.org/TR/social-web-protocols/#bib-activitystreams-vocabulary)]) for social data. ActivityStreams 2.0 represents content and interactions as _Objects_ and _Activities_. The ActivityStreams vocabulary defines a finite set of common Object and Activity types and properties, as well as an extension mechanism for applications which want to expand on or specialise these.

ActivityStreams 2.0 content is served with the Content-Type `application/activity+json` or for JSON-LD extended implementations, `application/ld+json; profile="https://www.w3.org/ns/activitystreams"`. Consumers should recognise both of these Content-Types as ActivityStreams 2.0; they should be treated as equivalent.

In order to claim ActivityStreams 2.0 conformance, a data publisher must use ActivityStreams 2.0 vocabulary terms where available, and only use other vocabularies _in addition_, or where no appropriate ActivityStreams 2.0 term exists.

>Note: ActivityStreams 1.0
>
>ActivityStreams 2.0 builds upon [[AS1](https://www.w3.org/TR/social-web-protocols/#bib-AS1)] and is not fully backwards compatible; [the relationship between AS1 and AS2 is documented in the AS2 spec](http://www.w3.org/TR/activitystreams-core#activitystreams-1.0). If you have implemented [[AS1](https://www.w3.org/TR/social-web-protocols/#bib-AS1)], you should transition to ActivityStreams 2.0.

To make content available as ActivityStreams 2.0 JSON, one could do so directly when requested with an appropriate `Accept` header (eg. `application/activity+json` or `application/ld+json`), or indirectly via a `rel="alternate" type="application/activity+json"` link . This link could be to a different domain, for third-party services which dynamically generate ActivityStreams 2.0 JSON on behalf of a publisher.

>Note: JSON-LD
>
>When sent as JSON-LD, ActivityStreams 2.0 must be [compacted](https://json-ld.org/spec/latest/json-ld-api/#compaction), and must not use the `@graph` keyword. This is because an ActivityStreams 2.0 document requires a single `Object` as the root. To serve multiple resources, you can instead nest them.
>
>The [ActivityStreams 2.0 JSON-LD context](https://www.w3.org/ns/activitystreams#) (https://www.w3.org/ns/activitystreams#) aliases `@id` and `@type` to `id` and `type` respectively.

**[[Activitypub](https://www.w3.org/TR/social-web-protocols/#bib-Activitypub)]** uses ActivityStreams 2.0 for all data, and also _extends_ ActivityStreams 2.0 with additional terms. Thus, ActivityPub requires responses to have the Content-Type `application/ld+json; profile="https://www.w3.org/ns/activitystreams"`. Publishers are however expected to also respect requests with the a`pplication/activity+json` Accept header.

### 3.1.1 Other ways of representing content

If you don't like ActivityStreams 2.0, there are still some specifications you can use for particular tasks.

[[LDN](https://www.w3.org/TR/social-web-protocols/#bib-LDN)] notification contents can use any vocabulary, so long as the data is available as JSON-LD. Thus notifications *MAY* use ActivityStreams 2.0, but don't have to.

**[[Micropub](https://www.w3.org/TR/social-web-protocols/#bib-Micropub)]** clients which expect to read data (this would usually be clients for _[updating](https://www.w3.org/TR/social-web-protocols/#updating)_) are expecting it as JSON in the parsed microformats2 syntax ([[microformats2-parsing](https://www.w3.org/TR/social-web-protocols/#bib-microformats2-parsing)]).

**[[WebSub](https://www.w3.org/TR/social-web-protocols/#bib-WebSub)]** is agnostic as to the Content-Type used by publishers; hubs are expected to deliver the new content to subscribers as-is produced by the publisher, at the publisher's `topic` URL.

## 3.2 Objects

All ActivityStreams 2.0 objects have URLs in the `id` property, which return the properties of an object. The response may vary depending on the requester's right to access the content.

## 3.3 Collections

Each ActivityStreams 2.0 collection has a URL in the `id` property which returns the contents of the stream (according to the requester's right to access). This could be paged - ActivityStreams 2.0 provides [a paging mechanism](https://www.w3.org/TR/activitystreams-core/#paging). It may include additional metadata about the stream (such as title, description).

Each [object](https://www.w3.org/TR/social-web-protocols/#objects) in a collection contains at least its URL (`id`), as well as optionally other properties of the object.

Collections may represent changing streams of objects, or fixed sets. One [profile](https://www.w3.org/TR/social-web-protocols/#profiles) may be associated with one or more streams of content. Streams may be generated automatically or manually, and might be segregated by post type, topic, audience, or any arbitrary criteria decided by the curator of the stream. A profile may include links to multiple streams, which a consumer could follow to read or subscribe to.
3.3.1 Special streams

**[[Activitypub](https://www.w3.org/TR/social-web-protocols/#bib-Activitypub)]** specifies two streams that *MUST* be accessible from a profile via the following properties:

- `inbox`: A reference to an ActivityStreams 2.0 collection comprising all the objects received by the actor.
- `outbox`: An ActivityStreams 2.0 collection comprising all the objects produced by the actor.

ActivityPub also specifies further properties for accessing additional streams; `following` and `followers` are expected, and the rest are optional:

- `following`: An ActivityStreams 2.0 collection of the actors that this actor is following.
- `followers`: An ActivityStreams 2.0 collection of the actors that follow this actor
- `liked`: An ActivityStreams 2.0 collection of every `object` from all of the actor's `Like` activities (generated automatically by the server).
- `streams`: A list of supplementary Collections which may be of interest.
- `preferredUsername`
- `endpoints`: A mapping of additional (typically server/domain-wide) endpoints which may be useful either for this actor or someone referencing this actor: `proxyUrl`, `oauthAuthorizationEndpoint`, `oauthTokenEndpoint`, `provideClientKey`, `signClientKey`, `sharedInbox`.
- and any other applicable ActivityStreams 2.0 properties.

[[Activitypub](https://www.w3.org/TR/social-web-protocols/#bib-Activitypub)] permits arbitrary collections to be created through specifying special behavior for the server when it receives activities with types `Add` and `Remove`. When a server receives such an activity in the `outbox`, and the `target` is a `Collection`, it adds the `object` to the `target` (for `Add`) or removes the `object` from the `target` (for `Remove`).

### 3.3.2 Inboxes

An Inbox is an endpoint to which new objects may be [delivered](https://www.w3.org/TR/social-web-protocols/#delivery). It also serves as a collection whose contents may be read. The Inbox endpoint is used by both ActivityPub and LDN, and can be discovered through the properties:

- `ldp:inbox` (`http://www.w3.org/ns/ldp#inbox`)
- `as:inbox` (`https://www.w3.org/ns/activitystreams#inbox`)

In terms of JSON-LD, the latter is an alias of the former.

For how and when to write to an Inbox, see [delivery](https://www.w3.org/TR/social-web-protocols/#delivery).

The contents of this collection may also be read. While ActivityPub and LDN align for writing to an Inbox, due to irritating but ultimately unavoidable compatibility requirements with AS2 and LDP respectively, they use different vocabularies when Inbox contents are returned for reading. Fortunately for consuming clients to check for both vocabularies or for publishers to publish using both is not a huge implementation hurdle, so bridging is fairly trivial.

- ActivityPub Inboxes are an ActivityStreams 2.0 `OrderedCollection`, and link to their contents with the `items` property.
- LDN Inboxes are an [[LDP](https://www.w3.org/TR/social-web-protocols/#bib-LDP)] `Container` (providing an explicit type is optional), and link to their contents with the `contains` property.

In addition, ActivityPub has more constraints on the format of the JSON-LD returned. The two lists to follow describe how to bridge the small differences between ActivityPub and LDN conformant Inboxes.

**ActivityPub servers** wishing to be read by LDN consumers:

- must return alongside the `items` for everything in the collection, an `ldp:contains` (`http://www.w3.org/ns/ldp#contains`) relation.

**ActivityPub clients** wishing to read from LDN Inboxes:

- must request content with the content-type `application/ld+json`. Running it through JSON-LD compaction should help to format the respone in a more friendly way.
- must look for items in the Inbox via the `ldp:contains` property (rather than AS2 `items`).
- should not expect any of the items to have their properties nested; will probably need to retrieve individual items from the URLs in the `@id` property.
- Note the possibility of multiple vocabularies within the items in the Inbox themselves, including potentially a complete absence of any AS2.

**LDN receivers** wishing to be readable by ActivityPub consuming clients:

- must treat the content-type `application/activity+json` as equivalent to `application/ld+json; profile="http://www.w3.org/ns/activitystreams"`.
- serve Inbox contents as an AS2 `Collection`, where each notification is related to the inbox with the AS2 `items` property.
- must return compacted JSON-LD, and no `@graph`, serving the Inbox collection as the root of the document.
- may make life easier by nesting additional properties of each resource in the Inbox.

**LDN consumers** wishing to read from Inboxes on ActivityPub servers:

- must, if content is returned with the content-type `application/activity+json` and missing an `@context`, apply the default AS2 context, and treat it as JSON-LD.
- must look for items in the Inbox via the AS2 `items` property (rather than `ldp:contains`).