[목차로 돌아가기](SocialWebProtocolsContents.md)

## 7. Profiles

The subject of a profile document can be a person, persona, organisation, bot, location, or other. None of the specifications described here prescribe particular relationships between real-world entities and online profiles. That is, one person can have many profiles, and one profile may be controlled by many people. How/if/when multiple profiles are linked together is implementation specific, and not specified anywhere here.

Most specifications expect that profiles are identified by and retrieved from a URL, and that attributes of the subject of the profile are available from the URL. Ideally they also return a link to at least one stream of content associated with the profile (or embed the content directly), for example activities or blog posts.

**ActivityPub** profiles are JSON-LD documents containing any appropriate ActivityStreams 2.0 properties, as well as links to various endpoints and collections (see [3.3.1 Special streams](https://www.w3.org/TR/social-web-protocols/#streams-special)).

**ActivityStreams 2.0** has various [Actor types](https://www.w3.org/TR/activitystreams-core/#actors), which may be used to represent individuals or groups, and also includes `Profile`.

**Micropub** has a notion of a profile page (URL) that represents a user, but does not specify the format of that page, except for the link to the Micropub endpoint and authorization endpoints for clients to discover.

**Webmention** does not specify any particular profile format, but in practice Webmention implementations typically publish and consume [[h-card](https://www.w3.org/TR/social-web-protocols/#bib-h-card)] profile information to display authors of webmention sources (see [examples in the Webmention spec](https://www.w3.org/TR/webmention/#webmention-verification-p-4)).

### 7.1 Relationships

Semantics and representation of personal relationships are implementation specific. These specifications deal with relationships only when distribution of content is affected, for example when 'following' triggers a subscription request from one server to another. Lists of other relationships may be discoverable from a user profile, should be represented according to the ActivityStreams 2.0 syntax and may (and are likely to) use extension vocabularies as needed.

- **ActivityPub**: When a server receives a `Follow` Activity in its `inbox`, the subject is added to a `Followers Collection`, which is discoverable from the subject's profile. Federated servers use this collection to deliver updates when new content is created by the owner of the collection.

### 7.2 Authentication, authorization, and access control

Authentication and authorization mechanisms were out of scope for the Social Web WG. Please follow the [Community Group](https://www.w3.org/wiki/SocialCG) for development in this space. Meanwhile, some of the WG specifications contain non-normative notes on the topic:

- **ActivityPub**: Points to a Community Group best practices report in [B.1 Authentication and Authorization](https://www.w3.org/TR/activitypub/#authorization).
- **LDN**: Recommends that receivers employ some kind of verification mechanism which may be authentication in [3.3.3 Sender verification](https://www.w3.org/TR/ldn/#sender-verification), with additional security considerations in [5.6 Authenticated inboxes](https://www.w3.org/TR/ldn/#authenticated-inboxes).
- **Micropub**: Requires bearer tokens, and suggests IndieAuth in [5. Authentication and Authorization](https://www.w3.org/TR/micropub/#authentication-and-authorization).
- **Webmention**: Points to an extension for use with access controlled posts in [B.3 Private Webmention](https://www.w3.org/TR/webmention/#private-webmention).
- **WebSub**: Describes optional use of HMAC Signatures in [8.1 Authenticated Content Distribution](https://www.w3.org/TR/websub/#authenticated-content-distribution).