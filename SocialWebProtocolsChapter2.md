[목차로 돌아가기](SocialWebProtocolsContents.md)

## 2. [개요 (Overview)](SocialWebProtocolsContents.md#목차-table-of-contents)

People and the content they create are the core components of the social web; they make up the social graph. This document describes a standard way in which people can:

사람들과 그들이 만든 콘텐츠는 소셜 웹의 핵심 요소입니다; 이들은 소셜 그래프를 구성하죠. 이 문서에서는 사용자가 다음을 수행할 수 있는 표준적인 방법을 설명합니다:

- create, update and delete social content;
- connect with other people by subscribing to their content;
- interact with other peoples' content;
- be notified when other people interact with their content.

[//Comment]: # "BLANK"

- 소셜 컨텐츠를 작성, 업데이트 및 삭제합니다;
- 자신의 컨텐츠에 가입하여 다른 사용자와 연결합니다;
- 다른 사람들의 컨텐츠와 상호작용합니다;
- 다른 사람들이 자신의 컨텐츠와 상호작용할 때 알림을 받습니다.

regardless of _what that content_ is or _where it is stored_.

위 사항은 _콘텐츠가 무엇인지_, _컨텐츠가 저장된 위치가 어디인지_ 랑 관계없이 언제든지 해당됩니다.

These components are core building blocks for interoperable decentralised social systems.

이러한 요소들은 상호운용 가능한 분산형 소셜 시스템을 구성하는 핵심 구성 요소입니다.

Each of these components can be implemented independently as needed, or all together in one system, as well as extended to meet domain-specific requirements. Users can store their social data across any number of compliant servers, and use compliant clients hosted elsewhere to interact with their own content and the content of others.

이러한 각 구성요소는 필요에 따라 독립적으로 구현하거나, 한 시스템에서 모두 함께 구현될 수 있을 뿐만 아니라 도메인별 요구사항을 충족하도록 확장할 수 있습니다. 사용자는 원하는 수의 호환 서버에 소셜 데이터를 저장할 수 있으며, 다른 곳에서 호스팅되는 호환 클라이언트를 사용하여 자신의 컨텐츠 및 다른 사용자의 컨텐츠와 상호 작용할 수 있습니다.

The [Social Web Working Group Charter](https://www.w3.org/2013/socialweb/social-wg-charter) proposes the following deliverables, which have been met by the Group, and will be referred to throughout this document:

[Social Web Working Group 헌장](https://www.w3.org/2013/socialweb/social-wg-charter)은 이 그룹이 검토한 다음과 같은 결과물을 제안하며, 이 문서 전반에 걸쳐 참조할 예정입니다:

**Social Data Syntax**

- A JSON-based syntax to allow the transfer of social information, such as status updates, across differing social systems.

**소셜 데이터 구문 (Social Data Syntax)**

JSON 기반 구문을 사용하여 상태 업데이트와 같은 소셜 정보를 서로 다른 소셜 시스템들을 거쳐 전송할 수 있습니다.

**Social API**

- A document that defines a specification for a client-side API that lets developers embed and format third party information such as social status updates.

**소셜 API (Social API)**

개발자가 소셜 상태 업데이트 같은 제3자 정보를 포함 및 정제할 수 있는 클라이언트측 API의 규격을 정의하는 문서입니다.

**Federation Protocol**

- A Web protocol to allow the federation of activity-based status updates and other data (such as profile information) between heterogeneous Web-based social systems. Federation should include multiple servers sharing updates within a client-server architecture, and allow decentralized social systems to be built.

**연합 프로토콜 (Federation Protocol)**

서로 다른 웹 기반 소셜 시스템 간에 액티비티-기반 상태 업데이트 및 (프로필 정보 같은) 기타 데이터를 결합할 수 있는 웹 프로토콜입니다. 연합은 클라이언트-서버 아키텍처 내에 업데이트를 공유하는 여러 서버를 포함해야 하며 분산형 사회 시스템을 구축할 수 있어야 합니다.

### 2.1 [컨텐츠 (Contents)](#2-개요-overview)

This is an overview of the specifications of the Social Web Working Group.

Social Web Working Group 규격의 개요입니다.

Due to the diversity of viable technical approaches proposed within the Working Group, several specifications reached recommendation which provide overlapping functionality through differing mechanisms. This document exists to provide informative guidance on how and when to implement the various specifications, as well as some hints towards routes to bridging between similar specifications.

Working Group 내에서 제안된 실행 가능한 기술 접근법의 다양성 때문에 여러 가지 명세서가 서로 다른 메커니즘을 통해 중복되는 기능을 제공하는 권장 사항에 도달했습니다. 이 문서는 다양한 규격을 구현하는 방법과 시기에 대한 유용한 지침과, 유사한 규격들을 연결하기 위한 방법에 대한 힌트를 제공하기 위해 존재합니다.

### 2.2 [정의 (Definitions)](#2-개요-overview)

This document is divided into five sections, pertaining to the components above, and derived from the [Social API Requirements](https://www.w3.org/wiki/Socialwg/Social_API/Requirements). The various Social Web Working Group specifications implement different combinations of these requirements (see [2.3.1 Requirements](https://www.w3.org/TR/social-web-protocols/#requirements)) so for clarity the requirement are defined here.

이 문서는 위의 구성 요소와 관련된 5개의 섹션으로 나뉘며, [소셜 API 요구사항](https://www.w3.org/wiki/Socialwg/Social_API/Requirements) 에서 파생됩니다. 다양한 Social Web Working Group 규격들은 이러한 요구 사항의 서로 다른 조합들로 구성되기 때문에([2.3.1 요구 사항](https://www.w3.org/TR/social-web-protocols/#requirements) 참조) 여기에서는 요구사항을 명확하게 정의합니다.

**[reading](https://www.w3.org/TR/social-web-protocols/#reading)**

- covers specifications which describe the syntax and vocabulary to be used for social content. Useful for applications which expose feeds, as well as those which consume them.

**[읽기 (reading)](https://www.w3.org/TR/social-web-protocols/#reading)**

소셜 콘텐츠에 사용할 구문과 어휘를 설명하는 규격을 다룹니다. 피드를 노출하는 응용 프로그램뿐만 아니라 피드를 소비하는 응용 프로그램에 유용합니다.

**publishing**

- covers Social API specifications which tell clients how to instruct servers to [create](https://www.w3.org/TR/social-web-protocols/#publishing), [update](https://www.w3.org/TR/social-web-protocols/#updating) or [delete](https://www.w3.org/TR/social-web-protocols/#deleting) content.

**게시 (publishing)**

서버에 [create](https://www.w3.org/TR/social-web-protocols/#publishing), [update](https://www.w3.org/TR/social-web-protocols/#updating) 또는 [delete](https://www.w3.org/TR/social-web-protocols/#deleting)를 지시하는 방법을 고객에게 알려주는 소셜 API 규격을 다룹니다.

**[subscribing](https://www.w3.org/TR/social-web-protocols/#subscribing)**

- covers Federation Protocol specifications which describe how to ask for notifications about content, and subsequently how those notifications should be delivered.

**[구독 (subscribing)](https://www.w3.org/TR/social-web-protocols/#subscribing)**

- 콘텐츠에 대한 알림을 요청하는 방법과 요청후 알림을 전달하는 방법을 설명하는 연합 프로토콜 규격이 나와 있습니다.

**[delivery](https://www.w3.org/TR/social-web-protocols/#delivery)**

- covers Federation Protocol specifications which describe how to deliver notifications which have not been solicited through subscription.

**[전달 (delivery)](https://www.w3.org/TR/social-web-protocols/#delivery)**

- 구독을 통해 요청되지 않은 알림를 전달하는 방법을 설명하는 연합 프로토콜 규격을 다룹니다.

**[profiles](https://www.w3.org/TR/social-web-protocols/#delivery)**

- covers specifications which describe profiles.

**[프로필 (profiles)](https://www.w3.org/TR/social-web-protocols/#delivery)**

- 프로필을 설명하는 규격을 다룹니다.

### 2.3 [규격 (Specifications)](#2-개요-overview)

These are the specifications produced by the Social Web Working Group. New implementation reports and feedback are always welcome (details for where to submit these are at the top of each document).

아래의 항목들은 Social Web Working Group 에서 제작한 규격들입니다. 새로운 구현 보고서 및 피드백은 언제든지 환영합니다 (각 문서의 맨 위에 이러한 보고서를 제출할 곳에 대한 세부 정보가 있습니다).

**[[Activitypub](https://www.w3.org/TR/social-web-protocols/#bib-Activitypub)]**

- JSON(-LD)-based APIs for client-to-server interactions (ie. publishing) and server-to-server interactions (ie. federation).

- 클라이언트-서버간 상호 작용(예: 게시) 및 서버-서버간 상호 작용(즉, 연합)을 위한 JSON(-LD) 기반 API입니다.

**ActivityStreams 2.0 [[activitystreams-core](https://www.w3.org/TR/social-web-protocols/#bib-activitystreams-core)] 와 [[activitystreams-vocabulary](https://www.w3.org/TR/social-web-protocols/#bib-activitystreams-vocabulary)]**

- The syntax and vocabulary for [representing](https://www.w3.org/TR/social-web-protocols/#reading) social activities, actors, objects, and collections in JSON(-LD).

- JSON(-LD)에서 소셜 액티비티, 액터, 객체 및 컬렉션을 [나타내는](https://www.w3.org/TR/social-web-protocols/#reading) 구문과 어휘입니다.

**Linked Data Notifications ([[LDN](https://www.w3.org/TR/social-web-protocols/#bib-LDN)])**

- A JSON-LD-based protocol for [delivery](https://www.w3.org/TR/social-web-protocols/#delivery).

- [전송](https://www.w3.org/TR/social-web-protocols/#delivery)을 위한 JSON-LD 기반 프로토콜입니다.

**[[Micropub](https://www.w3.org/TR/social-web-protocols/#bib-Micropub)]**

- A form-encoding and JSON-based API for client-to-server interactions (ie. publishing).

- 클라이언트-서버 간 상호 작용(예: 게시)을 위한 폼-인코딩 및 JSON 기반 API입니다.

**[[Webmention](https://www.w3.org/TR/social-web-protocols/#bib-Webmention)]**

- A form-encoding-based protocol for [delivery](https://www.w3.org/TR/social-web-protocols/#delivery).

- [전송](https://www.w3.org/TR/social-web-protocols/#delivery)을 위한 폼-인코딩 기반 프로토콜입니다.

**[[WebSub](https://www.w3.org/TR/social-web-protocols/#bib-WebSub)]**

- A protocol for [subscription](https://www.w3.org/TR/social-web-protocols/#subscribing) to any resource and [delivery](https://www.w3.org/TR/social-web-protocols/#delivery) of updates about it.

- 모든 리소스에 [구독](https://www.w3.org/TR/social-web-protocols/#subscribing) 하고 리소스에 대한 업데이트를 [전달](https://www.w3.org/TR/social-web-protocols/#delivery)하기 위한 프로토콜입니다.

Specifications which are not Social Web Working Group recommendations, but which are nonetheless relevent to the charter deliverables, are described in [8. Related specifcations](https://www.w3.org/TR/social-web-protocols/#related-specs).

Social Web Working Group의 권장사항은 아니지만 헌장 자료와 관련된 규격은 [8. 관련 규격](https://www.w3.org/TR/social-web-protocols/#related-specs)에 설명되어 있습니다.

### 2.3.1 [요구사항 (Requirements)](#23-규격-specifications)

This table shows the high level requirements according to the [Social Web Working Group charter](https://www.w3.org/2013/socialweb/social-wg-charter.html) and the [Social API Requirements](https://www.w3.org/wiki/Socialwg/Social_API/Requirements), and how the specifications of the Working Group overlap with respect to each.

이 표는 [Social Web Working Group 헌장](https://www.w3.org/2013/socialweb/social-wg-charter.html)와 [소셜 API 요구사항](https://www.w3.org/wiki/Socialwg/Social_API/Requirements)에 따른 상위 수준의 요구사항 및 Working Group 의 규격과 각 요구 사항들이 어떻게 서로 중첩되는지를 보여줍니다.

This table lists the requirements met by the core functionality of each specification. Some specifications may additionally touch on or make suggestions about other requirements, which can be useful when deciding how to combine specifications, and is highlighted as appropriate throughout this document.

이 표에는 각 규격의 핵심 기능에서 충족되는 요구 사항이 나열되어 있습니다. 일부 규격은 규격을 결합하는 방법을 결정할 때 유용할 수 있으며 본 문서 전체에 걸쳐 적절하게 강조 표시되어 있는 다른 요구 사항에 대해 추가적으로 언급하거나 제안할 수 있습니다.

<table class="th90"><tbody>
<tr>
    <td></td>
    <td colspan="3">Data syntax</td>
    <td colspan="4">Social API</td>
    <td colspan="2">Federation Protocol</td>
    <td></td>
</tr>
<tr>
    <th></th>
    <th><a href="#content-representation">Vocabulary</a></th>
    <th><a href="#content-representation">Syntax</a></th>
    <th><a href="#profiles">Profiles</a></th>
    <th><a href="#reading">Read</a></th>
    <th><a href="#publishing">Create</a></th>
    <th><a href="#updating">Update</a></th>
    <th><a href="#deleting">Delete</a></th>
    <th><a href="#subscribing">Subscription</a></th>
    <th><a href="#delivery">Delivery</a></th>
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

[//Comment]: # "BLANK"

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

As a quick reference, some key relationships between specifications are as follows:

간략하게나마, 규격 간 주요 관계는 다음과 같습니다:

[//Comment]: # "5개씩 끊어서"

- **ActivityPub and ActivityStreams 2.0**: ActivityPub uses the AS2 syntax and vocabulary for the payload of all requests.
- **ActivityPub and Linked Data Notifications**: ActivityPub specialises LDN as the mechanism for delivery of notifications by requiring that payloads are AS2. _Inbox_ endpoint discovery is the same. LDN receivers can understand requests from ActivityPub federated servers, but ActivityPub servers can't necessarily understand requests from generic LDN senders.
- **ActivityStreams 2.0 and Linked Data Notifications**: LDN *MAY* use the AS2 syntax and vocabulary for the payload of notification requests.
- **Webmention and Linked Data Notifications**: Overlapping functionality that needs to be bridged due to different content types of requests. An LDN request *MAY* contain the equivalent data as a Webmention request, but not necessarily vice versa.
- **ActivityPub and Micropub**: Overlapping functionality that needs to be bridged due to different vocabularies and possibly different content types of requests. Micropub specifies client-to-server interactions for content creation; ActivityPub specifies this, _plus_ side-effects and server-to-server interactions.

[//Comment]: # "BLANK"

- **ActivityPub 와 ActivityStreams 2.0**: ActivityPub은 모든 요청의 페이로드에 AS2 구문과 어휘를 사용합니다.
- **ActivityPub 와 Linked Data Notifications**: ActivityPub에서는 페이로드를 AS2로 요구하여 LDN을 알림 전달 메커니즘으로만 사용합니다. _인박스_ 엔드포인트 검색방식은 동일합니다. LDN 수신자는 ActivityPub 연합 서버의 요청을 이해할 수 있지만, ActivityPub 서버는 일반적인 LDN 전달자의 요청을 이해하지 못할 수도 있습니다.
- **ActivityStreams 2.0 와 Linked Data Notifications**: LDN은 알림 요청 페이로드에 AS2 구문과 어휘를 사용 *할 수도* 있습니다.
- **Webmention 와 Linked Data Notifications**: 서로 다른 유형의 요청들로 인해 브릿지해야 하는 중복되는 기능입니다. LDN 요청은 Webmention 요청과 동일한 데이터를 포함 *할 수도* 있지만, 반드시 그 반대일 필요는 없습니다.
- **ActivityPub 와 Microub**: 서로 다른 어휘와 서로 다른 유형의 요청들로 인해 브릿지해야 하는 중복되는 기능입니다. Micropub는 컨텐츠 작성을 위해 클라이언트-서버간 상호 작용을 하지만; 액티비티펍은 위의 기능과 _함께_ 부작용과 서버-서버간 상호 작용에도 사용합니다.

[//Comment]: # "5개씩 끊어서"

- **Micropub and Webmention**: Are complementary but independent. Content can be created with Micropub, then Webmentions can be sent to any URLs referenced by the content.
- **Micropub and Linked Data Notifications**: Are complementary but independent. Content can be created with Micropub, then LDN discovery can be commenced on any relevant resources referenced by the content.
- **Micropub and WebSub**: Are complementary but independent. Content can be created with Micropub, then a WebSub _hub_ can handle delivery to subscribers.
- **ActivityPub and WebSub**: Overlapping functionality using different content types and verification mechanisms.

[//Comment]: # "BLANK"

- **Micropub 와 Webmention**: 는 상호 보완적이지만 독립적입니다. Micropub로 콘텐츠를 만든 다음 콘텐츠에서 참조하는 모든 URL로 Webmentions를 보낼 수 있습니다.
- **Micropub 와 Linked Data Notifications**: 는 상호 보완적이지만 독립적입니다. Micropub로 콘텐츠를 만든 다음, 콘텐츠에서 참조하는 모든 관련 리소스에서 LDN 검색을 시작할 수 있습니다.
- **Micropub 와 WebSub**: 는 상호 보완적이지만 독립적입니다. Microub로 콘텐츠를 만든 다음 WebSub _허브(hub)_ 가 구독자에 대한 전달을 처리할 수 있습니다.
- **ActivityPub 와 WebSub**: 서로 다른 컨텐츠 유형 및 검증 메커니즘을 사용하여 중복되는 기능을 제공합니다.

[맨 위로](#2-개요-overview)
