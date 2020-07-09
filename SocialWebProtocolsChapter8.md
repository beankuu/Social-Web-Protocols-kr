[목차로 돌아가기](SocialWebProtocolsContents.md)

## 8. 관련된 규격들 (Related specifcations)

Other specifications worth mentioning in relation to the output of the Social Web Working Group are outlined here.

Social Web Working Group의 결과물과 관련된, 언급할 가치가 있는 다른 규격들은 다음과 같습니다.

Social Web Working Group Notes:

Social Web Working Group 참고사항:

- **[[IndieAuth](SocialWebProtocolsChapterB.md#indieauth)]**: is an identity layer on top of OAuth 2, and the expected auth mechanism for Micropub clients.
- **[[JF2](SocialWebProtocolsChapterB.md#jf2)]**: is an alternative JSON syntax for social content, derived from[[microformats2](SocialWebProtocolsChapterB.md#microformats2)]. It includes individual objects and feeds. If you don't like ActivityStreams 2.0, you might like this instead. At the time of writing it is not referenced by any other Social Web Working Group specifications.
- **[[post-type-discovery](SocialWebProtocolsChapterB.md#post-type-discovery)]**: specifies an algorithm for determining the type of post by its properties. This may help with bridging between content marked up with [[microformats2](SocialWebProtocolsChapterB.md#microformats2)], and explicitly typed vocabularies like ActivityStreams 2.0.

[//Comment]: # "BLANK"

- **[[IndieAuth](SocialWebProtocolsChapterB.md#indieauth)]**: 는 OAuth 2 위에 있는 신원 계층(identity layer)이며 Microub 클라이언트가 사용하리라 예상되는 인증 메커니즘입니다.
- **[[JF2](SocialWebProtocolsChapterB.md#jf2)]**:는 [[microformats2](SocialWebProtocolsChapterB.md#microformats2)]에서 파생된 소셜 콘텐츠의 대체 JSON 구문입니다. 이는 개별 객체와 피드를 포함합니다. ActivityStreams 2.0 이 마음에 들지 않으면 대신 이 옵션을 사용할 수도 있습니다. 작성 당시 이 문서는 다른 소셜 웹 작업 그룹 규격에서 참조하지 않았습니다.
- **[[post-type-properties](SocialWebProtocolsChapterB.md#post-type-discovery)]**: 속성을 기준으로 게시 유형을 결정하는 알고리즘을 지정합니다. 이는 [[microformats2](SocialWebProtocolsChapterB.md#microformats2)]로 표시된 내용과 ActivityStreams 2.0 과 같이 명시적으로 입력된 어휘 사이에 브릿징하는 데 도움이 될 수도 있습니다.

External:

외부:

- **[[LDP](SocialWebProtocolsChapterB.md#ldp)]**: was an input to the Social Web Working Group charter. `Container`s on LDP servers can be used directly as LDN receivers, if you happen to have one lying around. The Web Annotation Protocol is also based on LDP.
- **[[microformats2](SocialWebProtocolsChapterB.md#microformats2)]**: is a way to mark up structured information in HTML. Micropub expects the microformats2 vocabulary, and Webmention receiver implementations often look for microformats2 markup to fetch more information about a source.
- **[[annotation-protocol](SocialWebProtocolsChapterB.md#annotation-protocol)]**: uses ActivityStreams 2.0 Collections and Paging to model sets of annotations. Annotations themselves use the [[annotation-vocab](SocialWebProtocolsChapterB.md#annotation-vocab)].

[//Comment]: # "BLANK"

- **[[LDP](SocialWebProtocolsChapterB.md#ldp)]**: 는 Social Web Working Group 헌장을 작성하는데 사용되었습니다. LDP 서버의 `Container`는 가지고 있는 경우 LDN 수신기로 직접 사용할 수 있습니다. Web Annotation Protocol도 LDP를 기반으로 합니다.
- **[[microformats2](SocialWebProtocolsChapterB.md#microformats2)]**: 는 HTML로 구조화된 정보를 표시하는 방법입니다. Micropub는 microformats2 어휘를 사용하는것으로 간주되며, Webmention 수신기 구현은 종종 소스에 대한 더 많은 정보를 가져오기 위해 microformats2 마크업을 찾아봅니다.
- **[[annotation-protocol](SocialWebProtocolsChapterB.md#annotation-protocol)]**: 는 ActivityStreams 2.0 수집 및 페이징을 사용하여 주석 집합을 모델링합니다. 주석 자체는 [[annotation-vocab](SocialWebProtocolsChapterB.md#annotation-vocab)]을 사용합니다.

Development of related specifications is ongoing in various communities, notably the [Social Web Community Group](https://www.w3.org/wiki/SocialCG) and the [IndieWeb](https://indieweb.org/) community.

[Social Web Community Group](https://www.w3.org/wiki/SocialCG)과 [IndieWeb](https://indieweb.org/) 등 다양한 커뮤니티에서 관련 규격의 개발이 진행 중입니다.

[맨 위로](#8-관련된-규격들-related-specifcations)
