[목차로 돌아가기](SocialWebProtocolsContents.md)

## 2. Overview

People and the content they create are the core components of the social web; they make up the social graph. This document describes a standard way in which people can:

- create, update and delete social content;
- connect with other people by subscribing to their content;
- interact with other peoples' content;
- be notified when other people interact with their content.

regardless of _what that content_ is or _where it is stored_.

These components are core building blocks for interoperable decentralised social systems.

Each of these components can be implemented independently as needed, or all together in one system, as well as extended to meet domain-specific requirements. Users can store their social data across any number of compliant servers, and use compliant clients hosted elsewhere to interact with their own content and the content of others.

The [Social Web Working Group Charter](https://www.w3.org/2013/socialweb/social-wg-charter) proposes the following deliverables, which have been met by the Group, and will be referred to throughout this document:

**Social Data Syntax**

- A JSON-based syntax to allow the transfer of social information, such as status updates, across differing social systems.

**Social API**

- A document that defines a specification for a client-side API that lets developers embed and format third party information such as social status updates.

**Federation Protocol**

- A Web protocol to allow the federation of activity-based status updates and other data (such as profile information) between heterogeneous Web-based social systems. Federation should include multiple servers sharing updates within a client-server architecture, and allow decentralized social systems to be built.

### 2.1 Contents

This is an overview of the specifications of the Social Web Working Group.

Due to the diversity of viable technical approaches proposed within the Working Group, several specifications reached recommendation which provide overlapping functionality through differing mechanisms. This document exists to provide informative guidance on how and when to implement the various specifications, as well as some hints towards routes to bridging between similar specifications.

### 2.2 Definitions

This document is divided into five sections, pertaining to the components above, and derived from the [Social API Requirements](https://www.w3.org/wiki/Socialwg/Social_API/Requirements). The various Social Web Working Group specifications implement different combinations of these requirements (see [2.3.1 Requirements](https://www.w3.org/TR/social-web-protocols/#requirements)) so for clarity the requirement are defined here.

**[reading](https://www.w3.org/TR/social-web-protocols/#reading)**

- covers specifications which describe the syntax and vocabulary to be used for social content. Useful for applications which expose feeds, as well as those which consume them.

**publishing**

- covers Social API specifications which tell clients how to instruct servers to [create](https://www.w3.org/TR/social-web-protocols/#publishing), [update](https://www.w3.org/TR/social-web-protocols/#updating) or [delete](https://www.w3.org/TR/social-web-protocols/#deleting) content.

**[subscribing](https://www.w3.org/TR/social-web-protocols/#subscribing)**

- covers Federation Protocol specifications which describe how to ask for notifications about content, and subsequently how those notifications should be delivered.

**[delivery](https://www.w3.org/TR/social-web-protocols/#delivery)**

- covers Federation Protocol specifications which describe how to deliver notifications which have not been solicited through subscription.

**[profiles](https://www.w3.org/TR/social-web-protocols/#delivery)**

- covers specifications which describe profiles.

### 2.3 Specifications

These are the specifications produced by the Social Web Working Group. New implementation reports and feedback are always welcome (details for where to submit these are at the top of each document).

**[[Activitypub](https://www.w3.org/TR/social-web-protocols/#bib-Activitypub)]**

- JSON(-LD)-based APIs for client-to-server interactions (ie. publishing) and server-to-server interactions (ie. federation).

**ActivityStreams 2.0 [[activitystreams-core](https://www.w3.org/TR/social-web-protocols/#bib-activitystreams-core)] and [[activitystreams-vocabulary](https://www.w3.org/TR/social-web-protocols/#bib-activitystreams-vocabulary)]**

- The syntax and vocabulary for [representing](https://www.w3.org/TR/social-web-protocols/#reading) social activities, actors, objects, and collections in JSON(-LD).

**Linked Data Notifications ([[LDN](https://www.w3.org/TR/social-web-protocols/#bib-LDN)])**

- A JSON-LD-based protocol for [delivery](https://www.w3.org/TR/social-web-protocols/#delivery).

**[[Micropub](https://www.w3.org/TR/social-web-protocols/#bib-Micropub)]**

- A form-encoding and JSON-based API for client-to-server interactions (ie. publishing).

**[[Webmention](https://www.w3.org/TR/social-web-protocols/#bib-Webmention)]**

- A form-encoding-based protocol for [delivery](https://www.w3.org/TR/social-web-protocols/#delivery).

**[[WebSub](https://www.w3.org/TR/social-web-protocols/#bib-WebSub)]**

- A protocol for [subscription](https://www.w3.org/TR/social-web-protocols/#subscribing) to any resource and [delivery](https://www.w3.org/TR/social-web-protocols/#delivery) of updates about it.

Specifications which are not Social Web Working Group recommendations, but which are nonetheless relevent to the charter deliverables, are described in [8. Related specifcations](https://www.w3.org/TR/social-web-protocols/#related-specs).

### 2.3.1 Requirements

This table shows the high level requirements according to the [Social Web Working Group charter](https://www.w3.org/2013/socialweb/social-wg-charter.html) and the [Social API Requirements](https://www.w3.org/wiki/Socialwg/Social_API/Requirements), and how the specifications of the Working Group overlap with respect to each.

This table lists the requirements met by the core functionality of each specification. Some specifications may additionally touch on or make suggestions about other requirements, which can be useful when deciding how to combine specifications, and is highlighted as appropriate throughout this document.

<table class="th90">
    <tbody>
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
    </tbody>
</table>

### 2.3.2 How do these specifications relate to each other?

As a quick reference, some key relationships between specifications are as follows:

- **ActivityPub and ActivityStreams 2.0**: ActivityPub uses the AS2 syntax and vocabulary for the payload of all requests.
- **ActivityPub and Linked Data Notifications**: ActivityPub specialises LDN as the mechanism for delivery of notifications by requiring that payloads are AS2. _Inbox_ endpoint discovery is the same. LDN receivers can understand requests from ActivityPub federated servers, but ActivityPub servers can't necessarily understand requests from generic LDN senders.
- **ActivityStreams 2.0 and Linked Data Notifications**: LDN *MAY* use the AS2 syntax and vocabulary for the payload of notification requests.
- **Webmention and Linked Data Notifications**: Overlapping functionality that needs to be bridged due to different content types of requests. An LDN request *MAY* contain the equivalent data as a Webmention request, but not necessarily vice versa.
- **ActivityPub and Micropub**: Overlapping functionality that needs to be bridged due to different vocabularies and possibly different content types of requests. Micropub specifies client-to-server interactions for content creation; ActivityPub specifies this, _plus_ side-effects and server-to-server interactions.
- **Micropub and Webmention**: Are complementary but independent. Content can be created with Micropub, then Webmentions can be sent to any URLs referenced by the content.
- **Micropub and Linked Data Notifications**: Are complementary but independent. Content can be created with Micropub, then LDN discovery can be commenced on any relevant resources referenced by the content.
- **Micropub and WebSub**: Are complementary but independent. Content can be created with Micropub, then a WebSub _hub_ can handle delivery to subscribers.
- **ActivityPub and WebSub**: Overlapping functionality using different content types and verification mechanisms.
