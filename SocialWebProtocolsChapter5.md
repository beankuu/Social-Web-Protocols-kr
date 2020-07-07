[목차로 돌아가기](SocialWebProtocolsContents.md)

## 5. Subscribing

An agent (client or server) may ask to be notified of changes to a content object (eg. edits, new replies) or stream of content (eg. objects added or removed from a particular stream). This is subscribing. Specifications which contain subscription mechanisms are ActivityPub and WebSub.

>Note: Subscription vs delivery
>
>Receiving notifications does not need to rely on implementation of a subscription mechanism. That is, implementations may set themselves up to receive notifications without always being required to explicitly ask for them from a sender or publisher: see [delivery](https://www.w3.org/TR/social-web-protocols/#delivery).

### 5.1 Subscribing with `as:Follow`

**[[Activitypub](https://www.w3.org/TR/social-web-protocols/#bib-Activitypub)]** servers maintain a Followers collection for all users. This collection may be directly addressed, or addressed automatically or by default, in the `to`, `cc` or `bcc` field of any Activity. As a result, federated servers [deliver](https://www.w3.org/TR/social-web-protocols/#delivery) the Activity to the `inbox` of each profile in the collection.

Subscription requests are essentially requests to be added to this collection. They are made by the subscriber's server `POST`ing a `Follow` Activity to the target's `inbox`. This request should be authenticated, and therefore doesn't need additional verification. The target server then should add the subscriber to the target's Followers collection. Exceptions may be made if, for example, the target has blocked the subscriber.

This is a suitable subscription mechanism when:

- The subscriber wants to request updates from a specific profile's `outbox` (rather than objects, streams, feeds, collections, conversation threads).
- The subscriber and publisher both speak ActivityStreams 2.0.
- The publisher is aware of who has subscribed, and capable of delivering content to subscribers itself.

Since delivery is only a requirement for federated servers, prospective subscribers will not be able to `POST` their `Follow` activity to the `inbox` of a profile which is on a non-federated server (expect a `405 Method Not Allowed`), and thus are not able to subscribe to these profiles. In this case, prospective subscribers may wish to periodically pull from the publisher's `outbox` instead.

### 5.2 Subscribing with a hub

**[[WebSub](https://www.w3.org/TR/social-web-protocols/#bib-WebSub)]** provides a mechanism to delegate subscription handling and delivery of content to subscribers to a third-party, called a hub. All publishers need to do is link to their chosen hub(s) using HTTP `Link` headers or HTML `<link>` elements with `rel="hub"`, and then notify the hub when new content is available. The mechanism for notifying the hub is left deliberately unspecified, as publishers may have their own built in hub, and therefore use an internal mechanism.

>Note: Notifying the hub
>
>A mechanism for communcation between publishers and hubs may be standardised in future as an extension.

The subscriber discovers the hub from the publisher, and sends a form-encoded `POST` request containing values for `hub.mode` ("subscribe"), `hub.topic` (the URL to subscribe to) and `hub.callback` (the URL where updates should be sent to, which should be 'unguessable' and unique per subscription). The hub and subscriber carry out a series of exchanges to verify this request.

When the hub is notified of new content by the publisher, the hub fetches the content of the `topic` URL, and sends this to the subscriber's `callback` URL via a POST request. The body of the request is the content of the topic URL, and the `Content-Type` must match. A `rel=hub` `Link` header should be included.

This is a suitable subscription mechanism when:

- The subscriber wants to request updates from any resource (not just user profiles), and of any content type.
- Subscription requests are not authenticated, so you need a way to verify them.
- The publisher wants to delegate distribution of updates to another service (the hub) instead of doing it itself.

>Note: WebSub and LDN
>
>LDN Receivers can be used to receive deliveries from WebSub hubs by using the `inbox` URL as the `hub.callback` URL and either only subscribing to resources published as JSON-LD or accepting content-types other than JSON-LD.
