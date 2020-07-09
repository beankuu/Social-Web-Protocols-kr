[README로 돌아가기](README.md)

# [소셜 웹 프로토콜 (Social Web Protocols)]()

2017년 12월 25일 <abbr title="World Wide Web Consortium">W3C</abbr> Working Group 노트

**현재 버전**
- https://www.w3.org/TR/2017/NOTE-social-web-protocols-20171225/

**최신 게시 버전**
- 

**최신 편집자 초안**
- https://w3c-social.github.io/social-web-protocols

**이전 버전**
- https://www.w3.org/TR/2017/WD-social-web-protocols-20170504/

**편집자:**
- [Amy Guy](http://rhiaro.co.uk/), [University of Edinburgh](http://inf.ed.ac.uk/), amy@rhiaro.co.uk

**저장소**
- [Git 저장소](https://github.com/w3c-social/social-web-protocols)
- [이슈들](https://github.com/w3c-social/social-web-protocols/issues)
- [커밋들](https://github.com/w3c-social/social-web-protocols/gh-pages)

[Copyright](https://www.w3.org/Consortium/Legal/ipr-notice#Copyright) © 2017 [<abbr title="World Wide Web Consortium">W3C</abbr>](https://www.w3.org/)® (<abbr title="Massachusetts Institute of Technology">[MIT](https://www.csail.mit.edu/)</abbr>, <abbr title="European Research Consortium for Informatics and Mathematics">[ERCIM](https://www.ercim.eu/)</abbr>, [Keio](https://www.keio.ac.jp/), [Beihang](http://ev.buaa.edu.cn/)). <abbr title="World Wide Web Consortium">W3C</abbr> [법적 책임](https://www.w3.org/Consortium/Legal/ipr-notice#Legal_Disclaimer), [상표](https://www.w3.org/Consortium/Legal/ipr-notice#W3C_Trademarks)와 [문서 허용 라이센스](https://www.w3.org/Consortium/Legal/2015/copyright-software-and-document) 규칙이 적용됩니다.

-----

## [요약 (Abstract)](#소셜-웹-프로토콜-social-web-protocols)

Social Web Protocols은 웹에서의 분산된 소셜들의 다양한 상호작용 방법들을 가능하게 하는 표준들의 집합체입니다. 이 문서에서는 각 표준들의 용도와 이들이 어떻게 조화를 이루는지에 대해 설명합니다.

## [이 문서의 상태 (Status of This Document)](#소셜-웹-프로토콜-social-web-protocols)

_이 섹션에서는 현 문서의 발행 당시의 상태에 대하여 기술합니다. 다른 문서가 이 문서를 대체 할 수 있습니다. 현재 <abbr title="World Wide Web Consortium">W3C</abbr> 출판물 목록 및 이 기술보고서의 최신 개정판은 https://www.w3.org/TR/ 에 있는 [<abbr title="World Wide Web Consortium">W3C</abbr> 기술보고서 색인](https://www.w3.org/TR/)에서 찾아볼 수 있습니다._

이 문서는 [Social Web Working Group](https://www.w3.org/Social/WG)에 의하여 작성된 Working Group 노트입니다. 이 문서에 관한 의견은 언제나 환영합니다. 의견이 있을시 public-socialweb@w3.org ([구독](public-socialweb-request@w3.org), [기록들](https://lists.w3.org/Archives/Public/public-socialweb/))로 보내주시길 바랍니다.

Working Group 노트로 게시된 것은 <abbr title="World Wide Web Consortium">W3C</abbr> 멤버십에 의해 수용되었다는 의미가 아닙니다. 이 문서는 초안 문서이며 언제든지 다른 문서에 의해 업데이트, 교체 또는 폐기될 수 있습니다. 이 문서를 진행 중인 작업 이외의 다른 문서로 인용하는 것은 적절하지 않습니다.

이 문서는 [<abbr title="World Wide Web Consortium">W3C</abbr> 특허 정책](https://www.w3.org/Consortium/Patent-Policy/)에 따라 운영되는 그룹이 작성하였습니다. <abbr title="World Wide Web Consortium">W3C</abbr>는 그룹의 성과물에 관한 [모든 공개 특허 공개 목록](https://www.w3.org/2004/01/pp-impl/72531/status)을 관리합니다. 이곳에서는 특허 공개에 대한 지시사항도 포함됩니다. [필수 주장(들)](https://www.w3.org/Consortium/Patent-Policy/#def-essential)을 포함한다고 생각되는 특허에 대하여 실제 지식을 보유한 개인은 [<abbr title="World Wide Web Consortium">W3C</abbr> 특허 정책의 섹션6](https://www.w3.org/Consortium/Patent-Policy/#sec-Disclosure)에 의하여 정보를 공개하여야 합니다.

이 문서는 [2017년 3월 1일 <abbr title="World Wide Web Consortium">W3C</abbr> 프로세스 문서](https://www.w3.org/2017/Process-20170301/)를 적용받습니다.

## 목차 (Table of Contents)

1\. [서문 (Introduction)](#1-서문-introduction)

2\. [개요 (Overview)](#2-개요-overview)

- 2.1 [컨텐츠 (Contents)](#21-컨텐츠-contents)
- 2.2 [정의 (Definitions)](#22-정의-definitions)
- 2.3 [규격 (Specifications)](#23-규격-specifications)
  - 2.3.1 [요구사항 (Requirements)](#231-요구사항-requirements)
  - 2.3.2 [이 규격들은 서로 어떤 관계가 있을까요? (How do these specifications relate to each other?)](#232-이-규격들은-서로-어떤-관계가-있을까요-how-do-these-specifications-relate-to-each-other)

3\. [읽기 (Reading)](#3-읽기-reading)

- 3.1 [컨텐츠 표현 (Content representation)](#31-컨텐츠-표현-content-representation)
  - 3.1.1 [다른 방법으로 컨텐츠 표현 (Other ways of representing content)](#311-다른-방법으로-컨텐츠-표현-other-ways-of-representing-content)
- 3.2 [객체 (Objects)](#32-객체-objects)
- 3.3 [컬렉션 (Collections)](#33-컬렉션-collections)
  - 3.3.1 [특별 스트림 (Special streams)](#331-특별-스트림-special-streams)
  - 3.3.2 [인박스 (Inboxes)](#332-인박스-inboxes)

4\. [게시 (Publishing)](#4-게시-publishing)

- 4.1 [생성 (Creating)](#41-생성-creating)
- 4.2 [업데이트 (Updating)](#42-업데이트-updating)
- 4.3 [삭제 (Deleting)](#43-삭제-deleting)

5\. [구독 (Subscribing)](#5-구독-subscribing)

- 5.1 [`as:Follow`를 사용하여 구독 (Subscribing with `as:Follow`)](#51-asfollow를-사용하여-구독-subscribing-with-asfollow)
- 5.2 [hub를 사용하여 구독 (Subscribing with a hub)](#52-hub를-사용하여-구독-subscribing-with-a-hub)

6\. [전달 (Delivery)](#6-전달-delivery)

- 6.1 [타겟팅과 발견 (Targeting and discovery)](#61-타겟팅과-발견-targeting-and-discovery)
- 6.2 [일반적인 알림 (Generic notifications)](#62-일반적인-알림-generic-notifications)
- 6.3 [액티비티 알림 (Activity notifications)](#63-액티비티-알림-activity-notifications)
- 6.4 [멘션 (Mentioning)](#64-멘션-mentioning)
  - 6.4.1 [업데이트와 삭제 (Updates and deletes)](#641-업데이트와-삭제-updates-and-deletes)
- 6.5 [전달 상호 운용성 (Delivery interop)](#65-전달-상호-운용성-delivery-interop)
  - 6.5.1 [Webmention을 AS2 / ActivityPub로 (Webmention as AS2 / ActivityPub)](#651-webmention을-as2--activitypub로-webmention-as-as2--activitypub)
  - 6.5.2 [LDN 에서 Webmention로 (LDN to Webmention)](#652-ldn-에서-webmention로-ldn-to-webmention)
  - 6.5.3 [Webmention 에서 LDN로 (Webmention to LDN)](#653-webmention-에서-ldn로-webmention-to-ldn)

7\. [프로필 (Profiles)](#7-프로필-profiles)

- 7.1 [관계 (Relationships)](#71-관계-relationships))
- 7.2 [인증, 권한부여와 액세스 제어 (Authentication, authorization, and access control)](#72-인증-권한부여와-액세스-제어-authentication-authorization-and-access-control)

8\. [관련된 규격들 (Related specifcations)](#8-관련된-규격들-related-specifcations)

A\. [변경사항 (Change Log)](#a-변경사항-change-log)

- A.1 [2017년 5월 4일 WD에서 이 버전으로의 변경사항 (Changes from 4 May 2017 WD to this version)](#a1-2017년-5월-4일-wd에서-이-버전으로의-변경사항-changes-from-4-may-2017-wd-to-this-version))
- A.2 [2016년 11월 16일 WD에서 이 버전으로의 변경사항 (Changes from 16 November 2016 WD to this version)](#a2-2016년-11월-16일-wd에서-이-버전으로의-변경사항-changes-from-16-november-2016-wd-to-this-version)
- A.3 [2016년 11월 1일 WD에서 이 버전으로의 변경사항 (Changes from 1 November 2016 WD to this version)](#a3-2016년-11월-1일-wd에서-이-버전으로의-변경사항-changes-from-1-november-2016-wd-to-this-version)
- A.4 [2016년 10월 12일 WD에서 이 버전으로의 변경사항 (Changes from 12 October 2016 WD to this version)](#a4-2016년-10월-12일-wd에서-이-버전으로의-변경사항-changes-from-12-october-2016-wd-to-this-version)
- A.5 [2016년 8월 23일 버전에서 2016년 10월 12일 버전으로의 변경사항 (Changes from 23 August to 12 October 2016)](#a5-2016년-8월-23일-버전에서-2016년-10월-12일-버전으로의-변경사항-changes-from-23-august-to-12-october-2016)
- A.6 [2016년 6월 3일 버전에서 2016년 8월 23일 버전으로의 변경사항 (Changes from 3 June to 23 August 2016)](#a6-2016년-6월-3일-버전에서-2016년-8월-23일-버전으로의-변경사항-changes-from-3-june-to-23-august-2016))

B\. [참고 문헌 (References)](#b-참고-문헌-references)

- B.1 [정보 참고 문헌 (Informative references)](#b1-정보-참고-문헌-informative-references)

## 1. [서문 (Introduction)](#목차-table-of-contents)

<abbr title="World Wide Web Consortium">W3C</abbr> Social Web Working Group은 2014년 6월부터 2017년 12월까지 운영되었으며 7가지의 권장사항들과 몇 가지의 참고사항들을 발표했습니다. 이 문서는 참고사항 중의 하나이며, 그룹이 마감할 당시의 작업에 대해 설명합니다.

이 작업은 끝나지 않았고, 관련된 여러 공동체들은 아직 종료되지 않았습니다. 작업은 [Social Web Community Group](https://www.w3.org/wiki/SocialCG)에서 계속 진행되며 여러분들의 참여를 열렬히 환영합니다.

## 2. [개요 (Overview)](#목차-table-of-contents)

사람들과 그들이 만든 콘텐츠는 소셜 웹의 핵심 요소입니다; 이들은 소셜 그래프를 구성하죠. 이 문서에서는 사용자가 다음을 수행할 수 있는 표준적인 방법을 설명합니다:

- 소셜 컨텐츠를 작성, 업데이트 및 삭제합니다;
- 자신의 컨텐츠에 가입하여 다른 사용자와 연결합니다;
- 다른 사람들의 컨텐츠와 상호작용합니다;
- 다른 사람들이 자신의 컨텐츠와 상호작용할 때 알림을 받습니다.

위 사항은 _콘텐츠가 무엇인지_, _컨텐츠가 저장된 위치가 어디인지_ 랑 관계없이 언제든지 해당됩니다.

이러한 요소들은 상호운용 가능한 분산형 소셜 시스템을 구성하는 핵심 구성 요소입니다.

이러한 각 구성요소는 필요에 따라 독립적으로 구현하거나, 한 시스템에서 모두 함께 구현될 수 있을 뿐만 아니라 도메인별 요구사항을 충족하도록 확장할 수 있습니다. 사용자는 원하는 수의 호환 서버에 소셜 데이터를 저장할 수 있으며, 다른 곳에서 호스팅되는 호환 클라이언트를 사용하여 자신의 컨텐츠 및 다른 사용자의 컨텐츠와 상호 작용할 수 있습니다.

[Social Web Working Group 헌장](https://www.w3.org/2013/socialweb/social-wg-charter)은 이 그룹이 검토한 다음과 같은 결과물을 제안하며, 이 문서 전반에 걸쳐 참조할 예정입니다:

**소셜 데이터 구문 (Social Data Syntax)**

JSON 기반 구문을 사용하여 상태 업데이트와 같은 소셜 정보를 서로 다른 소셜 시스템들을 거쳐 전송할 수 있습니다.

**소셜 API (Social API)**

개발자가 소셜 상태 업데이트 같은 제3자 정보를 포함 및 정제할 수 있는 클라이언트측 API의 규격을 정의하는 문서입니다.

**연합 프로토콜 (Federation Protocol)**

서로 다른 웹 기반 소셜 시스템 간에 액티비티-기반 상태 업데이트 및 (프로필 정보 같은) 기타 데이터를 결합할 수 있는 웹 프로토콜입니다. 연합은 클라이언트-서버 아키텍처 내에 업데이트를 공유하는 여러 서버를 포함해야 하며 분산형 사회 시스템을 구축할 수 있어야 합니다.

### 2.1 [컨텐츠 (Contents)](#2-개요-overview)

Social Web Working Group 규격의 개요입니다.

Working Group 내에서 제안된 실행 가능한 기술 접근법의 다양성 때문에 여러 가지 명세서가 서로 다른 메커니즘을 통해 중복되는 기능을 제공하는 권장 사항에 도달했습니다. 이 문서는 다양한 규격을 구현하는 방법과 시기에 대한 유용한 지침과, 유사한 규격들을 연결하기 위한 방법에 대한 힌트를 제공하기 위해 존재합니다.

### 2.2 [정의 (Definitions)](#2-개요-overview)

이 문서는 위의 구성 요소와 관련된 5개의 섹션으로 나뉘며, [소셜 API 요구사항](https://www.w3.org/wiki/Socialwg/Social_API/Requirements) 에서 파생됩니다. 다양한 Social Web Working Group 규격들은 이러한 요구 사항의 서로 다른 조합들로 구성되기 때문에([2.3.1 요구 사항](#231-요구사항-requirements) 참조) 여기에서는 요구사항을 명확하게 정의합니다.

**[읽기 (reading)](#3-읽기-reading)**

소셜 콘텐츠에 사용할 구문과 어휘를 설명하는 규격을 다룹니다. 피드를 노출하는 응용 프로그램뿐만 아니라 피드를 소비하는 응용 프로그램에 유용합니다.

**게시 (publishing)**

서버에 [create](#4-게시-publishing), [update](#42-업데이트-updating) 또는 [delete](#43-삭제-deleting)를 지시하는 방법을 고객에게 알려주는 소셜 API 규격을 다룹니다.

**[구독 (subscribing)](#5-구독-subscribing)**

- 콘텐츠에 대한 알림을 요청하는 방법과 요청후 알림을 전달하는 방법을 설명하는 연합 프로토콜 규격이 나와 있습니다.

**[전달 (delivery)](#6-전달-delivery)**

- 구독을 통해 요청되지 않은 알림를 전달하는 방법을 설명하는 연합 프로토콜 규격을 다룹니다.

**[프로필 (profiles)](#7-프로필-profiles)**

- 프로필을 설명하는 규격을 다룹니다.

### 2.3 [규격 (Specifications)](#2-개요-overview)

아래의 항목들은 Social Web Working Group 에서 제작한 규격들입니다. 새로운 구현 보고서 및 피드백은 언제든지 환영합니다 (각 문서의 맨 위에 이러한 보고서를 제출할 곳에 대한 세부 정보가 있습니다).

**[[Activitypub](#activitypub)]**

- 클라이언트-서버간 상호 작용(예: 게시) 및 서버-서버간 상호 작용(즉, 연합)을 위한 JSON(-LD) 기반 API입니다.

**ActivityStreams 2.0 [[activitystreams-core](#activitystreams-core)] 와 [[activitystreams-vocabulary](#activitystreams-vocabulary)]**

- JSON(-LD)에서 소셜 액티비티, 액터, 객체 및 컬렉션을 [나타내는](#3-읽기-reading) 구문과 어휘입니다.

**Linked Data Notifications ([[LDN](#ldn)])**

- [전송](#6-전달-delivery)을 위한 JSON-LD 기반 프로토콜입니다.

**[[Micropub](#micropub)]**

- 클라이언트-서버 간 상호 작용(예: 게시)을 위한 폼-인코딩 및 JSON 기반 API입니다.

**[[Webmention](#webmention)]**

- [전송](#6-전달-delivery)을 위한 폼-인코딩 기반 프로토콜입니다.

**[[WebSub](#websub)]**

- 모든 리소스에 [구독](#5-구독-subscribing) 하고 리소스에 대한 업데이트를 [전달](#6-전달-delivery)하기 위한 프로토콜입니다.

Social Web Working Group의 권장사항은 아니지만 헌장 자료와 관련된 규격은 [8. 관련 규격](#8-관련된-규격들-related-specifcations)에 설명되어 있습니다.

### 2.3.1 [요구사항 (Requirements)](#23-규격-specifications)

이 표는 [Social Web Working Group 헌장](https://www.w3.org/2013/socialweb/social-wg-charter.html)와 [소셜 API 요구사항](https://www.w3.org/wiki/Socialwg/Social_API/Requirements)에 따른 상위 수준의 요구사항 및 Working Group 의 규격과 각 요구 사항들이 어떻게 서로 중첩되는지를 보여줍니다.

이 표에는 각 규격의 핵심 기능에서 충족되는 요구 사항이 나열되어 있습니다. 일부 규격은 규격을 결합하는 방법을 결정할 때 유용할 수 있으며 본 문서 전체에 걸쳐 적절하게 강조 표시되어 있는 다른 요구 사항에 대해 추가적으로 언급하거나 제안할 수 있습니다.

<table class="th90"><tbody>
<tr>
    <td></td>
    <td colspan="3">데이터 구문</td>
    <td colspan="4">소셜 API</td>
    <td colspan="2">연합 프로토콜</td>
    <td></td>
</tr>
<tr>
    <th></th>
    <th><a href="#content-representation">어휘</a></th>
    <th><a href="#content-representation">구문</a></th>
    <th><a href="#profiles">프로필</a></th>
    <th><a href="#reading">읽기</a></th>
    <th><a href="#publishing">생성</a></th>
    <th><a href="#updating">업데이트</a></th>
    <th><a href="#deleting">삭제</a></th>
    <th><a href="#subscribing">구독</a></th>
    <th><a href="#delivery">전달</a></th>
</tr>
<tr>
    <td style="text-align:left;">ActivityPub</td>
    <td></td>
    <td></td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
</tr>
<tr>
    <td style="text-align:left;">ActivityStreams 2.0</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
</tr>
<tr>
    <td style="text-align:left;">Linked Data Notifications</td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td>X</td>
</tr>
<tr>
    <td style="text-align:left;">Micropub</td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td></td>
    <td></td>
</tr>
<tr>
    <td style="text-align:left;">Webmention</td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td>X</td>
</tr>
<tr>
    <td style="text-align:left;">WebSub<br></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td>X</td>
    <td></td>
</tr>
</tbody></table>

### 2.3.2 [이 규격들은 서로 어떤 관계가 있을까요? (How do these specifications relate to each other?)](#23-규격-specifications)

간략하게나마, 규격 간 주요 관계는 다음과 같습니다:

- **ActivityPub 와 ActivityStreams 2.0**: ActivityPub은 모든 요청의 페이로드에 AS2 구문과 어휘를 사용합니다.
- **ActivityPub 와 Linked Data Notifications**: ActivityPub에서는 페이로드를 AS2로 요구하여 LDN을 알림 전달 메커니즘으로만 사용합니다. _인박스_ 엔드포인트 검색방식은 동일합니다. LDN 수신자는 ActivityPub 연합 서버의 요청을 이해할 수 있지만, ActivityPub 서버는 일반적인 LDN 전달자의 요청을 이해하지 못할 수도 있습니다.
- **ActivityStreams 2.0 와 Linked Data Notifications**: LDN은 알림 요청 페이로드에 AS2 구문과 어휘를 사용 *할 수도* 있습니다.
- **Webmention 와 Linked Data Notifications**: 서로 다른 유형의 요청들로 인해 브릿지해야 하는 중복되는 기능입니다. LDN 요청은 Webmention 요청과 동일한 데이터를 포함 *할 수도* 있지만, 반드시 그 반대일 필요는 없습니다.
- **ActivityPub 와 Microub**: 서로 다른 어휘와 서로 다른 유형의 요청들로 인해 브릿지해야 하는 중복되는 기능입니다. Micropub는 컨텐츠 작성을 위해 클라이언트-서버간 상호 작용을 하지만; 액티비티펍은 위의 기능과 _함께_ 부작용과 서버-서버간 상호 작용에도 사용합니다.
- **Micropub 와 Webmention**: 는 상호 보완적이지만 독립적입니다. Micropub로 콘텐츠를 만든 다음 콘텐츠에서 참조하는 모든 URL로 Webmentions를 보낼 수 있습니다.
- **Micropub 와 Linked Data Notifications**: 는 상호 보완적이지만 독립적입니다. Micropub로 콘텐츠를 만든 다음, 콘텐츠에서 참조하는 모든 관련 리소스에서 LDN 검색을 시작할 수 있습니다.
- **Micropub 와 WebSub**: 는 상호 보완적이지만 독립적입니다. Microub로 콘텐츠를 만든 다음 WebSub _허브(hub)_ 가 구독자에 대한 전달을 처리할 수 있습니다.
- **ActivityPub 와 WebSub**: 서로 다른 컨텐츠 유형 및 검증 메커니즘을 사용하여 중복되는 기능을 제공합니다.

## 3. [읽기 (Reading)](#목차-table-of-contents)

당신이 컨텐츠 게시자인 경우 이 섹션에서는 컨텐츠를 게시하는 방법에 대해 설명합니다. 반대로 컨텐츠 소비자일 경우, 이 섹션에서 다룰 것들을 소비하게 될것입니다.

### 3.1 [컨텐츠 표현 (Content representation)](#3-읽기-reading)

**ActivityStreams 2.0** 은 소셜 데이터에 권장되는 구문 ([[activitystreams-core](#activitystreams-core)]) 와 어휘 ([[activitystreams-vocabulary](#activitystreams-vocabulary)]) 로 이루어져 있습니다. ActivityStreams 2.0은 컨텐츠와 상호작용을 _Objects_ 와 _Activities_ 로 나타냅니다. ActivityStreams 어휘는 한정된 집합의 공통 객체(Object) 및 액티비티(Activity) 타입들과 속성들을 정의하고, 이를 확장하거나 특수화하려는 어플리케이션의 확장 메커니즘을 정의합니다.

ActivityStreams 2.0 콘텐츠는 Content-Type `application/activity+json`, JSON-LD 확장 구현에서는 `application/ld+json; profile="https://www.w3.org/ns/activitystreams"` 로 제공됩니다. 소비자는 이 두 가지 Content-Type을 모두 ActivityStream 2.0으로 인식해야 하며 동등하게 취급해야 합니다.

ActivityStreams 2.0 준수를 주장하려면 데이터 게시자는 *반드시* 가능한 한 ActivityStreams 2.0 어휘를 사용해야 하며, 다른 어휘들은 _추가적으로만_ 사용하거나 적절한 ActivityStreams 2.0 용어가 없는 경우에만 사용해야 합니다.

>참고: ActivityStreams 1.0
>
>ActivityStreams 2.0은 [[AS1](#as1)]을 기반으로 구축되며 완전하게 역호환되지는 않습니다; [AS1과 AS2의 관계는 AS2 규격에 설명되어 있습니다](http://www.w3.org/TR/activitystreams-core#activitystreams-1.0). [[AS1](#as1)]을 구현한 경우 ActivityStreams 2.0으로 전환해야 합니다.

컨텐츠가 ActivityStreams 2.0 JSON으로 제공되도록 하려면 적절한 `Accept` 헤더(예: `application/activity+json` 또는 `application/ld+json`)로 요청될 때 직접 또는 `rel="alternate" type="application/activity+json"` 링크를 통해 간접적으로 수행할 수 있습니다. 게시자를 대신하여 ActivityStreams 2.0 JSON 을 동적으로 생성하는 제3자 서비스의 경우 이 링크는 다른 도메인으로 연결될 수 있습니다.

>참고: JSON-LD
>
>JSON-LD로 전송되는 경우 ActivityStreams 2.0은 [압축](https://json-ld.org/spec/latest/json-ld-api/#compaction)되어야 하며 절대 `@graph` 키워드를 사용하면 안 됩니다. 그 이유는 ActivityStreams 2.0 문서의 루트로 단일 `Object`가 필요하기 때문입니다. 여러 리소스에 서비스를 제공하기 위해 대신 리소스를 중첩할 수 있습니다.
>
>ActivityStreams 2.0 JSON-LD 컨텍스트(https://www.w3.org/ns/activitystreams#)는 `@id`와 `@type`을 각각 `id`와 `type`로 별칭합니다.

**[[Activitypub](#activitypub)]** 은 모든 데이터에 ActivityStreams 2.0을 사용하며 추가적인 용어들과 함께 ActivityStreams 2.0을 _확장_ 합니다. 따라서 ActivityPub를 사용하려면 응답에 Content-Type `application/ld+json; profile="https://www.w3.org/ns/activitystreams"`이 있어야 합니다. 그러나 게시자는 `application/activity+json` 수락 헤더가 있는 요청도 존중해야 합니다.

### 3.1.1 [다른 방법으로 컨텐츠 표현 (Other ways of representing content)](#31-컨텐츠-표현-content-representation)

ActivityStreams 2.0이 마음에 들지 않더라도 특정한 작업에 사용할 수 있는 몇 가지 규격들이 있습니다.

**[[LDN](#ldn)]** 알림 콘텐츠는 데이터를 JSON-LD로 사용할 수 있는 한 모든 어휘를 사용할 수 있습니다. 따라서 알림은 ActivityStreams 2.0을 사용 *할 수도* 있지만 반드시 그럴 필요는 없습니다.

**[[Micropub](#micropub)]** 클라이언트중 데이터 읽기를 기대하는 클라이언트 (일반적으로 _[업데이트](#42-업데이트-updating)_ 클라이언트)는 ActivityStreams 2.0 를 구문 분석된 마이크로포맷2 구문([[microformats2-parsing](#microformats2-parsing)])이 적용된 JSON으로 예상하고 있습니다.

**[[WebSub](#websub)]** 는 게시자가 사용하는 Content-Type에 대해 독립적입니다; 허브는 게시자의 `topic` URL에서 게시자가 제작한 그대로 구독자에게 새 컨텐츠를 전달할 것으로 예상됩니다.

## 3.2 [객체 (Objects)](#3-읽기-reading)

모든 ActivityStreams 2.0 개체는 `id` 속성에 URL을 가지고 있으며, 이 URL은 개체의 속성을 반환합니다. 응답은 요청자의 콘텐츠 액세스 권한에 따라 달라질 수 있습니다.

## 3.3 [컬렉션 (Collections)](#3-읽기-reading)

각 ActivityStreams 2.0 컬렉션에는 요청자의 액세스 권한에 따라 스트림 내용을 반환하는 URL이 `id` 속성이 있습니다. 이는 페이징 될 수 있습니다 - ActivityStreams 2.0은 [페이징 메커니즘](https://www.w3.org/TR/activitystreams-core/#paging)을 제공합니다. 여기에는 스트림에 대한 추가 메타데이터(예를들어 제목이나 설명)가 포함될 수 있습니다.

컬렉션의 각 [객체](#objects)에는 최소한 URL (`id`)가 포함되고,선택적으로 객체의 다른 속성들이 포함됩니다.

컬렉션은 개체 또는 고정 집합의 스트림 변경 사항을 나타낼 수 있습니다. 하나 이상의 내용 스트림과 하나의 [프로필](#7-프로필-profiles)이 연관되어 있을 수 있습니다. 스트림은 자동으로 또는 수동으로 생성될 수 있으며, 스트림의 큐레이터가 결정한 포스트 유형, 주제, 청중 또는 임의의 기준에 따라 분리될 수 있습니다. 프로필에는 소비자가 읽거나 구독할 수 있는 여러 스트림에 대한 링크가 포함될 수 있습니다.

### 3.3.1 [특별 스트림 (Special streams)](#33-컬렉션-collections)

**[[Activitypub](#activitypub)]** 은 다음 속성을 통해 프로필에서 *반드시* 액세스가 가능해야 하는 두 개의 스트림을 지정합니다.

- `inbox`: 작업자가 받은 모든 객체로 구성된 ActivityStreams 2.0 컬렉션에 대한 참조.
- `outbox`: 액터에 의해 생산된 모든 객체로 구성된 ActivityStreams 2.0 컬렉션.

ActivityPub는 추가 스트림에 접근하기 위한 추가 속성도 지정합니다; `following` 및 `followers`는 필수적이며,나머지는 선택 사항입니다.

- `following`: 이 액터가 팔로우하고 있는 ActivityStreams 2.0 컬렉션.
- `followers`: 이 액터를 팔로잉하는 액터들의 ActivityStreams 2.0 컬렉션
- `liked`: 액터의 모든 (서버에서 자동으로 생성된) `Like` 액티비티의 모든  `object`의 ActivityStreams 2.0 컬렉션.
- `streams`: 관심 있을수도 있는 보조적인 컬렉션 목록.
- `preferredUsername`
- `endpoints`: 이 액터 또는 이 액터를 참조하는 사용자에게 유용할 수 있는 추가(일반적으로 서버/도메인 전체) 엔드포인트의 매핑: `proxyUrl`, `oauthAuthorizationEndpoint`, `oauthTokenEndpoint`, `provideClientKey`, `signClientKey`, `sharedInbox`
- 그리고 위의 속성 외에 해당되는 모든 ActivityStreams 2.0 속성들을 포함합니다.

[[Activitypub](#activitypub)]은 서버가 `Add` 및 `Remove` 유형의 활동을 수신할 때 서버에 대한 특수 동작을 지정하여 임의 컬렉션을 만들 수 있도록 허용합니다. 서버가 `outbox`에서 이러한 활동을 수신하고 `target`이 `Collection`인 경우, `object`를 `target`에 (`Add` 하기 위해)추가하거나 `object`를 `target`에서 (`Remove` 하기 위해) 제거합니다.

### 3.3.2 [인박스 (Inboxes)](#33-컬렉션-collections)

인박스은 새로운 객체가 [배달](#6-전달-delivery)될 수 있는 엔드포인트입니다. 또한 내용을 읽힐 수도 있는 컬렉션의 역할도 합니다. 인박스 엔드포인트은 ActivityPub 및 LDN에서 모두 사용되며 다음 속성을 통해 검색할 수 있습니다.

- `ldp:inbox` (`http://www.w3.org/ns/ldp#inbox`)
- `as:inbox` (`https://www.w3.org/ns/activitystreams#inbox`)

JSON-LD의 관점에서 후자는 전자의 별칭입니다.

인박스에 글을 어떻게 그리고 언제 쓰는지에 대해서는 [배달](#6-전달-delivery)의 정보를 참조하시길 바랍니다.

이 컬렉션의 내용 역시 읽힐 수도 있습니다. ActivityPub와 LDN은 인박스에 쓰기 위해 동일한 작업을 수행하지만, AS2 및 LDP와의 각각 자극적이지만 피할 수 없는 호환성 요구 사항으로 인해 인박스 내용을 읽을 때는 서로 다른 어휘를 사용합니다. 다행히도 고객이 두 단어를 모두 확인하거나 게시자가 두 단어를 모두 사용하여 게시하는 것은 큰 구현 장애물이 아니기 때문에 브릿징은 매우 사소한 일입니다.

- ActivityPub 인박스은 ActivityStreams 2.0 `OrderedCollection`이며, `items` 속성으로 내용에 연결합니다.
- LDN 인박스은 (선택 사항으로 명시적 유형을 제공하는) [[LDP](#ldp)] `Container`이며 `contains` 속성으로 자신들의 컨텐츠와 연결합니다.

또한 ActivityPub는 반환되는 JSON-LD 형식에 대한 제약 조건이 더 많습니다. 다음 두 목록은 ActivityPub와 LDN을 둘다 지원하는 인박스 안에서 두 표준 사이의 작은 차이를 브릿징 하는 방법을 설명합니다.

**ActivityPub 서버** 를 LDN 소비자가 읽기를 원할 경우:

- 컬렉션의 모든 `items` 와 함께 `ldp:contains` (`http://www.w3.org/ns/ldp#contains`) 관계를 반환해야 합니다.

**ActivityPub 클라이언트** 가 LDN 인박스에서 읽기를 원할 경우:

- 반드시 content-type `application/ld+json`의 컨텐츠를 요청해야 합니다. JSON-LD 압축을 통해 실행하면 보다 친숙한 방식으로 응답 형식을 지정할 수 있습니다.
- (AS2 `items`가 아닌) `ldp:contains` 속성을 통해 인박스에서 항목들을 찾아내야 합니다.
- 항목 중 어떤 항목도 해당 속성이 중첩될 것으로 예상해서는 안 되며, `@id` 속성의 URL에서 개별적인 항목을 검색해야 할 수 있습니다.
- AS2가 완전히 없는 경우를 포함하여 인박스 자체의 항목 내에서 여러 어휘가 포함될 수 있습니다.

**LDN 수신자** 가 ActivityPub 사용 클라이언트에서 읽을 수 있기를 원할경우:

- 반드시 content-type `application/activity+json`을 `application/ld+json; profile="http://www.w3.org/ns/activitystreams"`과 동등하게 취급해야 합니다.
- 인박스 내용을 AS2 `Collection`으로 제공해야 합니다. 여기서 각 알림은 AS2 `items` 속성이 있는 인박스와 관련이 있습니다.
- 압축된 JSON-LD를 반환해야 하며, `@graph`는 문서의 루트로 인박스 컬렉션을 제공합니다.
- 인박스에 각 리소스의 추가 속성을 중첩하여 처리하기 더 쉽게 만들 수 있습니다.

**LDN 소비자** 가 ActivityPub 서버의 인박스에서 읽기를 원할 경우:

- content-type `application/activity+json`과 함께 컨텐츠가 반환되고 `@context`가 누락된 경우 기본 AS2 컨텍스트를 적용하고 이를 JSON-LD로 처리해야 합니다.
- (`ldp:contains` 보다는) AS2 `items` 속성을 통해 인박스에서 항목을 찾아야 합니다.

## 4. [게시 (Publishing)](#목차-table-of-contents)

이 문단에서 '게시'한다는 것은 특정 프로필과 관련된 송신 피드를 수정하는 것을 의미합니다. 여기에는 새 콘텐츠 작성과 기존 콘텐츠 업데이트 또는 삭제 등이 포함됩니다. 클라이언트를 통해 생성된 콘텐츠(예: 웹 양식, 모바일 앱, 센서, 스마트 장치)는 일반적으로 저장되고 일반적으로 공개되는(공용 또는 제한된 청중이 사용 가능한) 서버로 전송될 때 작성됩니다. 클라이언트와 서버는 작성, 업데이트 및 삭제를 독립적으로 지원할 수 있습니다. 클라이언트와 서버 사이에는 종속성이 없습니다.

>참고: 기타 게시 유형
>
>알림 전달 또는 구독 요청에 응답하면 수신 엔드포인트 에서는 무언가를 생성하거나 업데이트 또는 삭제하는 트리거가 발생할 수 있지만, 원래의 목적은 다릅니다. 이러한 사례는 적절한 경우 구독 및 배송 시 부작용이라고 불립니다.

클라이언트와 서버 간의 인증 및 권한 부여에 대한 참고사항은 [7.2 인증, 권한 부여 및 액세스 제어](#72-인증-권한부여와-액세스-제어-authentication-authorization-and-access-control)를 참조하시기 바랍니다.

Social Web Working Group에서 게시용으로 권장하는 두 가지 규격은 [[Activitypub](#activitypub)]와 [[Micropub](#micropub)]입니다. 이들은 서로 유사한 고급 메커니즘을 사용하지만, 데이터의 어휘 및 컨텐츠 타입 두가지 모두에 대한 요구 사항이 다릅니다.

ActivityPub에는 ActivityStreams 2.0 객체 및 액티비티를 생성하기 위한 클라이언트 간 API가 포함되어 있으며, 객체 발신과 관련된 클라이언트의 추가적인 책임 및 특정 객체 유형의 부작용에 대한 서버에 대한 추가적인 책임을 명시합니다.

Micropub는 블로그 포스트 유형의 콘텐츠를 만들 수 있는 기본 클라이언트-서버 API를 제공하며, 콘텐츠 생성의 빠른 시작과 더불어 (선택 사항인)더 복잡한 작업을 계층화할 수 있습니다. 또한 Micropub는 파일 업로드를 위한 미디어 엔드포인트을 제공합니다.

>참고: REST
>
>ActivityPub와 Micropub 모두 HTTP 동사를 기준으로는 게시용 API를 정의하지 않습니다. 좀 더 RESTFul한것이 필요한 경우 Linked Data Platform[[LDP](#ldp)] 를 참조하시길 바랍니다.

### 4.1 [생성 (Creating)](#4-게시-publishing)

**[[Activitypub](#activitypub)]**의 게시 엔드포인트는 아웃박스입니다. 클라이언트는 (인증된) 프로필의 URL을 시작점으로 간주하고 (JSON으로 제공되어야 하는)프로필 URL에서 찾아낸 `https://www.w3.org/ns/activitystreams#outbox` 속성의 값을 검색합니다. 그런 다음 클라이언트는 `application/ld+json; profile="https://www.w3.org/ns/activitystreams"`의 내용 유형을 가진 JSON 페이로드로 ActivityStreams 2.0 액티비티 또는 객체가 포함된 HTTP POST 요청을 합니다. 생성된 리소스의 URL은 서버의 재량에 따라 생성되고 `Location` HTTP 헤더에 반환됩니다. 이 프로토콜은 다음과 같은 경우에 적절하 사용할 수 있는 프로토콜입니다:

- 당신은 JSON 또는 JSON-LD 페이로드를 전송/수신하려고 합니다.
- 당신의 데이터가 [[activitystreams-core](#activitystreams-core)] 와 (JSON-LD를 통해 선택적으로 확장 가능한) [[activitystreams-vocabulary](#activitystreams-vocabulary)]로 정의되어 있습니다.
- 당신은 서버가 컨텐츠 작성 시 알려진 작업 집합을 수행했으면 좋겠습니다.

ActivityPub로 컨텐츠를 만들 때 발생하는 부작용은 대부분 다양한 컬렉션(좋아요, 팔로우 등)에 항목을 추가하는 것이지만, 사용자 차단에 대한 요구 사항과 연합 서버를 활성화하기 위한 후크도 포함합니다.

**[[Micropub](#micropub)]**의 게시 엔드포인트는 `micropub` 엔드포인트입니다. 클라이언트는 (HTTP `Link` 헤더 또는 HTML `<link>` 요소 안의) `rel="micropub"` 링크를 통해 프로필 URL에서 이를 검색합니다. 클라이언트는 생성되는 개체의 특성에 대한 키 값 쌍을 포함하는 `x-www-form-urlencoded` POST 요청을 만듭니다. 생성된 리소스의 URL은 서버의 재량에 따라 생성되고 `Location` HTTP 헤더에 반환됩니다. 클라이언트와 서버는 Microformats2 [[h-entry](#h-entry)] 어휘의 속성들을 지원해야 합니다. Micropub는 또한 네 가지 예약된 속성(`access_token`, `h`, `action` 및 `url`)을 정의하고 `mp-` 접두사 앞에 있는 모든 속성을 예약합니다; 이러한 속성들은 서버에 대한 명령으로 사용됩니다. 서버가 이러한 어휘 외에 발송된 추가 키값 들은 무시할 수 있습니다.

Micropub 요청은 JSON 페이로드로 대신 전송될 수 있으며, 이 페이로드의 구문은 [[microformats2-parsing](#microformats2-parsing)]에서 파생됩니다.

이 프로토콜은 다음과 같은 경우에 적절히 사용할 수 있는 프로토콜입니다:

- 당신은 form-encoded 된 정보 또는 JSON 페이로드를 전송/수신하려고 합니다.
- 당신의 데이터는 [[h-entry](#h-entry)] 구문과 어휘로 설명됩니다.
- 당신은 어휘 확장을 위해 클라이언트와 서버 간의 대역-외-계약에 의존할 수 있습니다.

### 4.2 [업데이트 (Updating)](#4-게시-publishing)

클라이언트가 속성(추가, 제거, 교체)에 대한 변경 사항을 기존 객체에 보낼 때 내용이 업데이트됩니다.

**[[Activitypub](#activitypub)]** 클라이언트는 ActivityStreams 2.0 `Update` 활동이 포함된 HTTP `POST` 요청을 `outbox`로 보냅니다. 액티비티의 `object`는 `id`를 포함한 기존의 객체이며 업데이트할 필드는 중첩되어야 합니다. 객체의 부분 표현을 발송할 경우, 생략된 필드는 서버에서 삭제되지 _않습니다_. 특정 필드를 삭제하려면 클라이언트가 `null` 값을 할당할 수 있습니다.

ActivityPub 연합 서버의 경우 업데이트를 원래 객체의 수신자 `inbox` 로 전파해야 합니다. 그러나 연합 서버가 `Update` 작업을 다른 서버의 `inbox`로 전달하면 수신인은 이것이 교체할 _완전한_ 객체라고 가정해야 합니다; 부분 업데이트는 서버-서버 간에 수행되지 않습니다.

이전 `Update`의 `object`와 함께 `Undo`를 사용하여 변경 내용을 되돌릴 수 있습니다.

**[[Micropub](#micropub)]** 클라이언트는 `"action": "update"` 지시어를 사용하여 JSON POST 요청으로 업데이트를 수행할 뿐만 아니라 업데이트할 속성을 Micropub 엔드포인트에서 `replace`, `add` 또는 `delete`합니다.  `replace`는 지정된 속성의 모든 값을 대체합니다. 속성이 아직 존재하지 않는 경우에는 해당 속성이 생성됩니다. `add`는 기존 값을 변경하지 않고 지정된 속성에 새 값을 추가합니다. 속성이 아직 존재하지 않는 경우 해당 값이 생성됩니다. `delete`는 지정된 속성을 제거합니다. 값을 지정하여 값을 기준으로 속성을 제거할 수도 있습니다.

서버가 또한 [[Webmention](#webmention)]을 구현하는 경우, 원본 Webmention을 수신한 모든 사용자에게 업데이트를 전파해야 합니다.

서버가 [[WebSub](#websub)]도 구현하고 업데이트된 리소스가 `topic`의 일부인 경우, 서버는 허브에 항목(topic) URL에 대한 업데이트를 통지해야 합니다.

### 4.3 [삭제 (Deleting)](#4-게시-publishing)

클라이언트가 기존 개체 삭제 요청을 보낼 때 내용이 삭제됩니다.

**[[Activitypub](#activitypub)]** 클라이언트는 ActivityStreams 2.0 `Delete` 액티비티를 포함하는 HTTP POST 요청을 인증된 사용자의 `outbox`로 전송하여 개체를 삭제합니다. 서버는 이 액티비티의 `object`를 묘비(tombstone)로 _교체_ 하고 `410 Gone` 상태 코드를 반환하거나 URL에서 `404 Not Found` 상태 코드를 반환해야 합니다.

이전 `Delete`의 객체로 `Undo`를 사용하여 `object`를 복원할 수 있습니다.

**[[Micropub](#micropub)]** 삭제 요청은 JSON: `"action": "delete"` 및 `"url": url-to-be-deleted` 두 개의 키-값 쌍이며 Micropub 엔드포인트으로 전송됩니다. 게시물들은 `"action": "undelete"`으로 다시 복원될 수 있습니다.

[업데이트](#42-업데이트-updating)와 마찬가지로 ActivityPub 연합, Webmention 또는 WebSub를 구현하는 서버는 그에 따라 삭제 내용을 전파해야 합니다.

## 5. [구독 (Subscribing)](#목차-table-of-contents)

(클라이언트 또는 서버) 에이전트는 콘텐츠 객체(예: 편집, 새로운 응답) 또는 콘텐츠 스트림(예: 특정 스트림에서 추가 또는 제거된 객체)에 대한 변경 사항을 알려달라고 요청할 수 있습니다. 이는 _구독중_ 으로 표현됩니다. 구독 메커니즘을 포함하는 규격은 ActivityPub와 WebSub입니다.

>참고: 구독 vs 배달
>
>알림을 받는 것은 구독 메커니즘의 구현에 의존할 필요가 없습니다. 즉, 전송자 또는 게시자로부터 알림을 명시적으로 요청하지 않아도 자체적으로 알림을 받도록 구현을 설정할 수 있습니다. [전달](#6-전달-delivery)을 참조하십시오.

### 5.1 [`as:Follow`를 사용하여 구독 (Subscribing with `as:Follow`)](#5-구독-subscribing)

**[[Activitypub](#activitypub)]** 서버는 모든 사용자에 대한 팔로워 컬렉션을 유지합니다. 이 컬렉션은 액티비티의 `to`, `cc` 또는 `bcc`인 필드에서 직접 주소를 지정하거나 자동 또는 기본적으로 주소를 지정할 수 있습니다. 그 결과 연합 서버는 액티비티를 컬렉션에 있는 각 프로필의 인박스으로 [전달](#6-전달-delivery)합니다.

구독 요청은 기본적으로 이 컬렉션에 추가하기 위한 요청입니다. 구독자의 서버가 대상의 `inbox`에 `Follow` 액티비티를 `POST`하여 수행됩니다. 이 요청은 인증되어야 하므로 추가적인 인증은 필요하지 않습니다. 그런 다음 대상 서버는 대상의 팔로워 모음에 구독자를 추가해야 합니다. 단, 대상이 구독자를 차단한 경우 예외가 발생할 수 있습니다.

이는 다음과 같은 경우에 적합한 구독 메커니즘입니다.

- 구독자가 객체, 스트림, 피드, 컬렉션, 대화 스레드가 아닌 특정 프로필의 `outbox`에서 업데이트를 요청하려고 합니다.
- 구독자와 게시자가 모두 ActivityStreams 2.0을 사용하여 통신합니다.
- 게시자는 구독자를 알고 있으며 게시자 자신이 구독자에게 콘텐츠를 전달할 능력이 있습니다.

배달은 연합 서버의 요구 사항일 뿐이므로, 잠재 구독자는 연합되지 않은 서버에 있는 프로필의 인박스에 (예외사항인 `405 Method Not Allowed`를 제외하고) `Follow` 액티비티를 `POST`할 수 없으므로 이러한 프로필에는 구독할 수 없습니다. 이 경우 잠재 구독자는 게시자의 `outbox`에서 정기적으로 내용을 가져오기를 원할 수도 있습니다.

### 5.2 [hub를 사용하여 구독 (Subscribing with a hub)](#5-구독-subscribing)

**[[WebSub](#websub)]** 는 허브 라고 하는 제3자 가입자에게 구독 처리 및 콘텐츠 전달을 위임하는 메커니즘을 제공합니다. 게시자가 해야 할 일은 HTTP `Link` 헤더 또는 `rel="hub"`가 있는 HTML `<link>` 요소를 사용하여 선택한 허브에 연결한 후 새로운 콘텐츠가 사용 가능할 때 허브에 알리는 것입니다. 게시자가 자체 허브에 내장되어 있을 수 있으므로 허브에 알리기 위한 메커니즘은 의도적으로 지정되지 않은 상태로 방치됩니다.

>참고: 허브에게 알림 전달
>
>게시자와 허브 간의 공통화를 위한 메커니즘은 향후 확장으로서 표준화될 수도 있습니다.

구독자는 게시자에서 허브를 검색하고, `hub.mode`("구독"), `hub.topic`(구독할 URL) 및 `hub.callback`(업데이트가 전송될, '추측이 불가능한' 구독별 URL) 값이 포함된 폼 인코딩 `POST` 요청을 보냅니다. 허브와 구독자는 일련의 교환을 수행하여 이 요청을 확인합니다.

허브가 게시자로부터 새 내용을 통지받으면 허브는 `topic` URL의 내용을 가져오고, 이를 POST 요청을 통해 가입자의 `callback` URL로 보냅니다. 요청 본문은 항목 URL의 내용이며, `Content-Type`은 반드시 일치해야 합니다. `rel=hub` `Link` 헤더가 포함되어야 합니다.

이는 다음과 같은 경우에 적합한 구독 메커니즘입니다.

- 구독자는 사용자 프로필뿐만 아니라 모든 리소스 및 콘텐츠 유형에 대한 업데이트를 요청하려고 합니다.
- 구독 요청이 인증되지 않았으므로 확인할 수 있는 방법이 필요합니다.
- 게시자가 업데이트 배포를 직접 수행하는 대신 다른 서비스(허브)에 위임하려고 합니다.

>참고: WebSub와 LDN
>
>LDN 수신기는 `inbox` URL을 `hub.callback` URL로 사용하고 JSON-LD로 게시된 리소스에만 가입하거나 JSON-LD 이외의 content-types를 수락하여 WebSub 허브에서 전달을 수신하는 데 사용할 수 있습니다.

## 6. [전달 (Delivery)](#목차-table-of-contents)

사용자 또는 어플리케이션은 수신자가 명시적으로 요청하지 않은 알림을 다른 사용자에게 전달하려고 할 수도 있습니다. 예를 들어, 메시지 또는 새로운 정보를 보내기 위해; 콘텐츠에 연결(회신, 좋아요, 즐겨찾기, 책갈피, 다시 게시 등) 했기 때문에; 사용자와 직접 연결(태깅, 언급)했기 때문에; 수신자가 웹 상의 일부 문서 또는 리소스의 상태 변경을 인식하도록 합니다. Social Web Working Group 규격에는 전달을 수행하기 위한 몇 가지 메커니즘이 포함되어 있습니다; 이 메커니즘은 일반적인 메커니즘부터 특수화된 메커니즘까지 여기에 기재되어 있습니다.

>참고: 배달 vs 구독.
>
>사용자가 명시적으로 [구독](#5-구독-subscribing)하지 않은 콘텐츠를 거부할 수 있도록 내버려 둘 필요가 있습니다. 예를 들어 다른 어떤 것도 배달의 구현에 의존해서는 안 됩니다.

### 6.1 [타겟팅과 발견 (Targeting and discovery)](#6-전달-delivery)

알림의 대상은 일반적으로 URL에서 참조하는 주소록 또는 제목입니다. 또한 대상은 이전에 [구독](#5-구독-subscribing) 요청을 통해 알림을 요청한 리소스일 수 있습니다. 대상을 결정한 후에는 특정 대상에 대한 알림을 보낼 위치를 검색해야 합니다. 검색에서 대상 URL을 가져와서 보낼 알림 유형(읽기 시작)을 승인할 엔드포인트에 대한 링크를 찾고 있습니다.

많은 잠재적 대상들이 알림을 받도록 구성되지 않을 수도 있다는 점을 유의하시길 바랍니다. 의심하지 않는 서버에 검색 관련 요청으로 과부하를 하지 않도록 하려면 어플리케이션은 동일한 도메인에 있는 대상에 검색을 여러 번 수행할 때 "백오프" 전략을 사용해야 합니다. 이 작업에는 이후 요청 사이의 시간을 늘리거나 실패한 검색 시도를 캐싱하여 나중에 해당 도메인을 피할 수 있습니다. 수신자 서버가 요청의 목적에 대해 자세히 알 수 있도록 사용 중인 알림 메커니즘에 대한 참조와 함께 `User-Agent` 헤더를 보낼 수 있습니다.

또한 어플리케이션은 대상 서버에서 반환한 관련된 캐시 제어 및 재시도 헤더를 고려해야 합니다.

### 6.2 [일반적인 알림 (Generic notifications)](#6-전달-delivery)

**[[LDN](#ldn)]** 은 콘텐츠를 포함할 수 있는 알림을 전송, 수신 및 소비하기 위한 연합 프로토콜이며, 사용자 또는 프로세스에 의해 트리거됩니다. 보내는 사람, 받는 사람 및 소비자는 모두 다른 도메인에 있을 수 있습니다. 이는 다음과 같은 경우에 적합한 알림 메커니즘입니다.

- 알림은 자신의 URL로 식별할 수 있어야 하며 수신자에 의해 노출되어 다른 어플리케이션이 검색하고 재사용할 수 있어야 합니다.
- 알림은 JSON-LD 페이로드(예: '뚱뚱한 핑')로 표시됩니다.
- 수신자가 수락한 알림 유형 또는 내용에 대한 제약 조건을 알려야 합니다.

[[LDN](#ldn)] 기능은 송신자, 수신자 및 소비자로 구분됩니다. 알림이 전송되는 엔드포인트는 `inbox`입니다. (사용자 프로필, 블로그 게시물, 문서 같은) 모든 리소스는 HTTP 링크 헤더 또는 (JSON-LD 또는 HTML+RDFa 를 포함한) 모든 RDF 구문에서 문서의 본문을 통해 검색할수 있도록 `inbox`를 알릴 수 있습니다. 이 인박스에 대해 송신자는 알림의 JSON-LD(또는 수신자와의 [[Accept-Post](#accept-post)] 를 주고받은 RDF 구문 같은) 페이로드를 포함하는 `POST` 요청을 합니다. 수신자는 알림 데이터를 검색할 수 있는 URL을 반환하고 `GET` 요청 시 인박스로 반환되는 목록에 이 URL을 추가합니다 ([3. 읽기](#3-읽기-reading) 참조). 소비자는 이 인박스 목록과 이 목록에서의 개별 알림을 JSON-LD(선택적으로는 다른 RDF 구문과 주고받은 콘텐츠)로 받아 볼 수 있습니다. 확실한 소비자의 유형은 사람이 읽을 수 있는 방식으로 알림을 표시하는 스크립트입니다.

>참고: LDP 호환성
>
>기존 [[LDP](#ldp)] 구현은 즉시 [[LDN](#ldn)] 수신자 역할을 할 수 있습니다; 게시자는 `ldp:Container` 를 리소스의 `inbox`로 사용한다 라고 알리면 됩니다.

다양한 사용 사례에서 LDN을 사용할 수 있도록 알림 페이로드는 의도적으로 열려 있습니다. 그러나 특정 목적을 가진 수신자는 수신자가 수락하는 알림 유형을 제한하려고 할 가능성이 높습니다. 따라서 [[SHACL](#shacl)]과 같은 데이터 모양 제약 조건을 광고함으로써 전송자가 요청을 불투명하게 거부하지 않고 이를 준수하려고 시도할 수 있습니다. 또한 이러한 제약 조건을 알리는 광고를 통해 사용자는 인박스의 알림 유형을 확인한 후 검색할 수 있습니다. 수신자는 내부 및 공개되지 않은 제약 조건에 따라 알림을 거부할 수 있으며, 예를 들어 발신자과 소비자 모두의 `Authorization` 헤더를 요구하여 인박스에 액세스할 수도 있습니다.

[[WebSub](#websub)] 게시자는 HTTP `POST` 요청을 사용하여 컨텐츠를 허브로, 허브는 가입자에게 전달합니다. 요청 본문은 전자의 경우에는 발신자의 재량에 맡기고, 후자의 경우에는 Content-Type과 일치해야 하며 `topic` URL의 내용을 포함해야 합니다.

### 6.3 [액티비티 알림 (Activity notifications)](#6-전달-delivery)

**[[Activitypub](#activitypub)]**에서는 [[LDN](#ldn)]을 사용하여 몇 가지 특정 제약 조건이 있는 알림을 보냅니다. 이는 다음과 같습니다:

- 알림 페이로드는 *반드시* 단일 ActivityStreams 2.0 활동이어야 합니다.
- 알림 페이로드는 *반드시* 소형 JSON-LD여야 합니다.
- 수신자는 *반드시* 본래 서버에서 해당 소스를 가져와 알림을 확인해야 합니다.
- 모든 알림 `POST` 요청은 인증됩니다.

[[Activitypub](#activitypub)]는 [[activitystreams-vocabulary](#activitystreams-vocabulary)] 청중을 지정과 객체 연결 속성을 통해 ([[LDN](#ldn)] 전송의 사전 요구 사항인) 알림을 보낼 대상을 정의하는 방법을 지정합니다.

[[Activitypub](#activitypub)]은 알림 수신의 결과로 서버가 수행해야 하는 부작용도 정의합니다. 여기에는 다음이 포함됩니다.

- `Create`, `Update` 및 `Delete` 작업을 수신 후 새 객체를 만들거나 업데이트 또는 삭제합니다.
- `Undo` 액티비티를 수신한 후 이전 활동의 부작용을 반전시킵니다.
- `Follow`, `Like` 및 `Block`에 대해 특화된 컬렉션들을 업데이트합니다.
- `Add` 와 `Remove` 액티비티을 수신 후 다른 컬렉션들을 업데이트합니다.
- 연합 서버의 경우 네트워크를 통해 액티비티를 전파하기 위한 추가 전달을 수행합니다.

>참고: 인박스 속성
>
>ActivityPub 작업자 프로필은 `https://www.w3.org/ns/activitystreams#inbox` 속성을 통해 인박스에 연결됩니다. 이것은 LDN의 `http://www.w3.org/ns/ldp#inbox`에 대한 (AS2 JSON-LD 컨텍스트에서의)별칭입니다. 이러한 문서를 구문 분석하기 위해 전체 JSON-LD 프로세서를 사용하는 어플리케이션에서는 이 용어들을 같은 용어로 취급할수 있습니다. 게으른 문자열 매칭을 수행하는 어플리케이션은 `ldp:inbox`를 찾으면 `as:inbox`와 동일한 방식으로 `POST` 요청을 수락한다는 점을 유념해야 합니다.

### 6.4 [멘션 (Mentioning)](#6-전달-delivery)

**[[Webmention](#webmention)]** 은 두 문서 간에 관계가 생성(또는 업데이트 또는 삭제)될 때 알림을 보내고 받을 수 있는 API를 제공합니다. Webmention 발신자는 다른 문서의 URL을 포함하는 내용의 작성(또는 수정)에 의해 트리거됩니다. 두 문서가 서로 다른 도메인에 있을 때 작동하므로 이는 연합 프로토콜의 역할을 합니다. 이는 다음과 같은 경우에 적합한 알림 메커니즘입니다:

- 다른 문서(대상)의 URL을 포함하는 문서(출처)가 있습니다.
- 엔드포인트 소유자는 요청을 확인할 수 있도록 소스를 볼 수 있는 권한을 가집니다.
- 전송해야 하는 데이터는 원본 및 대상 문서의 URL(즉, '얇은 ping') 뿐입니다.

원본 및 대상 문서의 구문에는 제약이 없습니다. (수신 Webmention을 처리할 수 있는 스크립트인) [[Webmention](#webmention)] 엔드포인트의 검색은 대상의 HTTP `Link` 헤더 또는 HTML 본문에서 링크 관계(`rel="webmention"`)를 통해 이루어집니다. 이 엔드포인트는 대상과 동일한 도메인에 있을 필요가 없으므로 Webmention 수신을 타사에 위임할 수 있습니다.

Webmention은 서버에서 소스를 역참조하고 구문 분석하여 대상 URL이 있는지 확인합니다. 대상 URL이 없으면 *반드시* Webmention을 거부해야 합니다.

Webmention은 소스 및 대상에 대해 `x-www-form-urlencoded`를 HTTP POST 요청의 매개 변수로 사용합니다. Webmention 수신시 수신자가 취해야 할 조치는 검증 이외에 명시되어 있지 않습니다. `GET` 요청 시 Webmention 엔드포인트이 반환해야 하는 내용도 지정되지 않은 상태로 남아 있습니다.

#### 6.4.1 [업데이트와 삭제 (Updates and deletes)](#64-멘션-mentioning)

실제로 Webmention 수신자는 Webmention 소스를 가져오고 저장하는 경향이 있습니다. 예를 들어, 대상 블로그 게시물 아래에 회신으로 표시되는 경우가 많습니다.

Webmention이 수신되고 수신자가 이 `source`와 `target` 조합을 처음 보는 경우, 이는 `source`와 `target` 간의 관계가 생성되었음을 나타냅니다. 수신자가 이전에 이러한 값을 본 적이 있는 경우, 수신자는 `source`를 가져와 구문 분석하여 무엇이 변경되었는지 확인할 수 있습니다. 즉, `source`의 내용이 업데이트된 경우(수신자가 처음부터 로컬 사본을 저장한 경우)거나 전체 원본이 삭제된 경우(`410 Gone` 예상) 입니다.

### 6.5 [전달 상호 운용성 (Delivery interop)](#6-전달-delivery)

이 섹션에서는 Webmention, ActivityPub 및 LDN을 구현하여 다른 사용자로부터 알림을 보내고 받기 위해 브릿징 코드를 만드는 방법에 대해 설명합니다.

#### 6.5.1 [Webmention을 AS2 / ActivityPub로 (Webmention as AS2 / ActivityPub)](#65-전달-상호-운용성-delivery-interop)

Webmention은 ActivityStreams 2.0 어휘가 있는 일관적인 리소스로 나타낼 수 있습니다. 이는 Webmention 발신자가 ActivityPub 연합 서버를 실행 중인 것으로 알려진 사용자를 언급하고 일반적인(즉, ActivityPub 전용이 아닌 경우) 알림 방법을 원하는 경우 유용하게 사용할 수 있습니다. 이 경우 발신자는 AS2 페이로드를 사용하여 [6.5.3 Webmention에서 LDN으로](#653-webmention-에서-ldn로-webmention-to-ldn) 전송할 수 있습니다.

><div id="wm-as2">예시 1</div>
>
>```json
>{
>  "@context": "https://www.w3.org/ns/activitystreams#",
>  "type": "Relationship",
>  "subject": "https://waterpigs.example/post-by-barnaby",
>  "object": "https://aaronpk.example/post-by-aaron"
>}
>```

수신자 또는 송신자는 두 문서 간의 관계 및 기타 관련 데이터로 이 표현을 보강시킬 수 있습니다. 수신자의 경우, 이는 검증 프로세스 중 소스를 구문 분석할 때 수집할 수 있습니다. 예를 들어:

>예시 2
>
>```json
>{
>  "@context": "https://www.w3.org/ns/activitystreams#",
>  "type": "Relationship",
>  "subject": {
>    "id": "https://waterpigs.example/post-by-barnaby",
>    "name": "안녕 Aaron, 굉장한 게시물이야."
>  },
>  "object": {
>    "id": "https://aaronpk.example/post-by-aaron",
>    "name": "Aaron의 첫 게시물."
>  },
>  "relationship": "inReplyTo"
>}
>```

#### 6.5.2 [LDN 에서 Webmention로 (LDN to Webmention)](#65-전달-상호-운용성-delivery-interop)

**Webmention 수신자** 중 Webmention 엔드포인트에서 LDN `POST`를 수락하고자 하는 자는 다음을 반드시 수행해야 합니다:

- `rel="webmention"`(`Link` 헤더, HTML 본문 또는 대상의 JSON 본문) 외에 `rel="http://www.w3.org/ns/ldp#inbox"`을 통해 Webmention 엔드포인트을 알립니다.
- Content-Type `application/ld+json`에서 POST 요청을 수락합니다. 요청 본문은 다음과 같이 예상됩니다:

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

- `source->@id `및 `target-@id` 값을 Webmention의 `source`와 `target` 으로 사용하고 검증을 진행합니다.
- `201 Created`를 반환하는 경우 *반드시* 게시된 요청의 내용을 검색할 수 있는 URL이 포함된 `Location` 헤더를 반환해야 합니다. `202 Accepted`의 경우는 아직은 괜찮습니다.
- 소스를 검증할 때 소스를 RDF로 요청/파싱할 수도 있습니다.

**LDN 발신자** 중 Webmention 엔드포인트로 보내려는 자는 기본적으로 Webmention 전송을 구현하기만 하면 됩니다. Webmention 엔드포인트는 `rel="webmention"`(HTTP `Link` 헤더 또는 HTML `<link>` 요소)에 있습니다.

Webmention 엔드포인트는 `source`가 공개적으로 검색 가능하고 `target`의 URL을 포함하는 경우에만 수신된 알림을 확인합니다.

#### 6.5.3 [Webmention 에서 LDN로 (Webmention to LDN)](#65-전달-상호-운용성-delivery-interop)

**LDN 수신자** 중 인박스에 Webmention을 수신하려는 자는 다음을 수행해야 합니다.

- (`Link` 헤더, HTML 본문 또는 대상의 JSON 본문의) `rel="http://www.w3.org/ns/ldp#inbox"` 외에 `rel="webmention"`을 통해 인박스를 알립니다.
- content type `application/x-www-form-urlencoded`가 있는 `POST` 요청을 수락합니다. 이러한 요청을 다음과 같이 변환합니다:

    >예시 4
    >
    >```lang-none
    >source=https://waterpigs.example/post-by-barnaby&
    >target=https://aaronpk.example/post-by-aaron
    >```

    에서:

    ><div id="wm-json">예시 5</div>
    >
    >```json
    >{
    >  "@context": "http://www.w3.org/ns/webmention#",
    >  "@id": "",
    >  "source": { "@id": "https://waterpigs.example/post-by-barnaby" },
    >  "target": { "@id": "https://aaronpk.example/post-by-aaron" }
    >}
    >```

- 그리고 [[LDN](#ldn)]에 따라 진행하시길 바랍니다; 수신자는 임의로 다른 3배수를 추가 *할 수도* 있습니다.
- 수신자는 *반드시* 위치 헤더로 작성된 201 또는 수락된 202를 반환해야 합니다.
- 수신자는 *반드시* 원본 문서를 검색하고 대상 문서에 대한 링크가 있는지 확인하여 요청을 확인해야 합니다. Webmention이 확인되지 않은 경우 수신자가 Webmention을 *절대* 보관해서는 안 됩니다.

**Webmention 발신자** 중 LDN 인박스로 보내려는 자는 JSON-LD 페이로드를 보내야 합니다. `target`과 인박스 사이의 `http://www.w3.org/ns/ldp#inbox` 관계를 통해 인박스 엔드포인트을 검색합니다. 일반적인 Webmention은 [이 예시](#wm-json)에서는 JSON-LD로, 또는 [이 예시](#wm-as2)에서는 ActivityStreams 2.0 JSON으로 나타낼 수 있습니다.

>참고: 서비스 브릿징하기
>
>Webmention-ActivityPub 브릿지를 서비스로 제공하는걸 고려해보시길 바랍니다. 이렇게 하면 직접 구현하지 않으려는 규격의 무거운 부분들을 수행할 수 있는 엔드포인트를 제공할 수 있습니다. 이러한 엔드포인트를 각각 Webmention 또는 인박스 엔드포인트로 사용할 수 있습니다. 고안 및 이러한 브릿지의 구현은 [Social Web Community Group](https://www.w3.org/wiki/SocialCG)과 [IndieWeb community](https://indieweb.org/bridge#ActivityPub)에서 확인할 수 있습니다.

## 7. [프로필 (Profiles)](#목차-table-of-contents)

프로필(profile) 문서의 주제는 개인(person), 인물(persona), 조직, 봇, 위치 또는 기타 일 수 있습니다. 여기에 설명된 규격 중 실제 개체와 온라인 프로필 간의 특정 관계를 규정하는 것은 없습니다. 즉, 한 사람이 여러 프로필을 가질 수 있고, 한 사람이 여러 프로필을 제어할 수 있습니다. 여러 프로필이 함께 연결되는 방법은 구현마다 다르며 이 문서에서는 기술하지 않습니다.

대부분의 규격에서는 URL에 의해 프로필을 식별하고 검색하며, 해당 URL에서 프로필 대상의 속성을 사용할 수 있을 것으로 예상합니다. 또한 작업 또는 블로그 게시물과 같이 프로필과 관련된 하나 이상의 내용 스트림에 대한 링크를 반환하거나 직접 내용을 포함시키는 것이 좋습니다.

**ActivityPub** 프로필은 적절한 ActivityStreams 2.0 속성과 다양한 엔드포인트 및 컬렉션에 대한 링크가 포함된 JSON-LD 문서입니다([3.3.1 특수 스트림](#331-특별-스트림-special-streams) 참조).

**ActivityStreams 2.0** 에는 개인 또는 그룹을 나타내는 데 사용할 수 있는 다양한 유형의 [액터 타입](https://www.w3.org/TR/activitystreams-core/#actors)이 있으며 `Profile`도 포함됩니다.

**Micropub**에는 사용자를 나타내는 프로필 페이지 (URL) 개념이 있지만, 클라이언트가 검색할 Micropub 엔드포인트와 권한부여 엔드포인트에 대한 링크를 제외하고는 해당 페이지의 형식을 강제하지는 않습니다

**Webmention** 은 특정한 프로필 형식만을 수용하지는 않지만, 실제 Webmention 구현에서는 일반적으로는 [[h-card](#h-card)] 프로필 정보를 게시하고 사용하여 Webmention 소스 작성자를 표시합니다 ([Webmention 규격](https://www.w3.org/TR/webmention/#webmention-verification-p-4) 의 예시 참조).

### 7.1 [관계 (Relationships)](#7-프로필-profiles)

개개인 사이의 시맨틱과 관계에 대한 표현은 구현에 따라 다릅니다. 이러한 규격은 '팔로잉'으로 한 서버에서 다른 서버로 구독 요청을 트리거하는 경우처럼 콘텐츠 배포가 영향을 받는 경우의 관계만 다룹니다. 다른 관계 목록은 사용자 프로필에서 검색할 수 있으며 ActivityStreams 2.0 구문에 따라 표시되어야 하고 필요에 따라 확장 단어를 사용할 수도 있습니다.

- **ActivityPub**: 서버가 `inbox`에서 `Follow` 액티비티를 수신하면 수신자는 제목 프로필에서 검색할 수 있는 `Followers Collection`에 추가됩니다. 연합 서버는 컬렉션 소유자가 새 콘텐츠를 만들 때 이 컬렉션을 통해 업데이트를 제공합니다.

### 7.2 [인증, 권한부여와 액세스 제어 (Authentication, authorization, and access control)](#7-프로필-profiles)

인증 및 인증 메커니즘은 Social Web WG가 다루는 범위를 벗어납니다. 이것과 관련된 개발을 보려면 [커뮤니티 그룹](https://www.w3.org/wiki/SocialCG)을 참조하시길 바랍니다. 한편, 일부 WG 규격에는 위와 같은 주제에 대한 비표준적인 참고사항들이 포함되어 있습니다:

- **ActivityPub**: [B.1 인증 및 권한부여](https://www.w3.org/TR/activitypub/#authorization)의 커뮤니티 그룹 모범 사례 보고서를 가리킵니다.
- **LDN**: 수신자에게 [3.3.3 전송자 확인](https://www.w3.org/TR/ldn/#sender-verification)에서 인증될 수 있는 일종의 확인 메커니즘을 사용하고, [5.6 인증받은 인박스](https://www.w3.org/TR/ldn/#authenticated-inboxes)에 기재된 추가적인 보안 고려사항을 적용할 것을 권장합니다.
- **Micropub**: [5. 인증 및 권한부여](https://www.w3.org/TR/micropub/#authentication-and-authorization)에서 운반 토큰(bearer tokens)이 필요한 IndieAuth를 제안합니다.
- **Webmention**: [B.3 비공개 Webmention](https://www.w3.org/TR/webmention/#private-webmention)에서 액세스 제어 게시물과 함께 사용할 수 있는 확장을 가리킵니다.
- **WebSub**: [8.1 인증된 컨텐츠 배포](https://www.w3.org/TR/websub/#authenticated-content-distribution)에서 HMAC 서명을 선택적으로 사용하는 방법에 대해 설명합니다.

## 8. 관련된 규격들 (Related specifcations)

Social Web Working Group의 결과물과 관련된, 언급할 가치가 있는 다른 규격들은 다음과 같습니다.

Social Web Working Group 참고사항:

- **[[IndieAuth](#indieauth)]**: 는 OAuth 2 위에 있는 신원 계층(identity layer)이며 Microub 클라이언트가 사용하리라 예상되는 인증 메커니즘입니다.
- **[[JF2](#jf2)]**:는 [[microformats2](#microformats2)]에서 파생된 소셜 콘텐츠의 대체 JSON 구문입니다. 이는 개별 객체와 피드를 포함합니다. ActivityStreams 2.0 이 마음에 들지 않으면 대신 이 옵션을 사용할 수도 있습니다. 작성 당시 이 문서는 다른 소셜 웹 작업 그룹 규격에서 참조하지 않았습니다.
- **[[post-type-properties](#post-type-discovery)]**: 속성을 기준으로 게시 유형을 결정하는 알고리즘을 지정합니다. 이는 [[microformats2](#microformats2)]로 표시된 내용과 ActivityStreams 2.0 과 같이 명시적으로 입력된 어휘 사이에 브릿징하는 데 도움이 될 수도 있습니다.

외부:

- **[[LDP](#ldp)]**: 는 Social Web Working Group 헌장을 작성하는데 사용되었습니다. LDP 서버의 `Container`는 가지고 있는 경우 LDN 수신기로 직접 사용할 수 있습니다. Web Annotation Protocol도 LDP를 기반으로 합니다.
- **[[microformats2](#microformats2)]**: 는 HTML로 구조화된 정보를 표시하는 방법입니다. Micropub는 microformats2 어휘를 사용하는것으로 간주되며, Webmention 수신기 구현은 종종 소스에 대한 더 많은 정보를 가져오기 위해 microformats2 마크업을 찾아봅니다.
- **[[annotation-protocol](#annotation-protocol)]**: 는 ActivityStreams 2.0 수집 및 페이징을 사용하여 주석 집합을 모델링합니다. 주석 자체는 [[annotation-vocab](#annotation-vocab)]을 사용합니다.

[Social Web Community Group](https://www.w3.org/wiki/SocialCG)과 [IndieWeb](https://indieweb.org/) 등 다양한 커뮤니티에서 관련 규격의 개발이 진행 중입니다.

## A. [변경사항 (Change Log)](#목차-table-of-contents)

### A.1 [2017년 5월 4일 WD에서 이 버전으로의 변경사항 (Changes from 4 May 2017 WD to this version)](#a-변경사항-change-log)

- 전체적으로 편집을 개선했습니다.
- 뒤처진 모든(대부분 Micropub) 규격의 기능을 업데이트 했습니다.
- 요구사항 정의를 추가하여 각 규격이 규격의 하단에 열거된 섹션 및 헌장 결과물과의 관계를 명확히 했습니다.
- Federation Protocols와 Social API 부분(예: 새로운 알림을 트리거하는 업데이트 등)의 관련성을 명확히 했습니다.
- AP와 Webmention에 대한 업데이트 및 삭제에 대해 더욱 자세하게 풀어썼습니다.
- 프로필은 이제 각 규격의 프로필 사용 또는 예상에 대해 설명합니다.
- Auth 섹션은 이제 각 규격의 개별적인 관련된 부분들과 연결됩니다.
- 관련된 규격들 섹션을 추가했습니다.

### A.2 [2016년 11월 16일 WD에서 이 버전으로의 변경사항 (Changes from 16 November 2016 WD to this version)](#a-변경사항-change-log)

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

- 최근에 게시된 초안의 문서 상태를 업데이트했습니다.

### A.4 [2016년 10월 12일 WD에서 이 버전으로의 변경사항 (Changes from 12 October 2016 WD to this version)](#a-변경사항-change-log)

- WebSub가 FPWD로 게시된 이후 업데이트 했습니다.

### A.5 [2016년 8월 23일 버전에서 2016년 10월 12일 버전으로의 변경사항 (Changes from 23 August to 12 October 2016)](#a-변경사항-change-log)

- "백오프(backoff)" 전략 조언을 포함하여 타겟팅 및 검색 섹션이 추가했습니다.

### A.6 [2016년 6월 3일 버전에서 2016년 8월 23일 버전으로의 변경사항 (Changes from 3 June to 23 August 2016)](#a-변경사항-change-log)

- JF2, PTD, LDN, PuSH 그룹에 의해 게시된 새 WG 초안을 추가했습니다.
- 기존 WG 초안이 진행되어서 등록 상태를 업데이트했습니다.
- 배송 및 판독(Delivery and Reading)에서 LDN에 대해 설명했습니다.
- 구독 및 배달(Subscribing and Delivery)에서 PuSH에 대해 설명했습니다.
- 배달 상호 운용성은 다음과 같습니다:
  - Webmention 송신자/수신자 및 LDN 송신자/수신자가 브릿지를 구현하는 방법입니다.
  - Webmention을 AS2 관계로 표현하는 방법입니다.
- 구독 및 읽기(Refactor Subscripting and Reading)를 리팩터링하여 WG 규격의 우선순위를 정하고 이들 사이의 관계를 명확히 헀습니다.
- 소개 및 개요(introductory and overview) 텍스트에 대해 편집을 개선했습니다.

## B. [참고 문헌 (References)](#목차-table-of-contents)

### B.1 [정보 참고 문헌 (Informative references)](#b-참고-문헌-references)

#### [Accept-Post]

- [*The Accept-Post HTTP Header.*](http://tools.ietf.org/html/draft-wilde-accept-post). J. Arwe; S. Speicher; E. Wilde. IETF. Internet Draft. URL: http://tools.ietf.org/html/draft-wilde-accept-post 

#### [Activitypub]

- [*ActivityPub*](https://www.w3.org/TR/activitypub/). Christopher Webber; Jessica Tallon. W3C. 5 December 2017. W3C Proposed Recommendation. URL: https://www.w3.org/TR/activitypub/ 

#### [activitystreams-core]

- [*Activity Streams 2.0*](https://www.w3.org/TR/activitystreams-core/). James Snell; Evan Prodromou. W3C. 23 May 2017. W3C Recommendation. URL: https://www.w3.org/TR/activitystreams-core/ 

#### [activitystreams-vocabulary]

- [*Activity Vocabulary*](https://www.w3.org/TR/activitystreams-vocabulary/). James Snell; Evan Prodromou. W3C. 23 May 2017. W3C Recommendation. URL: https://www.w3.org/TR/activitystreams-vocabulary/ 

#### [annotation-protocol]

- [*Web Annotation Protocol*](https://www.w3.org/TR/annotation-protocol/). Robert Sanderson. W3C. 23 February 2017. W3C Recommendation. URL: https://www.w3.org/TR/annotation-protocol/ 

#### [annotation-vocab]

- [*Web Annotation Vocabulary*](https://www.w3.org/TR/annotation-vocab/). Robert Sanderson; Paolo Ciccarese; Benjamin Young. W3C. 23 February 2017. W3C Recommendation. URL: https://www.w3.org/TR/annotation-vocab/ 

#### [AS1]

- [*JSON Activity Streams 1.0.*](http://activitystrea.ms/specs/json/1.0/). J. Snell; M. Atkins; W. Norris; C. Messina; M. Wilkinson; R. Dolin. http://activitystrea.ms. Unofficial. URL: http://activitystrea.ms/specs/json/1.0/ 

#### [h-card]

- [*h-card*](http://microformats.org/wiki/h-card). Tantek Çelik. microformats.org. Living Specification. URL: http://microformats.org/wiki/h-card 

#### [h-entry]

- [*h-entry*](http://microformats.org/wiki/h-entry). Tantek Çelik. microformats.org. Living Specification. URL: http://microformats.org/wiki/h-entry 

#### [IndieAuth]

- [*IndieAuth*](https://www.w3.org/TR/indieauth). Aaron Parecki. W3C. Note. URL: https://www.w3.org/TR/indieauth 

#### [JF2]

- [*JF2 Post Serialization Format*](https://www.w3.org/TR/jf2/). Benjamin Roberts. W3C. 26 October 2017. W3C Working Draft. URL: https://www.w3.org/TR/jf2/ 

#### [LDN]

- [*Linked Data Notifications*](https://www.w3.org/TR/ldn/). Sarven Capadisli; Amy Guy. W3C. 2 May 2017. W3C Recommendation. URL: https://www.w3.org/TR/ldn/ 

#### [LDP]

- [*Linked Data Platform 1.0*](https://www.w3.org/TR/ldp/). Steve Speicher; John Arwe; Ashok Malhotra. W3C. 26 February 2015. W3C Recommendation. URL: https://www.w3.org/TR/ldp/ 

#### [microformats2]

- [*Microformats2*](https://microformats.org/wiki/microformats2). Tantek Çelik. https://microformats.org. Living specification. URL: https://microformats.org/wiki/microformats2 

#### [microformats2-parsing]

- [*microformats2 parsing*](http://microformats.org/wiki/microformats2-parsing). Tantek Çelik. microformats.org. Living Specification. URL: http://microformats.org/wiki/microformats2-parsing 

#### [Micropub]

- [*Micropub*](https://www.w3.org/TR/micropub/). Aaron Parecki. W3C. 23 May 2017. W3C Recommendation. URL: https://www.w3.org/TR/micropub/ 

#### [post-type-discovery]

- [*Post Type Discovery*](https://www.w3.org/TR/post-type-discovery/). Tantek Çelik. W3C. 1 August 2017. W3C Working Draft. URL: https://www.w3.org/TR/post-type-discovery/ 

#### [SHACL]

- [*Shapes Constraint Language (SHACL)*](https://www.w3.org/TR/shacl/). Holger Knublauch; Dimitris Kontokostas. W3C. 20 July 2017. W3C Recommendation. URL: https://www.w3.org/TR/shacl/ 

#### [Webmention]

- [*Webmention*](https://www.w3.org/TR/webmention/). Aaron Parecki. W3C. 12 January 2017. W3C Recommendation. URL: https://www.w3.org/TR/webmention/ 

#### [WebSub]

- [*WebSub*](https://www.w3.org/TR/websub/). Julien Genestoux; Aaron Parecki. W3C. 3 October 2017. W3C Proposed Recommendation. URL: https://www.w3.org/TR/websub/ 

[맨 위로](#소셜-웹-프로토콜-social-web-protocols)
