[목차로 돌아가기](SocialWebProtocolsContents.md)

## 6. [전달 (Delivery)](SocialWebProtocolsContents.md#목차-table-of-contents)

A user or application may wish to push a notification to another user that the receiver has not explicitly asked for. For example to send a message or some new information; because they have linked to (replied, liked, bookmarked, reposted, etc) their content; because they have linked to (tagged, addressed) the user directly; to make the recipient aware of a change in state of some document or resource on the Web. The Social Web Working Group specifications contain several mechanisms for carrying out delivery; they are listed here from general to specialised.

사용자 또는 어플리케이션은 수신자가 명시적으로 요청하지 않은 알림을 다른 사용자에게 전달하려고 할 수도 있습니다. 예를 들어, 메시지 또는 새로운 정보를 보내기 위해; 콘텐츠에 연결(회신, 좋아요, 즐겨찾기, 책갈피, 다시 게시 등) 했기 때문에; 사용자와 직접 연결(태깅, 언급)했기 때문에; 수신자가 웹 상의 일부 문서 또는 리소스의 상태 변경을 인식하도록 합니다. Social Web Working Group 규격에는 전달을 수행하기 위한 몇 가지 메커니즘이 포함되어 있습니다; 이 메커니즘은 일반적인 메커니즘부터 특수화된 메커니즘까지 여기에 기재되어 있습니다.

[//Comment]: # "addressing을 언급 으로 번역했습니다"

>Note: Delivery vs subscription
>
>We need to leave it open for users to refuse content they have not explicitly [subscribed](https://www.w3.org/TR/social-web-protocols/#subscribing) to, ie. nothing else should rely on implementation of delivery.

>참고: 배달 vs 구독.
>
>사용자가 명시적으로 [구독](https://www.w3.org/TR/social-web-protocols/#subscribing)하지 않은 콘텐츠를 거부할 수 있도록 내버려 둘 필요가 있습니다. 예를 들어 다른 어떤 것도 배달의 구현에 의존해서는 안 됩니다.

### 6.1 [타겟팅과 발견 (Targeting and discovery)](#6-전달-delivery)

The target of a notification is usually the addressee or the subject, as referenced by a URL. The target may also a resource which has previously requested notifications through a [subscription](https://www.w3.org/TR/social-web-protocols/#subscribing) request. Once you have determined your target, you need to discover where to send the notification for that particular target. Discovery is fetching the target URL and looking for a link to an endpoint which will accept the type of notification you want to send (read on, for all of your exciting options).

알림의 대상은 일반적으로 URL에서 참조하는 주소록 또는 제목입니다. 또한 대상은 이전에 [구독](https://www.w3.org/TR/social-web-protocols/#subscribing) 요청을 통해 알림을 요청한 리소스일 수 있습니다. 대상을 결정한 후에는 특정 대상에 대한 알림을 보낼 위치를 검색해야 합니다. 검색에서 대상 URL을 가져와서 보낼 알림 유형(읽기 시작)을 승인할 엔드포인트에 대한 링크를 찾고 있습니다.

Bear in mind that many potential targets will not be configured to receive notifications at all. To avoid overloading unsuspecting servers with discovery-related requests, your application should employ a "back-off" strategy when carrying out discovery multiple times to targets on the same domin. This could involve increasing the period of time between subsequent requests, or caching unsuccessful discovery attempts so those domains can be avoided in future. You may wish to send a `User-Agent` header with a reference to the notification mechanism you are using so that recipient servers can find out more about the purpose of your requests.

많은 잠재적 대상들이 알림을 받도록 구성되지 않을 수도 있다는 점을 유의하시길 바랍니다. 의심하지 않는 서버에 검색 관련 요청으로 과부하를 하지 않도록 하려면 어플리케이션은 동일한 도메인에 있는 대상에 검색을 여러 번 수행할 때 "백오프" 전략을 사용해야 합니다. 이 작업에는 이후 요청 사이의 시간을 늘리거나 실패한 검색 시도를 캐싱하여 나중에 해당 도메인을 피할 수 있습니다. 수신자 서버가 요청의 목적에 대해 자세히 알 수 있도록 사용 중인 알림 메커니즘에 대한 참조와 함께 `User-Agent` 헤더를 보낼 수 있습니다.

Your application should also respect relevant cache control and retry headers returned by the target server.

또한 어플리케이션은 대상 서버에서 반환한 관련된 캐시 제어 및 재시도 헤더를 고려해야 합니다.

### 6.2 [일반적인 알림 (Generic notifications)](#6-전달-delivery)

**[[LDN](https://www.w3.org/TR/social-web-protocols/#bib-LDN)]** is a federation protocol for sending, receiving and consuming notifications which may contain any content, and be triggered by any person or process. Senders, receivers and consumers can all be on different domains. This is a suitable notification mechanism when:

**[[LDN](https://www.w3.org/TR/social-web-protocols/#bib-LDN)]**은 콘텐츠를 포함할 수 있는 알림을 전송, 수신 및 소비하기 위한 연합 프로토콜이며, 사용자 또는 프로세스에 의해 트리거됩니다. 보내는 사람, 받는 사람 및 소비자는 모두 다른 도메인에 있을 수 있습니다. 이는 다음과 같은 경우에 적합한 알림 메커니즘입니다.

- Notifications need to be identifiable with their own URLs and exposed by the receiver for other applications to discover and re-use.
- Notifications are represented as a JSON-LD payload (ie. a 'fat ping').
- You need to advertise constraints on the type or contents of notifications accepted by a receiver.

[//Comment]: # "BLANK"

- 알림은 자신의 URL로 식별할 수 있어야 하며 수신자에 의해 노출되어 다른 어플리케이션이 검색하고 재사용할 수 있어야 합니다.
- 알림은 JSON-LD 페이로드(예: '뚱뚱한 핑')로 표시됩니다.
- 수신자가 수락한 알림 유형 또는 내용에 대한 제약 조건을 알려야 합니다.

[[LDN](https://www.w3.org/TR/social-web-protocols/#bib-LDN)] functionality is divided between senders, receivers and consumers. The endpoint to which notifications are sent is the `inbox`. Any resource (a user profile, blog post, document) can advertise its `inbox` so that it may be discovered through an HTTP `Link` header or the document body in any RDF syntax (including JSON-LD or HTML+RDFa). To this Inbox, senders make a `POST` request containing the JSON-LD (or other RDF syntax per [[Accept-Post](https://www.w3.org/TR/social-web-protocols/#bib-Accept-Post)] negotation with the receiver) payload of the notification. The receiver returns a URL from which the notification data can be retrieved, and also adds this URL to a list which is returned upon a `GET` request to the Inbox (see [3. Reading](https://www.w3.org/TR/social-web-protocols/#reading)). Consumers can retrieve this Inbox listing, and from there the individual notifications, as JSON-LD (optionally content negotiated to another RDF syntax). An obvious type of consumer is a script which displays notifications in a human-readable way.

[[LDN](https://www.w3.org/TR/social-web-protocols/#bib-LDN)] 기능은 송신자, 수신자 및 소비자로 구분됩니다. 알림이 전송되는 엔드포인트는 `inbox`입니다. (사용자 프로필, 블로그 게시물, 문서 같은) 모든 리소스는 HTTP 링크 헤더 또는 (JSON-LD 또는 HTML+RDFa 를 포함한) 모든 RDF 구문에서 문서의 본문을 통해 검색할수 있도록 `inbox`를 알릴 수 있습니다. 이 인박스에 대해 송신자는 알림의 JSON-LD(또는 수신자와의 [[Accept-Post](https://www.w3.org/TR/social-web-protocols/#bib-Accept-Post)] 를 주고받은 RDF 구문 같은) 페이로드를 포함하는 `POST` 요청을 합니다. 수신자는 알림 데이터를 검색할 수 있는 URL을 반환하고 `GET` 요청 시 인박스로 반환되는 목록에 이 URL을 추가합니다 ([3. 읽기](https://www.w3.org/TR/social-web-protocols/#reading) 참조). 소비자는 이 인박스 목록과 이 목록에서의 개별 알림을 JSON-LD(선택적으로는 다른 RDF 구문과 주고받은 콘텐츠)로 받아 볼 수 있습니다. 확실한 소비자의 유형은 사람이 읽을 수 있는 방식으로 알림을 표시하는 스크립트입니다.

>Note: LDP compatibility
>
>An existing [[LDP](https://www.w3.org/TR/social-web-protocols/#bib-LDP)] implementation can serve as an [[LDN](https://www.w3.org/TR/social-web-protocols/#bib-LDN)] receiver out of the box; publishers simply advertise any `ldp:Container` as the `inbox` for a resource.

>참고: LDP 호환성
>
>기존 [[LDP](https://www.w3.org/TR/social-web-protocols/#bib-LDP)] 구현은 즉시 [[LDN](https://www.w3.org/TR/social-web-protocols/#bib-LDN)] 수신자 역할을 할 수 있습니다; 게시자는 `ldp:Container` 를 리소스의 `inbox`로 사용한다 라고 알리면 됩니다.

The payload of notifications is deliberately left open so that LDN may be used in a wide variety of use cases. However, receivers with particular purposes are likely to want to constrain the types of notifications they accept. They can do this transparently (such that senders are able to attempt to conform, rather than having their requests rejected opaquely) by advertising data shapes constraints such as [[SHACL](https://www.w3.org/TR/social-web-protocols/#bib-SHACL)]. Advertisement of such constraints also allows consumers to understand the types of notifications in the Inbox before attempting to retrieve them. Receivers may reject notifications on the basis of internal, undisclosed constraints, and may also access control the Inbox for example by requiring an `Authorization` header from both senders and consumers.

다양한 사용 사례에서 LDN을 사용할 수 있도록 알림 페이로드는 의도적으로 열려 있습니다. 그러나 특정 목적을 가진 수신자는 수신자가 수락하는 알림 유형을 제한하려고 할 가능성이 높습니다. 따라서 [[SHACL](https://www.w3.org/TR/social-web-protocols/#bib-SHACL)]과 같은 데이터 모양 제약 조건을 광고함으로써 전송자가 요청을 불투명하게 거부하지 않고 이를 준수하려고 시도할 수 있습니다. 또한 이러한 제약 조건을 알리는 광고를 통해 사용자는 인박스의 알림 유형을 확인한 후 검색할 수 있습니다. 수신자는 내부 및 공개되지 않은 제약 조건에 따라 알림을 거부할 수 있으며, 예를 들어 발신자과 소비자 모두의 `Authorization` 헤더를 요구하여 인박스에 액세스할 수도 있습니다.

[[WebSub](https://www.w3.org/TR/social-web-protocols/#bib-WebSub)] publishers deliver content to their hub, and hubs to their subscribers using HTTP `POST` requests. The body of the request is left to the discretion of the sender in the first case, and in the latter case must match the Content-Type of and contain contents from the `topic` URL.

[[WebSub](https://www.w3.org/TR/social-web-protocols/#bib-WebSub)] 게시자는 HTTP `POST` 요청을 사용하여 컨텐츠를 허브로, 허브는 가입자에게 전달합니다. 요청 본문은 전자의 경우에는 발신자의 재량에 맡기고, 후자의 경우에는 Content-Type과 일치해야 하며 `topic` URL의 내용을 포함해야 합니다.

### 6.3 [액티비티 알림 (Activity notifications)](#6-전달-delivery)

**[[Activitypub](https://www.w3.org/TR/social-web-protocols/#bib-Activitypub)]** uses [[LDN](https://www.w3.org/TR/social-web-protocols/#bib-LDN)] to send notifications with some specific constraints. These are:

**[[Activitypub](https://www.w3.org/TR/social-web-protocols/#bib-Activitypub)]**에서는 [[LDN](https://www.w3.org/TR/social-web-protocols/#bib-LDN)]을 사용하여 몇 가지 특정 제약 조건이 있는 알림을 보냅니다. 이는 다음과 같습니다:

- The notification payload *MUST* be a single ActivityStreams 2.0 Activity.
- The notification payload *MUST* be compact JSON-LD.
- The receiver *MUST* verify the notification by fetching its source from the origin server.
- All notification `POST` requests are authenticated.

[//Comment]: # "BLANK"

- 알림 페이로드는 *반드시* 단일 ActivityStreams 2.0 활동이어야 합니다.
- 알림 페이로드는 *반드시* 소형 JSON-LD여야 합니다.
- 수신자는 *반드시* 본래 서버에서 해당 소스를 가져와 알림을 확인해야 합니다.
- 모든 알림 `POST` 요청은 인증됩니다.

[[Activitypub](https://www.w3.org/TR/social-web-protocols/#bib-Activitypub)] specifies how to define the target(s) to which a notification is to be sent (a pre-requisite to [[LDN](https://www.w3.org/TR/social-web-protocols/#bib-LDN)] sending), via the [[activitystreams-vocabulary](https://www.w3.org/TR/social-web-protocols/#bib-activitystreams-vocabulary)] audience targeting and object linking properties.

[[Activitypub](https://www.w3.org/TR/social-web-protocols/#bib-Activitypub)]는 [[activitystreams-vocabulary](https://www.w3.org/TR/social-web-protocols/#bib-activitystreams-vocabulary)] 청중을 지정과 객체 연결 속성을 통해 ([[LDN](https://www.w3.org/TR/social-web-protocols/#bib-LDN)] 전송의 사전 요구 사항인) 알림을 보낼 대상을 정의하는 방법을 지정합니다.

[[Activitypub](https://www.w3.org/TR/social-web-protocols/#bib-Activitypub)] also defines side-effects that must be carried out by the server as a result of notification receipt. These include:

[[Activitypub](https://www.w3.org/TR/social-web-protocols/#bib-Activitypub)]은 알림 수신의 결과로 서버가 수행해야 하는 부작용도 정의합니다. 여기에는 다음이 포함됩니다.

- Creating, updating or deleting new objects upon receipt of `Create`, `Update` and `Delete` activities.
- Reversing the side-effects of prior activities upon receipt of the `Undo` activity.
- Updating specialised collections for `Follow`, `Like` and `Block` activities.
- Updating any other collections upon receipt of `Add` and `Remove` activities.
- Carrying out further delivery to propagate activities through the network in the case of federated servers.

[//Comment]: # "BLANK"

- `Create`, `Update` 및 `Delete` 작업을 수신 후 새 객체를 만들거나 업데이트 또는 삭제합니다.
- `Undo` 액티비티를 수신한 후 이전 활동의 부작용을 반전시킵니다.
- `Follow`, `Like` 및 `Block`에 대해 특화된 컬렉션들을 업데이트합니다.
- `Add` 와 `Remove` 액티비티을 수신 후 다른 컬렉션들을 업데이트합니다.
- 연합 서버의 경우 네트워크를 통해 액티비티를 전파하기 위한 추가 전달을 수행합니다.

>Note: The inbox property
>
>ActivityPub actor profiles are linked to their inboxes via the `https://www.w3.org/ns/activitystreams#inbox` property. This is an alias (in the AS2 JSON-LD context) for LDN's `http://www.w3.org/ns/ldp#inbox`. Applications using a full JSON-LD processor to parse these documents will see these terms as one and the same. Applications doing naive string matching on terms may wish to note that if you find an `ldp:inbox` it will accept `POST` requests in the same way as an `as:inbox`.

>참고: 인박스 속성
>
>ActivityPub 작업자 프로필은 `https://www.w3.org/ns/activitystreams#inbox` 속성을 통해 인박스에 연결됩니다. 이것은 LDN의 `http://www.w3.org/ns/ldp#inbox`에 대한 (AS2 JSON-LD 컨텍스트에서의)별칭입니다. 이러한 문서를 구문 분석하기 위해 전체 JSON-LD 프로세서를 사용하는 어플리케이션에서는 이 용어들을 같은 용어로 취급할수 있습니다. 게으른 문자열 매칭을 수행하는 어플리케이션은 `ldp:inbox`를 찾으면 `as:inbox`와 동일한 방식으로 `POST` 요청을 수락한다는 점을 유념해야 합니다.

### 6.4 [멘션 (Mentioning)](#6-전달-delivery)

**[[Webmention](https://www.w3.org/TR/social-web-protocols/#bib-Webmention)]** provides an API for sending and receiving notifications when a relationship is created (or updated, or deleted) between two documents. A webmention sender is triggered by the creation (or modification) of content which includes the URL of another document. It works when the two documents are on different domains, thus serving as a federation protocol. This is a suitable notification mechanism when:

**[[Webmention](https://www.w3.org/TR/social-web-protocols/#bib-Webmention)]**은 두 문서 간에 관계가 생성(또는 업데이트 또는 삭제)될 때 알림을 보내고 받을 수 있는 API를 제공합니다. Webmention 발신자는 다른 문서의 URL을 포함하는 내용의 작성(또는 수정)에 의해 트리거됩니다. 두 문서가 서로 다른 도메인에 있을 때 작동하므로 이는 연합 프로토콜의 역할을 합니다. 이는 다음과 같은 경우에 적합한 알림 메커니즘입니다:

- You have a document (source) which contains the URL of another document (target).
- The owner of the endpoint has access to view the source (so the request can be verified).
- The only data you need to send over the wire are the URLs of the source and target documents (ie. a 'thin ping').

[//Comment]: # "BLANK"

- 다른 문서(대상)의 URL을 포함하는 문서(출처)가 있습니다.
- 엔드포인트 소유자는 요청을 확인할 수 있도록 소스를 볼 수 있는 권한을 가집니다.
- 전송해야 하는 데이터는 원본 및 대상 문서의 URL(즉, '얇은 ping') 뿐입니다.

There are no constraints on the syntax of the source and target documents. Discovery of the [[Webmention](https://www.w3.org/TR/social-web-protocols/#bib-Webmention)] endpoint (a script which can process incoming webmentions) is through a link relation (`rel="webmention"`), either in the HTTP `Link` header or HTML body of the target. This endpoint does not need to be on the same domain as the target, so webmention receiving can be delegated to a third party.

원본 및 대상 문서의 구문에는 제약이 없습니다. (수신 Webmention을 처리할 수 있는 스크립트인) [[Webmention](https://www.w3.org/TR/social-web-protocols/#bib-Webmention)] 엔드포인트의 검색은 대상의 HTTP `Link` 헤더 또는 HTML 본문에서 링크 관계(`rel="webmention"`)를 통해 이루어집니다. 이 엔드포인트는 대상과 동일한 도메인에 있을 필요가 없으므로 Webmention 수신을 타사에 위임할 수 있습니다.

Webmentions are verified by the server dereferencing the source and parsing it to check for the existence of the target URL. If the target URL isn't found, the webmention *MUST* be rejected.

Webmention은 서버에서 소스를 역참조하고 구문 분석하여 대상 URL이 있는지 확인합니다. 대상 URL이 없으면 *반드시* Webmention을 거부해야 합니다.

Webmention uses `x-www-form-urlencoded` for the source and target as parameters in an HTTP POST request. Beyond verification, it is not specified what the receiver should do upon receipt of a Webmention. What the webmention endpoint should return on a `GET` request is also left unspecified.

Webmention은 소스 및 대상에 대해 `x-www-form-urlencoded`를 HTTP POST 요청의 매개 변수로 사용합니다. Webmention 수신시 수신자가 취해야 할 조치는 검증 이외에 명시되어 있지 않습니다. `GET` 요청 시 Webmention 엔드포인트이 반환해야 하는 내용도 지정되지 않은 상태로 남아 있습니다.

#### 6.4.1 [업데이트와 삭제 (Updates and deletes)](#64-멘션-mentioning)

In practice, Webmention receivers tend to fetch and store the webmention source. It is often displayed, for example as a reply underneath the target blog post.

실제로 Webmention 수신자는 Webmention 소스를 가져오고 저장하는 경향이 있습니다. 예를 들어, 대상 블로그 게시물 아래에 회신으로 표시되는 경우가 많습니다.

If a Webmention is received and this is the first time this `source` and `target` combination has been seen by the receiver, this indicates a relationship between the `source` and `target` has been created. If the receiver has seen these values before, the receiver can fetch and parse the `source` to determine what has changed; either the content of the `source` has been updated (in which case the receiver can update local copies of the content, if it stored them in the first place), or the entire source has been deleted (expect a `410 Gone` response).

Webmention이 수신되고 수신자가 이 `source`와 `target` 조합을 처음 보는 경우, 이는 `source`와 `target` 간의 관계가 생성되었음을 나타냅니다. 수신자가 이전에 이러한 값을 본 적이 있는 경우, 수신자는 `source`를 가져와 구문 분석하여 무엇이 변경되었는지 확인할 수 있습니다. 즉, `source`의 내용이 업데이트된 경우(수신자가 처음부터 로컬 사본을 저장한 경우)거나 전체 원본이 삭제된 경우(`410 Gone` 예상) 입니다.

### 6.5 [전달 상호 운용성 (Delivery interop)](#6-전달-delivery)

This section describes how implementations of Webmention, ActivityPub and LDN may create bridging code in order to send and receive notifications from the others.

이 섹션에서는 Webmention, ActivityPub 및 LDN을 구현하여 다른 사용자로부터 알림을 보내고 받기 위해 브릿징 코드를 만드는 방법에 대해 설명합니다.

#### 6.5.1 [Webmention을 AS2 / ActivityPub로 (Webmention as AS2 / ActivityPub)](#65-전달-상호-운용성-delivery-interop)

A webmention may be represented as a persistent resource with the ActivityStreams 2.0 vocabulary. This could come in handy if a **Webmention sender** mentions a user known to be running an ActivityPub federated server, and wants a generic (ie. not ActivityPub specific) way of notifying about this. In this case, the sender can use an AS2 payload and deliver the notification per [6.5.3 Webmention to LDN](https://www.w3.org/TR/social-web-protocols/#wm-to-ldn).

Webmention은 ActivityStreams 2.0 어휘가 있는 일관적인 리소스로 나타낼 수 있습니다. 이는 Webmention 발신자가 ActivityPub 연합 서버를 실행 중인 것으로 알려진 사용자를 언급하고 일반적인(즉, ActivityPub 전용이 아닌 경우) 알림 방법을 원하는 경우 유용하게 사용할 수 있습니다. 이 경우 발신자는 AS2 페이로드를 사용하여 [6.5.3 Webmention에서 LDN으로](https://www.w3.org/TR/social-web-protocols/#wm-to-ldn) 전송할 수 있습니다.

>Example 1

>예시 1
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

수신자 또는 송신자는 두 문서 간의 관계 및 기타 관련 데이터로 이 표현을 보강시킬 수 있습니다. 수신자의 경우, 이는 검증 프로세스 중 소스를 구문 분석할 때 수집할 수 있습니다. 예를 들어:

>Example 2
>
>```json
>{
>- "name": "Hi Aaron, great post."
>- "name": "Aaron's first post."
>}
>```

>예시 2
>
>```json
>{
>  "@context": "https://www.w3.org/ns/activitystreams#",
>  "type": "Relationship",
>  "subject": {
>- "id": "https://waterpigs.example/post-by-barnaby",
>- "name": "안녕 Aaron, 굉장한 게시물이야."
>  },
>  "object": {
>- "id": "https://aaronpk.example/post-by-aaron",
>- "name": "Aaron의 첫 게시물."
>  },
>  "relationship": "inReplyTo"
>}
>```

#### 6.5.2 [LDN 에서 Webmention로 (LDN to Webmention)](#65-전달-상호-운용성-delivery-interop)

**Webmention receivers** wishing to also accept LDN `POST`s at their Webmention endpoint must:

**Webmention 수신자** 중 Webmention 엔드포인트에서 LDN `POST`를 수락하고자 하는 자는 다음을 반드시 수행해야 합니다:

- Advertise the webmention endpoint via `rel="http://www.w3.org/ns/ldp#inbox"` in addition to `rel="webmention"` (in the `Link` header, HTML body or JSON body of a target).
- Accept `POST` requests with the Content-Type `application/ld+json`. Expect the body of the request to be:

[//Comment]: # "BLANK"

- `rel="webmention"`(`Link` 헤더, HTML 본문 또는 대상의 JSON 본문) 외에 `rel="http://www.w3.org/ns/ldp#inbox"`을 통해 Webmention 엔드포인트을 알립니다.
- Content-Type `application/ld+json`에서 POST 요청을 수락합니다. 요청 본문은 다음과 같이 예상됩니다:

    >Example 3

    >예시 3
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

[//Comment]: # "BLANK"

- `source->@id `및 `target-@id` 값을 Webmention의 `source`와 `target` 으로 사용하고 검증을 진행합니다.
- `201 Created`를 반환하는 경우 *반드시* 게시된 요청의 내용을 검색할 수 있는 URL이 포함된 `Location` 헤더를 반환해야 합니다. `202 Accepted`의 경우는 아직은 괜찮습니다.
- 소스를 검증할 때 소스를 RDF로 요청/파싱할 수도 있습니다.

**LDN senders** wishing to send to Webmention endpoints basically just need to implement Webmention sending. The Webmention endpoint is at `rel="webmention"` (either in an HTTP `Link` header or HTML `<link>` element).

**LDN 발신자** 중 Webmention 엔드포인트로 보내려는 자는 기본적으로 Webmention 전송을 구현하기만 하면 됩니다. Webmention 엔드포인트는 `rel="webmention"`(HTTP `Link` 헤더 또는 HTML `<link>` 요소)에 있습니다.

Note that Webmention endpoints will only verify a received notification if the `source` is publicly retrievable and contains the URL of the `target`.

Webmention 엔드포인트는 `source`가 공개적으로 검색 가능하고 `target`의 URL을 포함하는 경우에만 수신된 알림을 확인합니다.

#### 6.5.3 [Webmention 에서 LDN로 (Webmention to LDN)](#65-전달-상호-운용성-delivery-interop)

**LDN receivers** wishing to also accept Webmentions to their Inbox *MUST*:

**LDN 수신자** 중 인박스에 Webmention을 수신하려는 자는 다음을 수행해야 합니다.

- Advertise the Inbox via `rel="webmention"` in addition to `rel="http://www.w3.org/ns/ldp#inbox"` (in the `Link` header, HTML body or JSON body of a target).
- Accept `POST` requests with a content type `application/x-www-form-urlencoded`. Convert these requests from:

[//Comment]: # "BLANK"

- (`Link` 헤더, HTML 본문 또는 대상의 JSON 본문의) `rel="http://www.w3.org/ns/ldp#inbox"` 외에 `rel="webmention"`을 통해 인박스를 알립니다.
- content type `application/x-www-form-urlencoded`가 있는 `POST` 요청을 수락합니다. 이러한 요청을 다음과 같이 변환합니다:

    >Example 4

    >예시 4
    >
    >```lang-none
    >source=https://waterpigs.example/post-by-barnaby&
    >target=https://aaronpk.example/post-by-aaron
    >```

    to:

    에서:

    >Example 5

    >예시 5
    >
    >```json
    >{
    >  "@context": "http://www.w3.org/ns/webmention#",
    >  "@id": "",
    >  "source": { "@id": "https://waterpigs.example/post-by-barnaby" },
    >  "target": { "@id": "https://aaronpk.example/post-by-aaron" }
    >}
    >```

[//Comment]: # "BLANK"

- and proceed per [[LDN](https://www.w3.org/TR/social-web-protocols/#bib-LDN)]; receivers *MAY* add other triples at their discretion.
- Receivers *MUST* return a 201 Created with a Location header or 202 Accepted.
- Receivers *MUST* verify the request by retrieving the source document and checking a link to the target document is present. If the Webmention is not verified, recievers *MUST NOT* keep it.

[//Comment]: # "BLANK"

- 그리고 [[LDN](https://www.w3.org/TR/social-web-protocols/#bib-LDN)]에 따라 진행하시길 바랍니다; 수신자는 임의로 다른 3배수를 추가 *할 수도* 있습니다.
- 수신자는 *반드시* 위치 헤더로 작성된 201 또는 수락된 202를 반환해야 합니다.
- 수신자는 *반드시* 원본 문서를 검색하고 대상 문서에 대한 링크가 있는지 확인하여 요청을 확인해야 합니다. Webmention이 확인되지 않은 경우 수신자가 Webmention을 *절대* 보관해서는 안 됩니다.

**Webmention senders** wishing to send to LDN Inboxes need to send a JSON-LD payload. Discover the Inbox endpoint through a relation of `http://www.w3.org/ns/ldp#inbox` between the `target` and the Inbox. A typical Webmention can be represented as JSON-LD per [this example](https://www.w3.org/TR/social-web-protocols/#wm-json), or as ActivityStreams 2.0 JSON per [this example](https://www.w3.org/TR/social-web-protocols/#wm-as2).

**Webmention 발신자** 중 LDN 인박스로 보내려는 자는 JSON-LD 페이로드를 보내야 합니다. `target`과 인박스 사이의 `http://www.w3.org/ns/ldp#inbox` 관계를 통해 인박스 엔드포인트을 검색합니다. 일반적인 Webmention은 [이 예시](https://www.w3.org/TR/social-web-protocols/#wm-json)에서는 JSON-LD로, 또는 [이 예시](https://www.w3.org/TR/social-web-protocols/#wm-as2)에서는 ActivityStreams 2.0 JSON으로 나타낼 수 있습니다.

>Note: Bridging services
>
>Look out for Webmention-ActivityPub bridges as services. These will provide endpoints to do the heavy lifting of the spec you don't want to implement yourself. You can use these endpoints as your Webmention or Inbox endpoint respectively. Brainstorming and implementations of such bridges can be found on the [Social Web Community Group](https://www.w3.org/wiki/SocialCG) and the [IndieWeb community](https://indieweb.org/bridge#ActivityPub).

>참고: 서비스 브릿징하기
>
>Webmention-ActivityPub 브릿지를 서비스로 제공하는걸 고려해보시길 바랍니다. 이렇게 하면 직접 구현하지 않으려는 규격의 무거운 부분들을 수행할 수 있는 엔드포인트를 제공할 수 있습니다. 이러한 엔드포인트를 각각 Webmention 또는 인박스 엔드포인트로 사용할 수 있습니다. 고안 및 이러한 브릿지의 구현은 [Social Web Community Group](https://www.w3.org/wiki/SocialCG)과 [IndieWeb community](https://indieweb.org/bridge#ActivityPub)에서 확인할 수 있습니다.

[맨 위로](#6-전달-delivery)
