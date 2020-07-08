[목차로 돌아가기](SocialWebProtocolsContents.md)

## A. [변경사항 (Change Log)](SocialWebProtocolsContents.md#목차-table-of-contents)

### A.1 [2017년 5월 4일 WD에서 이 버전으로의 변경사항 (Changes from 4 May 2017 WD to this version)](#a-변경사항-change-log)

- Editorial updates throughout.
- Update all spec functionality which had fallen behind (mostly Micropub).
- Add requirements definitions to clarify the sections each spec is listed under, and their relation to charter deliverables.
- Clarify relevence of Federation Protocols to Social API parts (ie. updates triggering new notifications etc).
- Elaborate on Updates and Deletes for AP and Webmention.
- Profiles now describes each spec's use or expectations of profiles.
- Auth section now links to relevent parts of each individual spec.
- Add a section for related specs.

[//Comment]: # "BLANK"

- 전체적으로 편집을 개선했습니다.
- 뒤처진 모든(대부분 Micropub) 규격의 기능을 업데이트 했습니다.
- 요구사항 정의를 추가하여 각 규격이 규격의 하단에 열거된 섹션 및 헌장 결과물과의 관계를 명확히 했습니다.
- Federation Protocols와 Social API 부분(예: 새로운 알림을 트리거하는 업데이트 등)의 관련성을 명확히 했습니다.
- AP와 Webmention에 대한 업데이트 및 삭제에 대해 더욱 자세하게 풀어썼습니다.
- 프로필은 이제 각 규격의 프로필 사용 또는 예상에 대해 설명합니다.
- Auth 섹션은 이제 각 규격의 개별적인 관련된 부분들과 연결됩니다.
- 관련된 규격들 섹션을 추가했습니다.

### A.2 [2016년 11월 16일 WD에서 이 버전으로의 변경사항 (Changes from 16 November 2016 WD to this version)](#a-변경사항-change-log)

- Update document status of progressing specs.
- s/PubSub/WebSub/
- Add list of relationships between specific specs to Overview.
- Update AP streams info.
- Bring contents of Reading up to date.
- Remove references to external specs that aren't explicitly mentioned in a SWWG spec.
- Capture Create/Update/Delete under Publish header.
- Clean up text in Publish.
- Update Delivery for each spec and make section headings based on function rather than spec names.
- Add WebSub detail for Subscription.

[//Comment]: # "BLANK"

- 진행 규격에 대한 문서 상태를 업데이트 했습니다.
- s/PubSub/WebSub/
- 특정 규격들 간의 관계 목록을 개요(Overview) 에 추가했습니다.
- AP 스트림 정보를 업데이트했습니다.
- Reading의 내용을 최신 상태로 가져왔습니다.
- SWWG 규격에 명시적으로 언급되지 않은 외부 규격에 대한 참조를 제거했습니다.
- 게시(Publish) 헤더에서 생성/업데이트/삭제를 캡처했습니다.
- 게시(Publish)에서 텍스트를 정리했습니다.
- 각 규격에 대해 배달을 업데이트하고 규격 이름이 아닌 기능에 따라 섹션 제목을 작성했습니다.
- 구독에 대한 WebSub 세부사항을 추가했습니다.

### A.3 [2016년 11월 1일 WD에서 이 버전으로의 변경사항 (Changes from 1 November 2016 WD to this version)](#a-변경사항-change-log)

- Update document status of recently published drafts.

[//Comment]: # "BLANK"

- 최근에 게시된 초안의 문서 상태를 업데이트했습니다.

### A.4 [2016년 10월 12일 WD에서 이 버전으로의 변경사항 (Changes from 12 October 2016 WD to this version)](#a-변경사항-change-log)

- Updated WebSub since it was published as FPWD.

[//Comment]: # "BLANK"

- WebSub가 FPWD로 게시된 이후 업데이트 했습니다.

### A.5 [2016년 8월 23일 버전에서 2016년 10월 12일 버전으로의 변경사항 (Changes from 23 August to 12 October 2016)](#a-변경사항-change-log)

- Added targeting and discovery section, including "backoff" strategy advice.

[//Comment]: # "BLANK"

- "백오프(backoff)" 전략 조언을 포함하여 타겟팅 및 검색 섹션이 추가했습니다.

### A.6 [2016년 6월 3일 버전에서 2016년 8월 23일 버전으로의 변경사항 (Changes from 3 June to 23 August 2016)](#a-변경사항-change-log)

- Add new WG drafts as they were published by the group: JF2, PTD, LDN, PuSH.
- Update the publication statuses of existing WG drafts as they advanced.
- Describe LDN in Delivery and Reading.
- Describe PuSH in Subscribing and Delivery.
- Delivery interop:
  - how Webmention senders/receivers and LDN senders/receivers may implement a bridge.
  - how a Webmention could be represented as an AS2 Relationship.
- Refactor Subscribing and Reading to prioritise WG specs and clarify relations between them.
- Editorial improvements to introductory and overview text.

[//Comment]: # "BLANK"

- JF2, PTD, LDN, PuSH 그룹에 의해 게시된 새 WG 초안을 추가했습니다.
- 기존 WG 초안이 진행되어서 등록 상태를 업데이트했습니다.
- 배송 및 판독(Delivery and Reading)에서 LDN에 대해 설명했습니다.
- 구독 및 배달(Subscribing and Delivery)에서 PuSH에 대해 설명했습니다.
- 배달 상호 운용성은 다음과 같습니다:
  - Webmention 송신자/수신자 및 LDN 송신자/수신자가 브릿지를 구현하는 방법입니다.
  - Webmention을 AS2 관계로 표현하는 방법입니다.
- 구독 및 읽기(Refactor Subscripting and Reading)를 리팩터링하여 WG 규격의 우선순위를 정하고 이들 사이의 관계를 명확히 헀습니다.
- 소개 및 개요(introductory and overview) 텍스트에 대해 편집을 개선했습니다.

[맨 위로](#a-변경사항-change-log)
