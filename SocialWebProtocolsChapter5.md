[목차로 돌아가기](SocialWebProtocolsContents.md)

## 5. [구독 (Subscribing)](SocialWebProtocolsContents.md#목차-table-of-contents)

An agent (client or server) may ask to be notified of changes to a content object (eg. edits, new replies) or stream of content (eg. objects added or removed from a particular stream). This is _subscribing_. Specifications which contain subscription mechanisms are ActivityPub and WebSub.

(클라이언트 또는 서버) 에이전트는 콘텐츠 객체(예: 편집, 새로운 응답) 또는 콘텐츠 스트림(예: 특정 스트림에서 추가 또는 제거된 객체)에 대한 변경 사항을 알려달라고 요청할 수 있습니다. 이는 _구독중_ 으로 표현됩니다. 구독 메커니즘을 포함하는 규격은 ActivityPub와 WebSub입니다.

>Note: Subscription vs delivery
>
>Receiving notifications does not need to rely on implementation of a subscription mechanism. That is, implementations may set themselves up to receive notifications without always being required to explicitly ask for them from a sender or publisher: see [delivery](https://www.w3.org/TR/social-web-protocols/#delivery).

>참고: 구독 vs 배달
>
>알림을 받는 것은 구독 메커니즘의 구현에 의존할 필요가 없습니다. 즉, 전송자 또는 게시자로부터 알림을 명시적으로 요청하지 않아도 자체적으로 알림을 받도록 구현을 설정할 수 있습니다. [전달](https://www.w3.org/TR/social-web-protocols/#delivery)을 참조하십시오.

### 5.1 [`as:Follow`를 사용하여 구독 (Subscribing with `as:Follow`)](#5-구독-subscribing)

**[[Activitypub](https://www.w3.org/TR/social-web-protocols/#bib-Activitypub)]** servers maintain a Followers collection for all users. This collection may be directly addressed, or addressed automatically or by default, in the `to`, `cc` or `bcc` field of any Activity. As a result, federated servers [deliver](https://www.w3.org/TR/social-web-protocols/#delivery) the Activity to the `inbox` of each profile in the collection.

**[[Activitypub](https://www.w3.org/TR/social-web-protocols/#bib-Activitypub)]** 서버는 모든 사용자에 대한 팔로워 컬렉션을 유지합니다. 이 컬렉션은 액티비티의 `to`, `cc` 또는 `bcc`인 필드에서 직접 주소를 지정하거나 자동 또는 기본적으로 주소를 지정할 수 있습니다. 그 결과 연합 서버는 액티비티를 컬렉션에 있는 각 프로필의 인박스으로 [전달](https://www.w3.org/TR/social-web-protocols/#delivery)합니다.

Subscription requests are essentially requests to be added to this collection. They are made by the subscriber's server `POST`ing a `Follow` Activity to the target's `inbox`. This request should be authenticated, and therefore doesn't need additional verification. The target server then should add the subscriber to the target's Followers collection. Exceptions may be made if, for example, the target has blocked the subscriber.

구독 요청은 기본적으로 이 컬렉션에 추가하기 위한 요청입니다. 구독자의 서버가 대상의 `inbox`에 `Follow` 액티비티를 `POST`하여 수행됩니다. 이 요청은 인증되어야 하므로 추가적인 인증은 필요하지 않습니다. 그런 다음 대상 서버는 대상의 팔로워 모음에 구독자를 추가해야 합니다. 단, 대상이 구독자를 차단한 경우 예외가 발생할 수 있습니다.

This is a suitable subscription mechanism when:

이는 다음과 같은 경우에 적합한 구독 메커니즘입니다.

- The subscriber wants to request updates from a specific profile's `outbox` (rather than objects, streams, feeds, collections, conversation threads).
- The subscriber and publisher both speak ActivityStreams 2.0.
- The publisher is aware of who has subscribed, and capable of delivering content to subscribers itself.

[//Comment]: # "BLANK"

- 구독자가 객체, 스트림, 피드, 컬렉션, 대화 스레드가 아닌 특정 프로필의 `outbox`에서 업데이트를 요청하려고 합니다.
- 구독자와 게시자가 모두 ActivityStreams 2.0을 사용하여 통신합니다.
- 게시자는 구독자를 알고 있으며 게시자 자신이 구독자에게 콘텐츠를 전달할 능력이 있습니다.

Since delivery is only a requirement for federated servers, prospective subscribers will not be able to `POST` their `Follow` activity to the `inbox` of a profile which is on a non-federated server (expect a `405 Method Not Allowed`), and thus are not able to subscribe to these profiles. In this case, prospective subscribers may wish to periodically pull from the publisher's `outbox` instead.

배달은 연합 서버의 요구 사항일 뿐이므로, 잠재 구독자는 연합되지 않은 서버에 있는 프로필의 인박스에 (예외사항인 `405 Method Not Allowed`를 제외하고) `Follow` 액티비티를 `POST`할 수 없으므로 이러한 프로필에는 구독할 수 없습니다. 이 경우 잠재 구독자는 게시자의 `outbox`에서 정기적으로 내용을 가져오기를 원할 수도 있습니다.

### 5.2 [hub를 사용하여 구독 (Subscribing with a hub)](#5-구독-subscribing)

**[[WebSub](https://www.w3.org/TR/social-web-protocols/#bib-WebSub)]** provides a mechanism to delegate subscription handling and delivery of content to subscribers to a third-party, called a hub. All publishers need to do is link to their chosen hub(s) using HTTP `Link` headers or HTML `<link>` elements with `rel="hub"`, and then notify the hub when new content is available. The mechanism for notifying the hub is left deliberately unspecified, as publishers may have their own built in hub, and therefore use an internal mechanism.

**[[WebSub](https://www.w3.org/TR/social-web-protocols/#bib-WebSub)]**는 허브 라고 하는 제3자 가입자에게 구독 처리 및 콘텐츠 전달을 위임하는 메커니즘을 제공합니다. 게시자가 해야 할 일은 HTTP `Link` 헤더 또는 `rel="hub"`가 있는 HTML `<link>` 요소를 사용하여 선택한 허브에 연결한 후 새로운 콘텐츠가 사용 가능할 때 허브에 알리는 것입니다. 게시자가 자체 허브에 내장되어 있을 수 있으므로 허브에 알리기 위한 메커니즘은 의도적으로 지정되지 않은 상태로 방치됩니다.

>Note: Notifying the hub
>
>A mechanism for communcation between publishers and hubs may be standardised in future as an extension.

>참고: 허브에게 알림 전달
>
>게시자와 허브 간의 공통화를 위한 메커니즘은 향후 확장으로서 표준화될 수도 있습니다.

The subscriber discovers the hub from the publisher, and sends a form-encoded `POST` request containing values for `hub.mode` ("subscribe"), `hub.topic` (the URL to subscribe to) and `hub.callback` (the URL where updates should be sent to, which should be 'unguessable' and unique per subscription). The hub and subscriber carry out a series of exchanges to verify this request.

구독자는 게시자에서 허브를 검색하고, `hub.mode`("구독"), `hub.topic`(구독할 URL) 및 `hub.callback`(업데이트가 전송될, '추측이 불가능한' 구독별 URL) 값이 포함된 폼 인코딩 `POST` 요청을 보냅니다. 허브와 구독자는 일련의 교환을 수행하여 이 요청을 확인합니다.

When the hub is notified of new content by the publisher, the hub fetches the content of the `topic` URL, and sends this to the subscriber's `callback` URL via a POST request. The body of the request is the content of the topic URL, and the `Content-Type` must match. A `rel=hub` `Link` header should be included.

허브가 게시자로부터 새 내용을 통지받으면 허브는 `topic` URL의 내용을 가져오고, 이를 POST 요청을 통해 가입자의 `callback` URL로 보냅니다. 요청 본문은 항목 URL의 내용이며, `Content-Type`은 반드시 일치해야 합니다. `rel=hub` `Link` 헤더가 포함되어야 합니다.

This is a suitable subscription mechanism when:

이는 다음과 같은 경우에 적합한 구독 메커니즘입니다.

- The subscriber wants to request updates from any resource (not just user profiles), and of any content type.
- Subscription requests are not authenticated, so you need a way to verify them.
- The publisher wants to delegate distribution of updates to another service (the hub) instead of doing it itself.

[//Comment]: # "BLANK"

- 구독자는 사용자 프로필뿐만 아니라 모든 리소스 및 콘텐츠 유형에 대한 업데이트를 요청하려고 합니다.
- 구독 요청이 인증되지 않았으므로 확인할 수 있는 방법이 필요합니다.
- 게시자가 업데이트 배포를 직접 수행하는 대신 다른 서비스(허브)에 위임하려고 합니다.

>Note: WebSub and LDN
>
>LDN Receivers can be used to receive deliveries from WebSub hubs by using the `inbox` URL as the `hub.callback` URL and either only subscribing to resources published as JSON-LD or accepting content-types other than JSON-LD.

>참고: WebSub와 LDN
>
>LDN 수신기는 `inbox` URL을 `hub.callback` URL로 사용하고 JSON-LD로 게시된 리소스에만 가입하거나 JSON-LD 이외의 content-types를 수락하여 WebSub 허브에서 전달을 수신하는 데 사용할 수 있습니다.

[맨 위로](#5-구독-subscribing)
