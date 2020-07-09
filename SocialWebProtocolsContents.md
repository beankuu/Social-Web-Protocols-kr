[README로 돌아가기](README.md)

## 목차 (Table of Contents)

0\. [소셜 웹 프로토콜 (Social Web Protocols)](SocialWebProtocolsIntro.md)

- [요약 (Abstract)](SocialWebProtocolsIntro.md#요약-abstract)
- [이 문서의 상태 (Status of This Document)](SocialWebProtocolsIntro.md#요약-abstract)

1\. [서문 (Introduction)](SocialWebProtocolsChapter1.md#1-서문-introduction)

2\. [개요 (Overview)](SocialWebProtocolsChapter2.md#2-개요-overview)

- 2.1 [컨텐츠 (Contents)](SocialWebProtocolsChapter2.md#21-컨텐츠-contents)
- 2.2 [정의 (Definitions)](SocialWebProtocolsChapter2.md#22-정의-definitions)
- 2.3 [규격 (Specifications)](SocialWebProtocolsChapter2.md#23-규격-specifications)
  - 2.3.1 [요구사항 (Requirements)](SocialWebProtocolsChapter2.md#231-요구사항-requirements)
  - 2.3.2 [이 규격들은 서로 어떤 관계가 있을까요? (How do these specifications relate to each other?)](SocialWebProtocolsChapter2.md#232-이-규격들은-서로-어떤-관계가-있을까요-how-do-these-specifications-relate-to-each-other)

3\. [읽기 (Reading)](SocialWebProtocolsChapter3.md#3-읽기-reading)

- 3.1 [컨텐츠 표현 (Content representation)](SocialWebProtocolsChapter3.md#31-컨텐츠-표현-content-representation)
  - 3.1.1 [다른 방법으로 컨텐츠 표현 (Other ways of representing content)](SocialWebProtocolsChapter3.md#311-다른-방법으로-컨텐츠-표현-other-ways-of-representing-content)
- 3.2 [객체 (Objects)](SocialWebProtocolsChapter3.md#32-객체-objects)
- 3.3 [컬렉션 (Collections)](SocialWebProtocolsChapter3.md#33-컬렉션-collections)
  - 3.3.1 [특별 스트림 (Special streams)](SocialWebProtocolsChapter3.md#331-특별-스트림-special-streams)
  - 3.3.2 [인박스 (Inboxes)](SocialWebProtocolsChapter3.md#332-인박스-inboxes)

4\. [게시 (Publishing)](SocialWebProtocolsChapter4.md#4-게시-publishing)

- 4.1 [생성 (Creating)](SocialWebProtocolsChapter4.md#41-생성-creating)
- 4.2 [업데이트 (Updating)](SocialWebProtocolsChapter4.md#42-업데이트-updating)
- 4.3 [삭제 (Deleting)](SocialWebProtocolsChapter4.md#43-삭제-deleting)

5\. [구독 (Subscribing)](SocialWebProtocolsChapter5.md#5-구독-subscribing)

- 5.1 [`as:Follow`를 사용하여 구독 (Subscribing with `as:Follow`)](SocialWebProtocolsChapter5.md#51-asfollow를-사용하여-구독-subscribing-with-asfollow)
- 5.2 [hub를 사용하여 구독 (Subscribing with a hub)](SocialWebProtocolsChapter5.md#52-hub를-사용하여-구독-subscribing-with-a-hub)

6\. [전달 (Delivery)](SocialWebProtocolsChapter6.md#6-전달-delivery)

- 6.1 [타겟팅과 발견 (Targeting and discovery)](SocialWebProtocolsChapter6.md#61-타겟팅과-발견-targeting-and-discovery)
- 6.2 [일반적인 알림 (Generic notifications)](SocialWebProtocolsChapter6.md#62-일반적인-알림-generic-notifications)
- 6.3 [액티비티 알림 (Activity notifications)](SocialWebProtocolsChapter6.md#63-액티비티-알림-activity-notifications)
- 6.4 [멘션 (Mentioning)](SocialWebProtocolsChapter6.md#64-멘션-mentioning)
  - 6.4.1 [업데이트와 삭제 (Updates and deletes)](SocialWebProtocolsChapter6.md#641-업데이트와-삭제-updates-and-deletes)
- 6.5 [전달 상호 운용성 (Delivery interop)](SocialWebProtocolsChapter6.md#65-전달-상호-운용성-delivery-interop)
  - 6.5.1 [Webmention을 AS2 / ActivityPub로 (Webmention as AS2 / ActivityPub)](SocialWebProtocolsChapter6.md#651-webmention을-as2--activitypub로-webmention-as-as2--activitypub)
  - 6.5.2 [LDN 에서 Webmention로 (LDN to Webmention)](SocialWebProtocolsChapter6.md#652-ldn-에서-webmention로-ldn-to-webmention)
  - 6.5.3 [Webmention 에서 LDN로 (Webmention to LDN)](SocialWebProtocolsChapter6.md#653-webmention-에서-ldn로-webmention-to-ldn)

7\. [프로필 (Profiles)](SocialWebProtocolsChapter7.md#7-프로필-profiles)

- 7.1 [관계 (Relationships)](SocialWebProtocolsChapter7.md#71-관계-relationships))
- 7.2 [인증, 권한부여와 액세스 제어 (Authentication, authorization, and access control)](SocialWebProtocolsChapter7.md#72-인증-권한부여와-액세스-제어-authentication-authorization-and-access-control)

8\. [관련된 규격들 (Related specifcations)](SocialWebProtocolsChapter8.md#8-관련된-규격들-related-specifcations)

A\. [변경사항 (Change Log)](SocialWebProtocolsChapterA.md#a-변경사항-change-log)

- A.1 [2017년 5월 4일 WD에서 이 버전으로의 변경사항 (Changes from 4 May 2017 WD to this version)](SocialWebProtocolsChapterA.md#a1-2017년-5월-4일-wd에서-이-버전으로의-변경사항-changes-from-4-may-2017-wd-to-this-version))
- A.2 [2016년 11월 16일 WD에서 이 버전으로의 변경사항 (Changes from 16 November 2016 WD to this version)](SocialWebProtocolsChapterA.md#a2-2016년-11월-16일-wd에서-이-버전으로의-변경사항-changes-from-16-november-2016-wd-to-this-version)
- A.3 [2016년 11월 1일 WD에서 이 버전으로의 변경사항 (Changes from 1 November 2016 WD to this version)](SocialWebProtocolsChapterA.md#a3-2016년-11월-1일-wd에서-이-버전으로의-변경사항-changes-from-1-november-2016-wd-to-this-version)
- A.4 [2016년 10월 12일 WD에서 이 버전으로의 변경사항 (Changes from 12 October 2016 WD to this version)](SocialWebProtocolsChapterA.md#a4-2016년-10월-12일-wd에서-이-버전으로의-변경사항-changes-from-12-october-2016-wd-to-this-version)
- A.5 [2016년 8월 23일 버전에서 2016년 10월 12일 버전으로의 변경사항 (Changes from 23 August to 12 October 2016)](SocialWebProtocolsChapterA.md#a5-2016년-8월-23일-버전에서-2016년-10월-12일-버전으로의-변경사항-changes-from-23-august-to-12-october-2016)
- A.6 [2016년 6월 3일 버전에서 2016년 8월 23일 버전으로의 변경사항 (Changes from 3 June to 23 August 2016)](SocialWebProtocolsChapterA.md#a6-2016년-6월-3일-버전에서-2016년-8월-23일-버전으로의-변경사항-changes-from-3-june-to-23-august-2016))

B\. [참고 문헌 (References)](SocialWebProtocolsChapterB.md#b-참고-문헌-references)

- B.1 [정보 참고 문헌 (Informative references)](SocialWebProtocolsChapterB.md#b1-정보-참고-문헌-informative-references)

[@ 영어 원문](SocialWebProtocols-en.md)

[맨 위로](#목차-table-of-contents)