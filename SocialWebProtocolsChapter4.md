[목차로 돌아가기](SocialWebProtocolsContents.md)

## 4. [게시 (Publishing)](SocialWebProtocolsContents.md#목차-table-of-contents)

Publishing in this context refers to modifying the outgoing feed associated with a particular profile. This incorporates creating new content, as well as updating or deleting existing content. Content generated through a client (such as a web form, mobile app, sensor, smart device) is created when it is sent to a server for processing, where it is typically stored and usually published (either publicly or to a restricted audience), in human- and/or machine-readable forms. Clients and servers may independently support creating, updating and deleting; there are no dependencies between them.

이 문단에서 '게시'한다는 것은 특정 프로필과 관련된 송신 피드를 수정하는 것을 의미합니다. 여기에는 새 콘텐츠 작성과 기존 콘텐츠 업데이트 또는 삭제 등이 포함됩니다. 클라이언트를 통해 생성된 콘텐츠(예: 웹 양식, 모바일 앱, 센서, 스마트 장치)는 일반적으로 저장되고 일반적으로 공개되는(공용 또는 제한된 청중이 사용 가능한) 서버로 전송될 때 작성됩니다. 클라이언트와 서버는 작성, 업데이트 및 삭제를 독립적으로 지원할 수 있습니다. 클라이언트와 서버 사이에는 종속성이 없습니다.

>Note: Other kinds of publishing
>
>While delivering notifications or responding to subscription requests may trigger creating (or updating or deleting) something on the receiving end, the intent is different. These cases are called out as side effects in subscription and delivery where appropriate.

>참고: 기타 게시 유형
>
>알림 전달 또는 구독 요청에 응답하면 수신 엔드포인트 에서는 무언가를 생성하거나 업데이트 또는 삭제하는 트리거가 발생할 수 있지만, 원래의 목적은 다릅니다. 이러한 사례는 적절한 경우 구독 및 배송 시 부작용이라고 불립니다.

For notes about authentication and authorization between clients and servers, see [7.2 Authentication, authorization, and access control](https://www.w3.org/TR/social-web-protocols/#auth)

클라이언트와 서버 간의 인증 및 권한 부여에 대한 참고사항은 [7.2 인증, 권한 부여 및 액세스 제어](https://www.w3.org/TR/social-web-protocols/#auth)를 참조하시기 바랍니다.

The two specifications recommended by the Social Web Working Group for publishing are [[Activitypub](https://www.w3.org/TR/social-web-protocols/#bib-Activitypub)] and [[Micropub](https://www.w3.org/TR/social-web-protocols/#bib-Micropub)]. They use similar high level mechanisms, but differ in requirements around both the vocabularies and content types of data.

Social Web Working Group에서 게시용으로 권장하는 두 가지 규격은 [[Activitypub](https://www.w3.org/TR/social-web-protocols/#bib-Activitypub)]와 [[Micropub](https://www.w3.org/TR/social-web-protocols/#bib-Micropub)]입니다. 이들은 서로 유사한 고급 메커니즘을 사용하지만, 데이터의 어휘 및 컨텐츠 타입 두가지 모두에 대한 요구 사항이 다릅니다.

ActivityPub contains a client-to-server API for creating ActivityStreams 2.0 objects and activities, and specifies additional responsibilities for clients around addressing objects, and for servers around the side-effects of certain types of objects.

ActivityPub에는 ActivityStreams 2.0 객체 및 액티비티를 생성하기 위한 클라이언트 간 API가 포함되어 있으며, 객체 발신과 관련된 클라이언트의 추가적인 책임 및 특정 객체 유형의 부작용에 대한 서버에 대한 추가적인 책임을 명시합니다.

[//Comment]: # "Addressing을 발신으로 번역했습니다."

Micropub provides a basic client-to-server API for creating blog-post-type content and is intended as a quickstart for content creation, on top of which more complex (but optional) actions can be layered. Micropub also provides a media endpoint for uploading files.

Micropub는 블로그 포스트 유형의 콘텐츠를 만들 수 있는 기본 클라이언트-서버 API를 제공하며, 콘텐츠 생성의 빠른 시작과 더불어 (선택 사항인)더 복잡한 작업을 계층화할 수 있습니다. 또한 Micropub는 파일 업로드를 위한 미디어 엔드포인트을 제공합니다.

>Note: REST
>
>Neither ActivityPub nor Micropub define APIs for publishing based on HTTP verbs. If you're looking for something more RESTful, you may like the Linked Data Platform [[LDP](https://www.w3.org/TR/social-web-protocols/#bib-LDP)].

>참고: REST
>
>ActivityPub와 Micropub 모두 HTTP 동사를 기준으로는 게시용 API를 정의하지 않습니다. 좀 더 RESTFul한것이 필요한 경우 Linked Data Platform[[LDP](https://www.w3.org/TR/social-web-protocols/#bib-LDP)] 를 참조하시길 바랍니다.

### 4.1 [생성 (Creating)](#4-게시-publishing)

The publishing endpoint of **[[Activitypub](https://www.w3.org/TR/social-web-protocols/#bib-Activitypub)]** is the `outbox`. Clients are assumed to have the URL of a (ideally authenticated) profile as a starting point, and discover the value of the `https://www.w3.org/ns/activitystreams#outbox` property found at the profile URL (which should be available as JSON). The client then makes an HTTP POST request with an ActivityStreams 2.0 activity or object as a JSON payload with a content type of `application/ld+json; profile="https://www.w3.org/ns/activitystreams"`. The URL of the created resource is generated at the discretion of the server, and returned in the `Location` HTTP header. This is an appropriate protocol to use when:

**[[Activitypub](https://www.w3.org/TR/social-web-protocols/#bib-Activitypub)]**의 게시 엔드포인트는 아웃박스입니다. 클라이언트는 (인증된) 프로필의 URL을 시작점으로 간주하고 (JSON으로 제공되어야 하는)프로필 URL에서 찾아낸 `https://www.w3.org/ns/activitystreams#outbox` 속성의 값을 검색합니다. 그런 다음 클라이언트는 `application/ld+json; profile="https://www.w3.org/ns/activitystreams"`의 내용 유형을 가진 JSON 페이로드로 ActivityStreams 2.0 액티비티 또는 객체가 포함된 HTTP POST 요청을 합니다. 생성된 리소스의 URL은 서버의 재량에 따라 생성되고 `Location` HTTP 헤더에 반환됩니다. 이 프로토콜은 다음과 같은 경우에 적절하 사용할 수 있는 프로토콜입니다:

- You want to send/receive a JSON or JSON-LD payload.
- Your data is described with [[activitystreams-core](https://www.w3.org/TR/social-web-protocols/#bib-activitystreams-core)] and [[activitystreams-vocabulary](https://www.w3.org/TR/social-web-protocols/#bib-activitystreams-vocabulary)] (optionally extensible via JSON-LD).
- You want servers to carry out a known set of actions upon content creation.

[//Comment]: # "BLANK"

- 당신은 JSON 또는 JSON-LD 페이로드를 전송/수신하려고 합니다.
- 당신의 데이터가 [[activitystreams-core](https://www.w3.org/TR/social-web-protocols/#bib-activitystreams-core)] 와 (JSON-LD를 통해 선택적으로 확장 가능한) [[activitystreams-vocabulary](https://www.w3.org/TR/social-web-protocols/#bib-activitystreams-vocabulary)]로 정의되어 있습니다.
- 당신은 서버가 컨텐츠 작성 시 알려진 작업 집합을 수행했으면 좋겠습니다.

Side-effects of creating content with ActivityPub are for the most part adding things to various different collections collections (likes, follows, etc); but also include requirements about blocking users, and a hook to enable federated servers.

ActivityPub로 컨텐츠를 만들 때 발생하는 부작용은 대부분 다양한 컬렉션(좋아요, 팔로우 등)에 항목을 추가하는 것이지만, 사용자 차단에 대한 요구 사항과 연합 서버를 활성화하기 위한 후크도 포함합니다.

The publishing endpoint for **[[Micropub](https://www.w3.org/TR/social-web-protocols/#bib-Micropub)]** is the `micropub` endpoint. Clients discover this from a profile URL via a `rel="micropub"` link (in an HTTP `Link` header, or an HTML `<link>` element). Clients make a `x-www-form-urlencoded` POST request containing the key-value pairs for the attributes of the object being created. The URL of the created resource is generated at the discretion of the server, and returned in the `Location` HTTP header. Clients and servers must support attributes from the Microformats2 [[h-entry](https://www.w3.org/TR/social-web-protocols/#bib-h-entry)] vocabulary. Micropub also defines four reserved attributes (`access_token`, `h`, `action` and `url`) as well as reserves any attribute prefixed with `mp-`; these are used as commands to the server. Any additional key names sent outside of these vocabularies may be ignored by the server.

 **[[Micropub](https://www.w3.org/TR/social-web-protocols/#bib-Micropub)]**의 게시 엔드포인트는 `micropub` 엔드포인트입니다. 클라이언트는 (HTTP `Link` 헤더 또는 HTML `<link>` 요소 안의) `rel="micropub"` 링크를 통해 프로필 URL에서 이를 검색합니다. 클라이언트는 생성되는 개체의 특성에 대한 키 값 쌍을 포함하는 `x-www-form-urlencoded` POST 요청을 만듭니다. 생성된 리소스의 URL은 서버의 재량에 따라 생성되고 `Location` HTTP 헤더에 반환됩니다. 클라이언트와 서버는 Microformats2 [[h-entry](https://www.w3.org/TR/social-web-protocols/#bib-h-entry)] 어휘의 속성들을 지원해야 합니다. Micropub는 또한 네 가지 예약된 속성(`access_token`, `h`, `action` 및 `url`)을 정의하고 `mp-` 접두사 앞에 있는 모든 속성을 예약합니다; 이러한 속성들은 서버에 대한 명령으로 사용됩니다. 서버가 이러한 어휘 외에 발송된 추가 키값 들은 무시할 수 있습니다.

Micropub requests may alternatively be sent as a JSON payload, the syntax of which is derived from [[microformats2-parsing](https://www.w3.org/TR/social-web-protocols/#bib-microformats2-parsing)].

Micropub 요청은 JSON 페이로드로 대신 전송될 수 있으며, 이 페이로드의 구문은 [[microformats2-parsing](https://www.w3.org/TR/social-web-protocols/#bib-microformats2-parsing)]에서 파생됩니다.

This is an appropriate protocol to use when:

이 프로토콜은 다음과 같은 경우에 적절히 사용할 수 있는 프로토콜입니다:

- You want to send/receive a form-encoded or JSON payload.
- Your data is described with the [[h-entry](https://www.w3.org/TR/social-web-protocols/#bib-h-entry)] syntax and vocabulary.
- You can rely on out-of-band agreements between clients and servers for vocabulary extensibility.

[//Comment]: # "BLANK"

- 당신은 form-encoded 된 정보 또는 JSON 페이로드를 전송/수신하려고 합니다.
- 당신의 데이터는 [[h-entry](https://www.w3.org/TR/social-web-protocols/#bib-h-entry)] 구문과 어휘로 설명됩니다.
- 당신은 어휘 확장을 위해 클라이언트와 서버 간의 대역-외-계약에 의존할 수 있습니다.

[//Comment]: # "form-encoded를 'x-www-form-urlencoded' 에서의 form-encoded로 해석하고 원문 그대로 적었습니다"

### 4.2 [업데이트 (Updating)](#4-게시-publishing)

Content is updated when a client sends changes to attributes (additions, removals, replacements) to an existing object.

클라이언트가 속성(추가, 제거, 교체)에 대한 변경 사항을 기존 객체에 보낼 때 내용이 업데이트됩니다.

**[[Activitypub](https://www.w3.org/TR/social-web-protocols/#bib-Activitypub)]** clients send an HTTP `POST` request to the `outbox` containing an ActivityStreams 2.0 `Update` activity. The `object` of the activity is an existing object, including its `id`, and the fields to update should be nested. If a partial representation of an object is sent, omitted fields are _not_ deleted by the server. In order to delete specific fields, the client can assign them a `null` value.

**[[Activitypub](https://www.w3.org/TR/social-web-protocols/#bib-Activitypub)]** 클라이언트는 ActivityStreams 2.0 `Update` 활동이 포함된 HTTP `POST` 요청을 `outbox`로 보냅니다. 액티비티의 `object`는 `id`를 포함한 기존의 객체이며 업데이트할 필드는 중첩되어야 합니다. 객체의 부분 표현을 발송할 경우, 생략된 필드는 서버에서 삭제되지 _않습니다_. 특정 필드를 삭제하려면 클라이언트가 `null` 값을 할당할 수 있습니다.

In the case of ActivityPub federated servers, updates should be propagated to the `inbox`es of recipients of the original objects. However, when a federated server passes an `Update` activity to another server's `inbox`, the recipient must assume this is the _complete_ object to be replaced; partial updates are not performed server-to-server.

ActivityPub 연합 서버의 경우 업데이트를 원래 객체의 수신자 `inbox` 로 전파해야 합니다. 그러나 연합 서버가 `Update` 작업을 다른 서버의 `inbox`로 전달하면 수신인은 이것이 교체할 _완전한_ 객체라고 가정해야 합니다; 부분 업데이트는 서버-서버 간에 수행되지 않습니다.

An `Undo` with the `object` of the previous `Update` can be used to revert changes.

이전 `Update`의 `object`와 함께 `Undo`를 사용하여 변경 내용을 되돌릴 수 있습니다.

**[[Micropub](https://www.w3.org/TR/social-web-protocols/#bib-Micropub)]** clients perform updates as JSON POST requests, using the `"action": "update"` directive, as well as a `replace`, `add` or `delete` property containing the updates to make, to the Micropub endpoint. `replace` replaces all values of the specified property; if the property does not exist already, it is created. `add` adds new values to the specified property without changing the existing ones; if the property does not exist already, it is created. `delete` removes the specified property; you can also remove properties by value by specifying the value.

**[[Micropub](https://www.w3.org/TR/social-web-protocols/#bib-Micropub)]** 클라이언트는 `"action": "update"` 지시어를 사용하여 JSON POST 요청으로 업데이트를 수행할 뿐만 아니라 업데이트할 속성을 Micropub 엔드포인트에서 `replace`, `add` 또는 `delete`합니다.  `replace`는 지정된 속성의 모든 값을 대체합니다. 속성이 아직 존재하지 않는 경우에는 해당 속성이 생성됩니다. `add`는 기존 값을 변경하지 않고 지정된 속성에 새 값을 추가합니다. 속성이 아직 존재하지 않는 경우 해당 값이 생성됩니다. `delete`는 지정된 속성을 제거합니다. 값을 지정하여 값을 기준으로 속성을 제거할 수도 있습니다.

If a server also implements [[Webmention](https://www.w3.org/TR/social-web-protocols/#bib-Webmention)] it should propagate the updates to anyone who received Webmentions for the original.

서버가 또한 [[Webmention](https://www.w3.org/TR/social-web-protocols/#bib-Webmention)]을 구현하는 경우, 원본 Webmention을 수신한 모든 사용자에게 업데이트를 전파해야 합니다.

If a server also implements [[WebSub](https://www.w3.org/TR/social-web-protocols/#bib-WebSub)], and the updated resource is part of a `topic`, the server should notify the hub of an update to the topic URL.

서버가 [[WebSub](https://www.w3.org/TR/social-web-protocols/#bib-WebSub)]도 구현하고 업데이트된 리소스가 `topic`의 일부인 경우, 서버는 허브에 항목(topic) URL에 대한 업데이트를 통지해야 합니다.

### 4.3 [삭제 (Deleting)](#4-게시-publishing)

Content is deleted when a client sends a request to delete an existing object.

클라이언트가 기존 개체 삭제 요청을 보낼 때 내용이 삭제됩니다.

**[[Activitypub](https://www.w3.org/TR/social-web-protocols/#bib-Activitypub)]** clients delete an object by sending an HTTP POST request containing an ActivityStreams 2.0 `Delete` activity to the `outbox` of the authenticated user. Servers must either _replace_ the `object` of this activity with a tombstone and return a `410 Gone` status code, or return a `404 Not Found`, from its URL.

**[[Activitypub](https://www.w3.org/TR/social-web-protocols/#bib-Activitypub)]** 클라이언트는 ActivityStreams 2.0 `Delete` 액티비티를 포함하는 HTTP POST 요청을 인증된 사용자의 `outbox`로 전송하여 개체를 삭제합니다. 서버는 이 액티비티의 `object`를 묘비(tombstone)로 _교체_ 하고 `410 Gone` 상태 코드를 반환하거나 URL에서 `404 Not Found` 상태 코드를 반환해야 합니다.

An `Undo` with the `object` of the previous `Delete` may be used to restore the object.

이전 `Delete`의 객체로 `Undo`를 사용하여 `object`를 복원할 수 있습니다.

**[[Micropub](https://www.w3.org/TR/social-web-protocols/#bib-Micropub)]** delete requests are two key-value pairs, JSON: `"action": "delete"` and `"url": url-to-be-deleted`, sent to the Micropub endpoint. Posts may be resotred with `"action": "undelete"`.

**[[Micropub](https://www.w3.org/TR/social-web-protocols/#bib-Micropub)]** 삭제 요청은 JSON: `"action": "delete"` 및 `"url": url-to-be-deleted` 두 개의 키-값 쌍이며 Micropub 엔드포인트으로 전송됩니다. 게시물들은 `"action": "undelete"`으로 다시 복원될 수 있습니다.

As with [updating](https://www.w3.org/TR/social-web-protocols/#updating), servers implementing ActivityPub federation, Webmention or WebSub should propagate deletes accordingly.

[업데이트](https://www.w3.org/TR/social-web-protocols/#updating)와 마찬가지로 ActivityPub 연합, Webmention 또는 WebSub를 구현하는 서버는 그에 따라 삭제 내용을 전파해야 합니다.

[맨 위로](#4-게시-publishing)
