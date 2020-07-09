[목차로 돌아가기](SocialWebProtocolsContents.md)

## 3. [읽기 (Reading)](SocialWebProtocolsContents.md#목차-table-of-contents)

If you are a content publisher, this section is about how you should publish your content. If you are a content consumer, this is what you should expect to consume.

당신이 컨텐츠 게시자인 경우 이 섹션에서는 컨텐츠를 게시하는 방법에 대해 설명합니다. 반대로 컨텐츠 소비자일 경우, 이 섹션에서 다룰 것들을 소비하게 될것입니다.

### 3.1 [컨텐츠 표현 (Content representation)](#3-읽기-reading)

**ActivityStreams 2.0** is the recommended syntax ([[activitystreams-core](https://www.w3.org/TR/social-web-protocols/#bib-activitystreams-core)]) and vocabulary ([[activitystreams-vocabulary](https://www.w3.org/TR/social-web-protocols/#bib-activitystreams-vocabulary)]) for social data. ActivityStreams 2.0 represents content and interactions as _Objects_ and _Activities_. The ActivityStreams vocabulary defines a finite set of common Object and Activity types and properties, as well as an extension mechanism for applications which want to expand on or specialise these.

**ActivityStreams 2.0** 은 소셜 데이터에 권장되는 구문 ([[activityStreams-core](https://www.w3.org/TR/social-web-protocols/#bib-activitystreams-core)]) 과 어휘([[activitystreams-vocabulary](https://www.w3.org/TR/social-web-protocols/#bib-activitystreams-vocabulary)]) 로 이루어져 있습니다. ActivityStreams 2.0은 컨텐츠와 상호작용을 _Objects_ 와 _Activities_ 로 나타냅니다. ActivityStreams 어휘는 한정된 집합의 공통 객체(Object) 및 액티비티(Activity) 타입들과 속성들을 정의하고, 이를 확장하거나 특수화하려는 어플리케이션의 확장 메커니즘을 정의합니다.

ActivityStreams 2.0 content is served with the Content-Type `application/activity+json` or for JSON-LD extended implementations, `application/ld+json; profile="https://www.w3.org/ns/activitystreams"`. Consumers should recognise both of these Content-Types as ActivityStreams 2.0; they should be treated as equivalent.

ActivityStreams 2.0 콘텐츠는 Content-Type `application/activity+json`, JSON-LD 확장 구현에서는 `application/ld+json; profile="https://www.w3.org/ns/activitystreams"` 로 제공됩니다. 소비자는 이 두 가지 Content-Type을 모두 ActivityStream 2.0으로 인식해야 하며 동등하게 취급해야 합니다.

In order to claim ActivityStreams 2.0 conformance, a data publisher must use ActivityStreams 2.0 vocabulary terms where available, and only use other vocabularies _in addition_, or where no appropriate ActivityStreams 2.0 term exists.

ActivityStreams 2.0 준수를 주장하려면 데이터 게시자는 *반드시* 가능한 한 ActivityStreams 2.0 어휘를 사용해야 하며, 다른 어휘들은 _추가적으로만_ 사용하거나 적절한 ActivityStreams 2.0 용어가 없는 경우에만 사용해야 합니다.

>Note: ActivityStreams 1.0
>
>ActivityStreams 2.0 builds upon [[AS1](https://www.w3.org/TR/social-web-protocols/#bib-AS1)] and is not fully backwards compatible; [the relationship between AS1 and AS2 is documented in the AS2 spec](http://www.w3.org/TR/activitystreams-core#activitystreams-1.0). If you have implemented [[AS1](https://www.w3.org/TR/social-web-protocols/#bib-AS1)], you should transition to ActivityStreams 2.0.

>참고: ActivityStreams 1.0
>
>ActivityStreams 2.0은 [[AS1](https://www.w3.org/TR/social-web-protocols/#bib-AS1)]을 기반으로 구축되며 완전하게 역호환되지는 않습니다; [AS1과 AS2의 관계는 AS2 규격에 설명되어 있습니다](http://www.w3.org/TR/activitystreams-core#activitystreams-1.0). [[AS1](https://www.w3.org/TR/social-web-protocols/#bib-AS1)]을 구현한 경우 ActivityStreams 2.0으로 전환해야 합니다.

To make content available as ActivityStreams 2.0 JSON, one could do so directly when requested with an appropriate `Accept` header (eg. `application/activity+json` or `application/ld+json`), or indirectly via a `rel="alternate" type="application/activity+json"` link . This link could be to a different domain, for third-party services which dynamically generate ActivityStreams 2.0 JSON on behalf of a publisher.

컨텐츠가 ActivityStreams 2.0 JSON으로 제공되도록 하려면 적절한 `Accept` 헤더(예: `application/activity+json` 또는 `application/ld+json`)로 요청될 때 직접 또는 `rel="alternate" type="application/activity+json"` 링크를 통해 간접적으로 수행할 수 있습니다. 게시자를 대신하여 ActivityStreams 2.0 JSON 을 동적으로 생성하는 제3자 서비스의 경우 이 링크는 다른 도메인으로 연결될 수 있습니다.

>Note: JSON-LD
>
>When sent as JSON-LD, ActivityStreams 2.0 must be [compacted](https://json-ld.org/spec/latest/json-ld-api/#compaction), and must not use the `@graph` keyword. This is because an ActivityStreams 2.0 document requires a single `Object` as the root. To serve multiple resources, you can instead nest them.
>
>The [ActivityStreams 2.0 JSON-LD context](https://www.w3.org/ns/activitystreams#) (https://www.w3.org/ns/activitystreams#) aliases `@id` and `@type` to `id` and `type` respectively.

>참고: JSON-LD
>
>JSON-LD로 전송되는 경우 ActivityStreams 2.0은 [압축](https://json-ld.org/spec/latest/json-ld-api/#compaction)되어야 하며 절대 `@graph` 키워드를 사용하면 안 됩니다. 그 이유는 ActivityStreams 2.0 문서의 루트로 단일 `Object`가 필요하기 때문입니다. 여러 리소스에 서비스를 제공하기 위해 대신 리소스를 중첩할 수 있습니다.
>
>ActivityStreams 2.0 JSON-LD 컨텍스트(https://www.w3.org/ns/activitystreams#)는 `@id`와 `@type`을 각각 `id`와 `type`로 별칭합니다.

**[[Activitypub](https://www.w3.org/TR/social-web-protocols/#bib-Activitypub)]** uses ActivityStreams 2.0 for all data, and also _extends_ ActivityStreams 2.0 with additional terms. Thus, ActivityPub requires responses to have the Content-Type `application/ld+json; profile="https://www.w3.org/ns/activitystreams"`. Publishers are however expected to also respect requests with the `application/activity+json` Accept header.

**[[Activitypub](https://www.w3.org/TR/social-web-protocols/#bib-Activitypub)]** 은 모든 데이터에 ActivityStreams 2.0을 사용하며 추가적인 용어들과 함께 ActivityStreams 2.0을 _확장_ 합니다. 따라서 ActivityPub를 사용하려면 응답에 Content-Type `application/ld+json; profile="https://www.w3.org/ns/activitystreams"`이 있어야 합니다. 그러나 게시자는 `application/activity+json` 수락 헤더가 있는 요청도 존중해야 합니다.

### 3.1.1 [다른 방법으로 컨텐츠 표현 (Other ways of representing content)](#31-컨텐츠-표현-content-representation)

If you don't like ActivityStreams 2.0, there are still some specifications you can use for particular tasks.

ActivityStreams 2.0이 마음에 들지 않더라도 특정한 작업에 사용할 수 있는 몇 가지 규격들이 있습니다.

**[[LDN](https://www.w3.org/TR/social-web-protocols/#bib-LDN)]** notification contents can use any vocabulary, so long as the data is available as JSON-LD. Thus notifications *MAY* use ActivityStreams 2.0, but don't have to.

**[[LDN](https://www.w3.org/TR/social-web-protocols/#bib-LDN)]** 알림 콘텐츠는 데이터를 JSON-LD로 사용할 수 있는 한 모든 어휘를 사용할 수 있습니다. 따라서 알림은 ActivityStreams 2.0을 사용 *할 수도* 있지만 반드시 그럴 필요는 없습니다.

**[[Micropub](https://www.w3.org/TR/social-web-protocols/#bib-Micropub)]** clients which expect to read data (this would usually be clients for _[updating](https://www.w3.org/TR/social-web-protocols/#updating)_) are expecting it as JSON in the parsed microformats2 syntax ([[microformats2-parsing](https://www.w3.org/TR/social-web-protocols/#bib-microformats2-parsing)]).

**[[Micropub](https://www.w3.org/TR/social-web-protocols/#bib-LDN)]** 클라이언트중 데이터 읽기를 기대하는 클라이언트 (일반적으로 _[업데이트](https://www.w3.org/TR/social-web-protocols/#updating)_ 클라이언트)는 ActivityStreams 2.0 를 구문 분석된 마이크로포맷2 구문([[microformats2-parsing](https://www.w3.org/TR/social-web-protocols/#bib-microformats2-parsing)])이 적용된 JSON으로 예상하고 있습니다.

**[[WebSub](https://www.w3.org/TR/social-web-protocols/#bib-WebSub)]** is agnostic as to the Content-Type used by publishers; hubs are expected to deliver the new content to subscribers as-is produced by the publisher, at the publisher's `topic` URL.

**[[WebSub](https://www.w3.org/TR/social-web-protocols/#bib-WebSub)]**는 게시자가 사용하는 Content-Type에 대해 독립적입니다; 허브는 게시자의 `topic` URL에서 게시자가 제작한 그대로 구독자에게 새 컨텐츠를 전달할 것으로 예상됩니다.

## 3.2 [객체 (Objects)](#3-읽기-reading)

All ActivityStreams 2.0 objects have URLs in the `id` property, which return the properties of an object. The response may vary depending on the requester's right to access the content.

모든 ActivityStreams 2.0 개체는 `id` 속성에 URL을 가지고 있으며, 이 URL은 개체의 속성을 반환합니다. 응답은 요청자의 콘텐츠 액세스 권한에 따라 달라질 수 있습니다.

## 3.3 [컬렉션 (Collections)](#3-읽기-reading)

Each ActivityStreams 2.0 collection has a URL in the `id` property which returns the contents of the stream (according to the requester's right to access). This could be paged - ActivityStreams 2.0 provides [a paging mechanism](https://www.w3.org/TR/activitystreams-core/#paging). It may include additional metadata about the stream (such as title, description).

각 ActivityStreams 2.0 컬렉션에는 요청자의 액세스 권한에 따라 스트림 내용을 반환하는 URL이 `id` 속성이 있습니다. 이는 페이징 될 수 있습니다 - ActivityStreams 2.0은 [페이징 메커니즘](https://www.w3.org/TR/activitystreams-core/#paging)을 제공합니다. 여기에는 스트림에 대한 추가 메타데이터(예를들어 제목이나 설명)가 포함될 수 있습니다.

Each [object](https://www.w3.org/TR/social-web-protocols/#objects) in a collection contains at least its URL (`id`), as well as optionally other properties of the object.

컬렉션의 각 [객체](https://www.w3.org/TR/social-web-protocols/#objects)에는 최소한 URL (`id`)가 포함되고,선택적으로 객체의 다른 속성들이 포함됩니다.

Collections may represent changing streams of objects, or fixed sets. One [profile](https://www.w3.org/TR/social-web-protocols/#profiles) may be associated with one or more streams of content. Streams may be generated automatically or manually, and might be segregated by post type, topic, audience, or any arbitrary criteria decided by the curator of the stream. A profile may include links to multiple streams, which a consumer could follow to read or subscribe to.

컬렉션은 개체 또는 고정 집합의 스트림 변경 사항을 나타낼 수 있습니다. 하나 이상의 내용 스트림과 하나의 [프로필](https://www.w3.org/TR/social-web-protocols/#profiles)이 연관되어 있을 수 있습니다. 스트림은 자동으로 또는 수동으로 생성될 수 있으며, 스트림의 큐레이터가 결정한 포스트 유형, 주제, 청중 또는 임의의 기준에 따라 분리될 수 있습니다. 프로필에는 소비자가 읽거나 구독할 수 있는 여러 스트림에 대한 링크가 포함될 수 있습니다.

### 3.3.1 [특별 스트림 (Special streams)](#33-컬렉션-collections)

**[[Activitypub](https://www.w3.org/TR/social-web-protocols/#bib-Activitypub)]** specifies two streams that *MUST* be accessible from a profile via the following properties:

**[[Activitypub](https://www.w3.org/TR/social-web-protocols/#bib-Activitypub)]** 은 다음 속성을 통해 프로필에서 *반드시* 액세스가 가능해야 하는 두 개의 스트림을 지정합니다.

- `inbox`: A reference to an ActivityStreams 2.0 collection comprising all the objects received by the actor.
- `outbox`: An ActivityStreams 2.0 collection comprising all the objects produced by the actor.

- `inbox`: 작업자가 받은 모든 객체로 구성된 ActivityStreams 2.0 컬렉션에 대한 참조.
- `outbox`: 액터에 의해 생산된 모든 객체로 구성된 ActivityStreams 2.0 컬렉션.

[//Comment]: # "BLANK"

ActivityPub also specifies further properties for accessing additional streams; `following` and `followers` are expected, and the rest are optional:

ActivityPub는 추가 스트림에 접근하기 위한 추가 속성도 지정합니다; `following` 및 `followers`는 필수적이며,나머지는 선택 사항입니다.

- `following`: An ActivityStreams 2.0 collection of the actors that this actor is following.
- `followers`: An ActivityStreams 2.0 collection of the actors that follow this actor
- `liked`: An ActivityStreams 2.0 collection of every `object` from all of the actor's `Like` activities (generated automatically by the server).
- `streams`: A list of supplementary Collections which may be of interest.
- `preferredUsername`
- `endpoints`: A mapping of additional (typically server/domain-wide) endpoints which may be useful either for this actor or someone referencing this actor: `proxyUrl`, `oauthAuthorizationEndpoint`, `oauthTokenEndpoint`, `provideClientKey`, `signClientKey`, `sharedInbox`.
- and any other applicable ActivityStreams 2.0 properties.

[//Comment]: # "BLANK"

- `following`: 이 액터가 팔로우하고 있는 ActivityStreams 2.0 컬렉션.
- `followers`: 이 액터를 팔로잉하는 액터들의 ActivityStreams 2.0 컬렉션
- `liked`: 액터의 모든 (서버에서 자동으로 생성된) `Like` 액티비티의 모든  `object`의 ActivityStreams 2.0 컬렉션.
- `streams`: 관심 있을수도 있는 보조적인 컬렉션 목록.
- `preferredUsername`
- `endpoints`: 이 액터 또는 이 액터를 참조하는 사용자에게 유용할 수 있는 추가(일반적으로 서버/도메인 전체) 엔드포인트의 매핑: `proxyUrl`, `oauthAuthorizationEndpoint`, `oauthTokenEndpoint`, `provideClientKey`, `signClientKey`, `sharedInbox`
- 그리고 위의 속성 외에 해당되는 모든 ActivityStreams 2.0 속성들을 포함합니다.

[[Activitypub](https://www.w3.org/TR/social-web-protocols/#bib-Activitypub)] permits arbitrary collections to be created through specifying special behavior for the server when it receives activities with types `Add` and `Remove`. When a server receives such an activity in the `outbox`, and the `target` is a `Collection`, it adds the `object` to the `target` (for `Add`) or removes the `object` from the `target` (for `Remove`).

[[Activitypub](https://www.w3.org/TR/social-web-protocols/#bib-Activitypub)]은 서버가 `Add` 및 `Remove` 유형의 활동을 수신할 때 서버에 대한 특수 동작을 지정하여 임의 컬렉션을 만들 수 있도록 허용합니다. 서버가 `outbox`에서 이러한 활동을 수신하고 `target`이 `Collection`인 경우, `object`를 `target`에 (`Add` 하기 위해)추가하거나 `object`를 `target`에서 (`Remove` 하기 위해) 제거합니다.

### 3.3.2 [인박스 (Inboxes)](#33-컬렉션-collections)

An Inbox is an endpoint to which new objects may be [delivered](https://www.w3.org/TR/social-web-protocols/#delivery). It also serves as a collection whose contents may be read. The Inbox endpoint is used by both ActivityPub and LDN, and can be discovered through the properties:

인박스은 새로운 객체가 [배달](https://www.w3.org/TR/social-web-protocols/#delivery)될 수 있는 엔드포인트입니다. 또한 내용을 읽힐 수도 있는 컬렉션의 역할도 합니다. 인박스 엔드포인트은 ActivityPub 및 LDN에서 모두 사용되며 다음 속성을 통해 검색할 수 있습니다.

- `ldp:inbox` (`http://www.w3.org/ns/ldp#inbox`)
- `as:inbox` (`https://www.w3.org/ns/activitystreams#inbox`)

In terms of JSON-LD, the latter is an alias of the former.

JSON-LD의 관점에서 후자는 전자의 별칭입니다.

For how and when to write to an Inbox, see [delivery](https://www.w3.org/TR/social-web-protocols/#delivery).

인박스에 글을 어떻게 그리고 언제 쓰는지에 대해서는 [배달](https://www.w3.org/TR/social-web-protocols/#delivery)의 정보를 참조하시길 바랍니다.

The contents of this collection may also be read. While ActivityPub and LDN align for writing to an Inbox, due to irritating but ultimately unavoidable compatibility requirements with AS2 and LDP respectively, they use different vocabularies when Inbox contents are returned for reading. Fortunately for consuming clients to check for both vocabularies or for publishers to publish using both is not a huge implementation hurdle, so bridging is fairly trivial.

이 컬렉션의 내용 역시 읽힐 수도 있습니다. ActivityPub와 LDN은 인박스에 쓰기 위해 동일한 작업을 수행하지만, AS2 및 LDP와의 각각 자극적이지만 피할 수 없는 호환성 요구 사항으로 인해 인박스 내용을 읽을 때는 서로 다른 어휘를 사용합니다. 다행히도 고객이 두 단어를 모두 확인하거나 게시자가 두 단어를 모두 사용하여 게시하는 것은 큰 구현 장애물이 아니기 때문에 브릿징은 매우 사소한 일입니다.

[//Comment]: # "의역"

- ActivityPub Inboxes are an ActivityStreams 2.0 `OrderedCollection`, and link to their contents with the `items` property.
- LDN Inboxes are an [[LDP](https://www.w3.org/TR/social-web-protocols/#bib-LDP)] `Container` (providing an explicit type is optional), and link to their contents with the `contains` property.

[//Comment]: # "BLANK"

- ActivityPub 인박스은 ActivityStreams 2.0 `OrderedCollection`이며, `items` 속성으로 내용에 연결합니다.
- LDN 인박스은 (선택 사항으로 명시적 유형을 제공하는) [[LDP](https://www.w3.org/TR/social-web-protocols/#bib-LDP)] `Container`이며 `contains` 속성으로 자신들의 컨텐츠와 연결합니다.

In addition, ActivityPub has more constraints on the format of the JSON-LD returned. The two lists to follow describe how to bridge the small differences between ActivityPub and LDN conformant Inboxes.

또한 ActivityPub는 반환되는 JSON-LD 형식에 대한 제약 조건이 더 많습니다. 다음 두 목록은 ActivityPub와 LDN을 둘다 지원하는 인박스 안에서 두 표준 사이의 작은 차이를 브릿징 하는 방법을 설명합니다.

**ActivityPub servers** wishing to be read by LDN consumers:

**ActivityPub 서버** 를 LDN 소비자가 읽기를 원할 경우:

- must return alongside the `items` for everything in the collection, an `ldp:contains` (`http://www.w3.org/ns/ldp#contains`) relation.

- 컬렉션의 모든 `items` 와 함께 `ldp:contains` (`http://www.w3.org/ns/ldp#contains`) 관계를 반환해야 합니다.

**ActivityPub clients** wishing to read from LDN Inboxes:

**ActivityPub 클라이언트** 가 LDN 인박스에서 읽기를 원할 경우:

- must request content with the content-type `application/ld+json`. Running it through JSON-LD compaction should help to format the respone in a more friendly way.
- must look for items in the Inbox via the `ldp:contains` property (rather than AS2 `items`).
- should not expect any of the items to have their properties nested; will probably need to retrieve individual items from the URLs in the `@id` property.
- Note the possibility of multiple vocabularies within the items in the Inbox themselves, including potentially a complete absence of any AS2.

[//Comment]: # "BLANK"

- 반드시 content-type `application/ld+json`의 컨텐츠를 요청해야 합니다. JSON-LD 압축을 통해 실행하면 보다 친숙한 방식으로 응답 형식을 지정할 수 있습니다.
- (AS2 `items`가 아닌) `ldp:contains` 속성을 통해 인박스에서 항목들을 찾아내야 합니다.
- 항목 중 어떤 항목도 해당 속성이 중첩될 것으로 예상해서는 안 되며, `@id` 속성의 URL에서 개별적인 항목을 검색해야 할 수 있습니다.
- AS2가 완전히 없는 경우를 포함하여 인박스 자체의 항목 내에서 여러 어휘가 포함될 수 있습니다.

**LDN receivers** wishing to be readable by ActivityPub consuming clients:

**LDN 수신자**가 ActivityPub 사용 클라이언트에서 읽을 수 있기를 원할경우:

- must treat the content-type `application/activity+json` as equivalent to `application/ld+json; profile="http://www.w3.org/ns/activitystreams"`.
- serve Inbox contents as an AS2 `Collection`, where each notification is related to the inbox with the AS2 `items` property.
- must return compacted JSON-LD, and no `@graph`, serving the Inbox collection as the root of the document.
- may make life easier by nesting additional properties of each resource in the Inbox.

[//Comment]: # "BLANK"

- 반드시 content-type `application/activity+json`을 `application/ld+json; profile="http://www.w3.org/ns/activitystreams"`과 동등하게 취급해야 합니다.
- 인박스 내용을 AS2 `Collection`으로 제공해야 합니다. 여기서 각 알림은 AS2 `items` 속성이 있는 인박스와 관련이 있습니다.
- 압축된 JSON-LD를 반환해야 하며, `@graph`는 문서의 루트로 인박스 컬렉션을 제공합니다.
- 인박스에 각 리소스의 추가 속성을 중첩하여 처리하기 더 쉽게 만들 수 있습니다.

**LDN consumers** wishing to read from Inboxes on ActivityPub servers:

**LDN 소비자** 가 ActivityPub 서버의 인박스에서 읽기를 원할 경우:

- must, if content is returned with the content-type `application/activity+json` and missing an `@context`, apply the default AS2 context, and treat it as JSON-LD.
- must look for items in the Inbox via the AS2 `items` property (rather than `ldp:contains`).

[//Comment]: # "BLANK"

- content-type `application/activity+json`과 함께 컨텐츠가 반환되고 `@context`가 누락된 경우 기본 AS2 컨텍스트를 적용하고 이를 JSON-LD로 처리해야 합니다.
- (`ldp:contains` 보다는) AS2 `items` 속성을 통해 인박스에서 항목을 찾아야 합니다.

[맨 위로](#3-읽기-reading)