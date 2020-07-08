[목차로 돌아가기](SocialWebProtocolsContents.md)

## 7. [프로필 (Profiles)](SocialWebProtocolsContents.md#목차-table-of-contents)

The subject of a profile document can be a person, persona, organisation, bot, location, or other. None of the specifications described here prescribe particular relationships between real-world entities and online profiles. That is, one person can have many profiles, and one profile may be controlled by many people. How/if/when multiple profiles are linked together is implementation specific, and not specified anywhere here.

프로필(profile) 문서의 주제는 개인(person), 인물(persona), 조직, 봇, 위치 또는 기타 일 수 있습니다. 여기에 설명된 규격 중 실제 개체와 온라인 프로필 간의 특정 관계를 규정하는 것은 없습니다. 즉, 한 사람이 여러 프로필을 가질 수 있고, 한 사람이 여러 프로필을 제어할 수 있습니다. 여러 프로필이 함께 연결되는 방법은 구현마다 다르며 이 문서에서는 기술하지 않습니다.

[//Comment]: # "persona를 'the characters in a play' 라는 번역을 따라 '인물'로 번역하였으나 확실하지 않기는 합니다."

Most specifications expect that profiles are identified by and retrieved from a URL, and that attributes of the subject of the profile are available from the URL. Ideally they also return a link to at least one stream of content associated with the profile (or embed the content directly), for example activities or blog posts.

대부분의 규격에서는 URL에 의해 프로필을 식별하고 검색하며, 해당 URL에서 프로필 대상의 속성을 사용할 수 있을 것으로 예상합니다. 또한 작업 또는 블로그 게시물과 같이 프로필과 관련된 하나 이상의 내용 스트림에 대한 링크를 반환하거나 직접 내용을 포함시키는 것이 좋습니다.

**ActivityPub** profiles are JSON-LD documents containing any appropriate ActivityStreams 2.0 properties, as well as links to various endpoints and collections (see [3.3.1 Special streams](https://www.w3.org/TR/social-web-protocols/#streams-special)).

**ActivityPub** 프로필은 적절한 ActivityStreams 2.0 속성과 다양한 엔드포인트 및 컬렉션에 대한 링크가 포함된 JSON-LD 문서입니다([3.3.1 특수 스트림](https://www.w3.org/TR/social-web-protocols/#streams-special) 참조).

**ActivityStreams 2.0** has various [Actor types](https://www.w3.org/TR/activitystreams-core/#actors), which may be used to represent individuals or groups, and also includes `Profile`.

**ActivityStreams 2.0** 에는 개인 또는 그룹을 나타내는 데 사용할 수 있는 다양한 유형의 [액터 타입](https://www.w3.org/TR/activitystreams-core/#actors)이 있으며 `Profile`도 포함됩니다.

**Micropub** has a notion of a profile page (URL) that represents a user, but does not specify the format of that page, except for the link to the Micropub endpoint and authorization endpoints for clients to discover.

**Micropub**에는 사용자를 나타내는 프로필 페이지 (URL) 개념이 있지만, 클라이언트가 검색할 Micropub 엔드포인트와 권한부여 엔드포인트에 대한 링크를 제외하고는 해당 페이지의 형식을 강제하지는 않습니다

**Webmention** does not specify any particular profile format, but in practice Webmention implementations typically publish and consume [[h-card](https://www.w3.org/TR/social-web-protocols/#bib-h-card)] profile information to display authors of webmention sources (see [examples in the Webmention spec](https://www.w3.org/TR/webmention/#webmention-verification-p-4)).

**Webmention** 은 특정한 프로필 형식만을 수용하지는 않지만, 실제 Webmention 구현에서는 일반적으로는 [[h-card](https://www.w3.org/TR/social-web-protocols/#bib-h-card)] 프로필 정보를 게시하고 사용하여 Webmention 소스 작성자를 표시합니다 ([Webmention 규격](https://www.w3.org/TR/webmention/#webmention-verification-p-4) 의 예시 참조).

### 7.1 [관계 (Relationships)](#7-프로필-profiles)

Semantics and representation of personal relationships are implementation specific. These specifications deal with relationships only when distribution of content is affected, for example when 'following' triggers a subscription request from one server to another. Lists of other relationships may be discoverable from a user profile, should be represented according to the ActivityStreams 2.0 syntax and may (and are likely to) use extension vocabularies as needed.

개개인 사이의 시맨틱과 관계에 대한 표현은 구현에 따라 다릅니다. 이러한 규격은 '팔로잉'으로 한 서버에서 다른 서버로 구독 요청을 트리거하는 경우처럼 콘텐츠 배포가 영향을 받는 경우의 관계만 다룹니다. 다른 관계 목록은 사용자 프로필에서 검색할 수 있으며 ActivityStreams 2.0 구문에 따라 표시되어야 하고 필요에 따라 확장 단어를 사용할 수도 있습니다.

- **ActivityPub**: When a server receives a `Follow` Activity in its `inbox`, the subject is added to a `Followers Collection`, which is discoverable from the subject's profile. Federated servers use this collection to deliver updates when new content is created by the owner of the collection.

[//Comment]: # "BLANK"

- **ActivityPub**: 서버가 `inbox`에서 `Follow` 액티비티를 수신하면 수신자는 제목 프로필에서 검색할 수 있는 `Followers Collection`에 추가됩니다. 연합 서버는 컬렉션 소유자가 새 콘텐츠를 만들 때 이 컬렉션을 통해 업데이트를 제공합니다.

### 7.2 [인증, 권한부여와 액세스 제어 (Authentication, authorization, and access control)](#7-프로필-profiles)

Authentication and authorization mechanisms were out of scope for the Social Web WG. Please follow the [Community Group](https://www.w3.org/wiki/SocialCG) for development in this space. Meanwhile, some of the WG specifications contain non-normative notes on the topic:

인증 및 인증 메커니즘은 Social Web WG가 다루는 범위를 벗어납니다. 이것과 관련된 개발을 보려면 [커뮤니티 그룹](https://www.w3.org/wiki/SocialCG)을 참조하시길 바랍니다. 한편, 일부 WG 규격에는 위와 같은 주제에 대한 비표준적인 참고사항들이 포함되어 있습니다:

- **ActivityPub**: Points to a Community Group best practices report in [B.1 Authentication and Authorization](https://www.w3.org/TR/activitypub/#authorization).
- **LDN**: Recommends that receivers employ some kind of verification mechanism which may be authentication in [3.3.3 Sender verification](https://www.w3.org/TR/ldn/#sender-verification), with additional security considerations in [5.6 Authenticated inboxes](https://www.w3.org/TR/ldn/#authenticated-inboxes).
- **Micropub**: Requires bearer tokens, and suggests IndieAuth in [5. Authentication and Authorization](https://www.w3.org/TR/micropub/#authentication-and-authorization).
- **Webmention**: Points to an extension for use with access controlled posts in [B.3 Private Webmention](https://www.w3.org/TR/webmention/#private-webmention).
- **WebSub**: Describes optional use of HMAC Signatures in [8.1 Authenticated Content Distribution](https://www.w3.org/TR/websub/#authenticated-content-distribution).

[//Comment]: # "BLANK"

- **ActivityPub**: [B.1 인증 및 권한부여](https://www.w3.org/TR/activitypub/#authorization)의 커뮤니티 그룹 모범 사례 보고서를 가리킵니다.
- **LDN**: 수신자에게 [3.3.3 전송자 확인](https://www.w3.org/TR/ldn/#sender-verification)에서 인증될 수 있는 일종의 확인 메커니즘을 사용하고, [5.6 인증받은 인박스](https://www.w3.org/TR/ldn/#authenticated-inboxes)에 기재된 추가적인 보안 고려사항을 적용할 것을 권장합니다.
- **Micropub**: [5. 인증 및 권한부여](https://www.w3.org/TR/micropub/#authentication-and-authorization)에서 운반 토큰(bearer tokens)이 필요한 IndieAuth를 제안합니다.
- **Webmention**: [B.3 비공개 Webmention](https://www.w3.org/TR/webmention/#private-webmention)에서 액세스 제어 게시물과 함께 사용할 수 있는 확장을 가리킵니다.
- **WebSub**: [8.1 인증된 컨텐츠 배포](https://www.w3.org/TR/websub/#authenticated-content-distribution)에서 HMAC 서명을 선택적으로 사용하는 방법에 대해 설명합니다.

[맨 위로](#7-프로필-profiles)
