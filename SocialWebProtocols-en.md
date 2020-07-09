[목차로 돌아가기](SocialWebProtocolsContents.md)

# [Social Web Protocols](https://www.w3.org/TR/social-web-protocols/)

<abbr title="World Wide Web Consortium">W3C</abbr> Working Group Note 25 December 2017

**This version:**
- https://www.w3.org/TR/2017/NOTE-social-web-protocols-20171225/

**Latest published version:**
- https://www.w3.org/TR/social-web-protocols/

**Latest editor's draft:**
- https://w3c-social.github.io/social-web-protocols

**Previous version:**
- https://www.w3.org/TR/2017/WD-social-web-protocols-20170504/

**Editor:**
- [Amy Guy](http://rhiaro.co.uk/), [University of Edinburgh](http://inf.ed.ac.uk/), amy@rhiaro.co.uk

**Repository:**
- [Git repository](https://github.com/w3c-social/social-web-protocols)
- [Issues](https://github.com/w3c-social/social-web-protocols/issues)
- [Commits](https://github.com/w3c-social/social-web-protocols/gh-pages)

[Copyright](https://www.w3.org/Consortium/Legal/ipr-notice#Copyright) © 2017 [<abbr title="World Wide Web Consortium">W3C</abbr>](https://www.w3.org/)® (<abbr title="Massachusetts Institute of Technology">[MIT](https://www.csail.mit.edu/)</abbr>, <abbr title="European Research Consortium for Informatics and Mathematics">[ERCIM](https://www.ercim.eu/)</abbr>, [Keio](https://www.keio.ac.jp/), [Beihang](http://ev.buaa.edu.cn/)). <abbr title="World Wide Web Consortium">W3C</abbr> [liability](https://www.w3.org/Consortium/Legal/ipr-notice#Legal_Disclaimer), [trademark](https://www.w3.org/Consortium/Legal/ipr-notice#W3C_Trademarks) and [permissive document license](https://www.w3.org/Consortium/Legal/2015/copyright-software-and-document) rules apply.

-----

## Abstract

The Social Web Protocols are a collection of standards which enable various aspects of decentralised social interaction on the Web. This document describes the purposes of each, and how they fit together.

## Status of This Document

_This section describes the status of this document at the time of its publication. Other documents may supersede this document. A list of current <abbr title="World Wide Web Consortium">W3C</abbr> publications and the latest revision of this technical report can be found in the [<abbr title="World Wide Web Consortium">W3C</abbr> technical reports index](https://www.w3.org/TR/) at https://www.w3.org/TR/._

This document was published by the [Social Web Working Group](https://www.w3.org/Social/WG) as a Working Group Note. Comments regarding this document are welcome. Please send them to public-socialweb@w3.org ([subscribe](public-socialweb-request@w3.org), [archives](https://lists.w3.org/Archives/Public/public-socialweb/)).

Publication as a Working Group Note does not imply endorsement by the <abbr title="World Wide Web Consortium">W3C</abbr> Membership. This is a draft document and may be updated, replaced or obsoleted by other documents at any time. It is inappropriate to cite this document as other than work in progress.

This document was produced by a group operating under the [<abbr title="World Wide Web Consortium">W3C</abbr> Patent Policy](https://www.w3.org/Consortium/Patent-Policy/). <abbr title="World Wide Web Consortium">W3C</abbr> maintains a [public list of any patent disclosures](https://www.w3.org/2004/01/pp-impl/72531/status) made in connection with the deliverables of the group; that page also includes instructions for disclosing a patent. An individual who has actual knowledge of a patent which the individual believes contains [Essential Claim(s)](https://www.w3.org/Consortium/Patent-Policy/#def-essential) must disclose the information in accordance with [section 6 of the <abbr title="World Wide Web Consortium">W3C</abbr> Patent Policy](https://www.w3.org/Consortium/Patent-Policy/#sec-Disclosure).

This document is governed by the [1 March 2017 <abbr title="World Wide Web Consortium">W3C</abbr> Process Document](https://www.w3.org/2017/Process-20170301/).

## Table of Contents

1\. Introduction

2\. Overview

- 2.1 Contents
- 2.2 Definitions
- 2.3 Specifications
  - 2.3.1 Requirements
  - 2.3.2 How do these specifications relate to each other?

3\. Reading

- 3.1 Content representation
  - 3.1.1 Other ways of representing content
- 3.2 Objects
- 3.3 Collections
  - 3.3.1 Special streams
  - 3.3.2 Inboxes

4\. Publishing

- 4.1 Creating
- 4.2 Updating
- 4.3 Deleting

5\. Subscribing

- 5.1 Subscribing with `as:Follow`
- 5.2 Subscribing with a hub

6\. Delivery

- 6.1 Targeting and discovery
- 6.2 Generic notifications
- 6.3 Activity notifications
- 6.4 Mentioning
  - 6.4.1 Updates and deletes
- 6.5 Delivery interop
  - 6.5.1 Webmention as AS2 / ActivityPub
  - 6.5.2 LDN to Webmention
  - 6.5.3 Webmention to LDN

7\. Profiles

- 7.1 Relationships
- 7.2 Authentication, authorization, and access control

8\. Related specifcations

A\. Change Log

- A.1 Changes from 4 May 2017 WD to this version
- A.2 Changes from 16 November 2016 WD to this version
- A.3 Changes from 1 November 2016 WD to this version
- A.4 Changes from 12 October 2016 WD to this version
- A.5 Changes from 23 August to 12 October 2016
- A.6 Changes from 3 June to 23 August 2016

B\. References

- B.1 Informative references

## 1. Introduction

The <abbr title="World Wide Web Consortium">W3C</abbr> Social Web Working Group ran from June 2014 to December 2017, published seven recommendations and some notes. This is one of the notes, and it describes the work at the time of the group closing.

This work is by no means done, and the various communities involved have by no means gone to sleep. The endeavour continues in the [Social Web Community Group](https://www.w3.org/wiki/SocialCG), in which you are warmly invited to particiate.

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

## 3. Reading

If you are a content publisher, this section is about how you should publish your content. If you are a content consumer, this is what you should expect to consume.

### 3.1 Content representation

**ActivityStreams 2.0** is the recommended syntax ([[activitystreams-core](https://www.w3.org/TR/social-web-protocols/#bib-activitystreams-core)]) and vocabulary ([[activitystreams-vocabulary](https://www.w3.org/TR/social-web-protocols/#bib-activitystreams-vocabulary)]) for social data. ActivityStreams 2.0 represents content and interactions as _Objects_ and _Activities_. The ActivityStreams vocabulary defines a finite set of common Object and Activity types and properties, as well as an extension mechanism for applications which want to expand on or specialise these.

ActivityStreams 2.0 content is served with the Content-Type `application/activity+json` or for JSON-LD extended implementations, `application/ld+json; profile="https://www.w3.org/ns/activitystreams"`. Consumers should recognise both of these Content-Types as ActivityStreams 2.0; they should be treated as equivalent.

In order to claim ActivityStreams 2.0 conformance, a data publisher must use ActivityStreams 2.0 vocabulary terms where available, and only use other vocabularies _in addition_, or where no appropriate ActivityStreams 2.0 term exists.

>Note: ActivityStreams 1.0
>
>ActivityStreams 2.0 builds upon [[AS1](https://www.w3.org/TR/social-web-protocols/#bib-AS1)] and is not fully backwards compatible; [the relationship between AS1 and AS2 is documented in the AS2 spec](http://www.w3.org/TR/activitystreams-core#activitystreams-1.0). If you have implemented [[AS1](https://www.w3.org/TR/social-web-protocols/#bib-AS1)], you should transition to ActivityStreams 2.0.

To make content available as ActivityStreams 2.0 JSON, one could do so directly when requested with an appropriate `Accept` header (eg. `application/activity+json` or `application/ld+json`), or indirectly via a `rel="alternate" type="application/activity+json"` link . This link could be to a different domain, for third-party services which dynamically generate ActivityStreams 2.0 JSON on behalf of a publisher.

>Note: JSON-LD
>
>When sent as JSON-LD, ActivityStreams 2.0 must be [compacted](https://json-ld.org/spec/latest/json-ld-api/#compaction), and must not use the `@graph` keyword. This is because an ActivityStreams 2.0 document requires a single `Object` as the root. To serve multiple resources, you can instead nest them.
>
>The [ActivityStreams 2.0 JSON-LD context](https://www.w3.org/ns/activitystreams#) (https://www.w3.org/ns/activitystreams#) aliases `@id` and `@type` to `id` and `type` respectively.

**[[Activitypub](https://www.w3.org/TR/social-web-protocols/#bib-Activitypub)]** uses ActivityStreams 2.0 for all data, and also _extends_ ActivityStreams 2.0 with additional terms. Thus, ActivityPub requires responses to have the Content-Type `application/ld+json; profile="https://www.w3.org/ns/activitystreams"`. Publishers are however expected to also respect requests with the `application/activity+json` Accept header.

### 3.1.1 Other ways of representing content

If you don't like ActivityStreams 2.0, there are still some specifications you can use for particular tasks.

**[[LDN](https://www.w3.org/TR/social-web-protocols/#bib-LDN)]** notification contents can use any vocabulary, so long as the data is available as JSON-LD. Thus notifications *MAY* use ActivityStreams 2.0, but don't have to.

**[[Micropub](https://www.w3.org/TR/social-web-protocols/#bib-Micropub)]** clients which expect to read data (this would usually be clients for _[updating](https://www.w3.org/TR/social-web-protocols/#updating)_) are expecting it as JSON in the parsed microformats2 syntax ([[microformats2-parsing](https://www.w3.org/TR/social-web-protocols/#bib-microformats2-parsing)]).

**[[WebSub](https://www.w3.org/TR/social-web-protocols/#bib-WebSub)]** is agnostic as to the Content-Type used by publishers; hubs are expected to deliver the new content to subscribers as-is produced by the publisher, at the publisher's `topic` URL.

## 3.2 Objects

All ActivityStreams 2.0 objects have URLs in the `id` property, which return the properties of an object. The response may vary depending on the requester's right to access the content.

## 3.3 Collections

Each ActivityStreams 2.0 collection has a URL in the `id` property which returns the contents of the stream (according to the requester's right to access). This could be paged - ActivityStreams 2.0 provides [a paging mechanism](https://www.w3.org/TR/activitystreams-core/#paging). It may include additional metadata about the stream (such as title, description).

Each [object](https://www.w3.org/TR/social-web-protocols/#objects) in a collection contains at least its URL (`id`), as well as optionally other properties of the object.

Collections may represent changing streams of objects, or fixed sets. One [profile](https://www.w3.org/TR/social-web-protocols/#profiles) may be associated with one or more streams of content. Streams may be generated automatically or manually, and might be segregated by post type, topic, audience, or any arbitrary criteria decided by the curator of the stream. A profile may include links to multiple streams, which a consumer could follow to read or subscribe to.

### 3.3.1 Special streams

**[[Activitypub](https://www.w3.org/TR/social-web-protocols/#bib-Activitypub)]** specifies two streams that *MUST* be accessible from a profile via the following properties:

- `inbox`: A reference to an ActivityStreams 2.0 collection comprising all the objects received by the actor.
- `outbox`: An ActivityStreams 2.0 collection comprising all the objects produced by the actor.

ActivityPub also specifies further properties for accessing additional streams; `following` and `followers` are expected, and the rest are optional:

- `following`: An ActivityStreams 2.0 collection of the actors that this actor is following.
- `followers`: An ActivityStreams 2.0 collection of the actors that follow this actor
- `liked`: An ActivityStreams 2.0 collection of every `object` from all of the actor's `Like` activities (generated automatically by the server).
- `streams`: A list of supplementary Collections which may be of interest.
- `preferredUsername`
- `endpoints`: A mapping of additional (typically server/domain-wide) endpoints which may be useful either for this actor or someone referencing this actor: `proxyUrl`, `oauthAuthorizationEndpoint`, `oauthTokenEndpoint`, `provideClientKey`, `signClientKey`, `sharedInbox`.
- and any other applicable ActivityStreams 2.0 properties.

[[Activitypub](https://www.w3.org/TR/social-web-protocols/#bib-Activitypub)] permits arbitrary collections to be created through specifying special behavior for the server when it receives activities with types `Add` and `Remove`. When a server receives such an activity in the `outbox`, and the `target` is a `Collection`, it adds the `object` to the `target` (for `Add`) or removes the `object` from the `target` (for `Remove`).

### 3.3.2 Inboxes

An Inbox is an endpoint to which new objects may be [delivered](https://www.w3.org/TR/social-web-protocols/#delivery). It also serves as a collection whose contents may be read. The Inbox endpoint is used by both ActivityPub and LDN, and can be discovered through the properties:

- `ldp:inbox` (`http://www.w3.org/ns/ldp#inbox`)
- `as:inbox` (`https://www.w3.org/ns/activitystreams#inbox`)

In terms of JSON-LD, the latter is an alias of the former.

For how and when to write to an Inbox, see [delivery](https://www.w3.org/TR/social-web-protocols/#delivery).

The contents of this collection may also be read. While ActivityPub and LDN align for writing to an Inbox, due to irritating but ultimately unavoidable compatibility requirements with AS2 and LDP respectively, they use different vocabularies when Inbox contents are returned for reading. Fortunately for consuming clients to check for both vocabularies or for publishers to publish using both is not a huge implementation hurdle, so bridging is fairly trivial.

- ActivityPub Inboxes are an ActivityStreams 2.0 `OrderedCollection`, and link to their contents with the `items` property.
- LDN Inboxes are an [[LDP](https://www.w3.org/TR/social-web-protocols/#bib-LDP)] `Container` (providing an explicit type is optional), and link to their contents with the `contains` property.

In addition, ActivityPub has more constraints on the format of the JSON-LD returned. The two lists to follow describe how to bridge the small differences between ActivityPub and LDN conformant Inboxes.

**ActivityPub servers** wishing to be read by LDN consumers:

- must return alongside the `items` for everything in the collection, an `ldp:contains` (`http://www.w3.org/ns/ldp#contains`) relation.

**ActivityPub clients** wishing to read from LDN Inboxes:

- must request content with the content-type `application/ld+json`. Running it through JSON-LD compaction should help to format the respone in a more friendly way.
- must look for items in the Inbox via the `ldp:contains` property (rather than AS2 `items`).
- should not expect any of the items to have their properties nested; will probably need to retrieve individual items from the URLs in the `@id` property.
- Note the possibility of multiple vocabularies within the items in the Inbox themselves, including potentially a complete absence of any AS2.

**LDN receivers** wishing to be readable by ActivityPub consuming clients:

- must treat the content-type `application/activity+json` as equivalent to `application/ld+json; profile="http://www.w3.org/ns/activitystreams"`.
- serve Inbox contents as an AS2 `Collection`, where each notification is related to the inbox with the AS2 `items` property.
- must return compacted JSON-LD, and no `@graph`, serving the Inbox collection as the root of the document.
- may make life easier by nesting additional properties of each resource in the Inbox.

**LDN consumers** wishing to read from Inboxes on ActivityPub servers:

- must, if content is returned with the content-type `application/activity+json` and missing an `@context`, apply the default AS2 context, and treat it as JSON-LD.
- must look for items in the Inbox via the AS2 `items` property (rather than `ldp:contains`).

## 4. Publishing

Publishing in this context refers to modifying the outgoing feed associated with a particular profile. This incorporates creating new content, as well as updating or deleting existing content. Content generated through a client (such as a web form, mobile app, sensor, smart device) is created when it is sent to a server for processing, where it is typically stored and usually published (either publicly or to a restricted audience), in human- and/or machine-readable forms. Clients and servers may independently support creating, updating and deleting; there are no dependencies between them.

>Note: Other kinds of publishing
>
>While delivering notifications or responding to subscription requests may trigger creating (or updating or deleting) something on the receiving end, the intent is different. These cases are called out as side effects in subscription and delivery where appropriate.

For notes about authentication and authorization between clients and servers, see [7.2 Authentication, authorization, and access control](https://www.w3.org/TR/social-web-protocols/#auth)

The two specifications recommended by the Social Web Working Group for publishing are [[Activitypub](https://www.w3.org/TR/social-web-protocols/#bib-Activitypub)] and [[Micropub](https://www.w3.org/TR/social-web-protocols/#bib-Micropub)]. They use similar high level mechanisms, but differ in requirements around both the vocabularies and content types of data.

ActivityPub contains a client-to-server API for creating ActivityStreams 2.0 objects and activities, and specifies additional responsibilities for clients around addressing objects, and for servers around the side-effects of certain types of objects.

Micropub provides a basic client-to-server API for creating blog-post-type content and is intended as a quickstart for content creation, on top of which more complex (but optional) actions can be layered. Micropub also provides a media endpoint for uploading files.

>Note: REST
>
>Neither ActivityPub nor Micropub define APIs for publishing based on HTTP verbs. If you're looking for something more RESTful, you may like the Linked Data Platform [[LDP](https://www.w3.org/TR/social-web-protocols/#bib-LDP)].

### 4.1 Creating

The publishing endpoint of **[[Activitypub](https://www.w3.org/TR/social-web-protocols/#bib-Activitypub)]** is the `outbox`. Clients are assumed to have the URL of a (ideally authenticated) profile as a starting point, and discover the value of the `https://www.w3.org/ns/activitystreams#outbox` property found at the profile URL (which should be available as JSON). The client then makes an HTTP POST request with an ActivityStreams 2.0 activity or object as a JSON payload with a content type of `application/ld+json; profile="https://www.w3.org/ns/activitystreams"`. The URL of the created resource is generated at the discretion of the server, and returned in the `Location` HTTP header. This is an appropriate protocol to use when:

- You want to send/receive a JSON or JSON-LD payload.
- Your data is described with [[activitystreams-core](https://www.w3.org/TR/social-web-protocols/#bib-activitystreams-core)] and [[activitystreams-vocabulary](https://www.w3.org/TR/social-web-protocols/#bib-activitystreams-vocabulary)] (optionally extensible via JSON-LD).
- You want servers to carry out a known set of actions upon content creation.

Side-effects of creating content with ActivityPub are for the most part adding things to various different collections collections (likes, follows, etc); but also include requirements about blocking users, and a hook to enable federated servers.

The publishing endpoint for **[[Micropub](https://www.w3.org/TR/social-web-protocols/#bib-Micropub)]** is the `micropub` endpoint. Clients discover this from a profile URL via a `rel="micropub"` link (in an HTTP `Link` header, or an HTML `<link>` element). Clients make a `x-www-form-urlencoded` POST request containing the key-value pairs for the attributes of the object being created. The URL of the created resource is generated at the discretion of the server, and returned in the `Location` HTTP header. Clients and servers must support attributes from the Microformats2 [[h-entry](https://www.w3.org/TR/social-web-protocols/#bib-h-entry)] vocabulary. Micropub also defines four reserved attributes (`access_token`, `h`, `action` and `url`) as well as reserves any attribute prefixed with `mp-`; these are used as commands to the server. Any additional key names sent outside of these vocabularies may be ignored by the server.

Micropub requests may alternatively be sent as a JSON payload, the syntax of which is derived from [[microformats2-parsing](https://www.w3.org/TR/social-web-protocols/#bib-microformats2-parsing)].

This is an appropriate protocol to use when:

- You want to send/receive a form-encoded or JSON payload.
- Your data is described with the [[h-entry](https://www.w3.org/TR/social-web-protocols/#bib-h-entry)] syntax and vocabulary.
- You can rely on out-of-band agreements between clients and servers for vocabulary extensibility.

### 4.2 Updating

Content is updated when a client sends changes to attributes (additions, removals, replacements) to an existing object.

**[[Activitypub](https://www.w3.org/TR/social-web-protocols/#bib-Activitypub)]** clients send an HTTP `POST` request to the `outbox` containing an ActivityStreams 2.0 `Update` activity. The `object` of the activity is an existing object, including its `id`, and the fields to update should be nested. If a partial representation of an object is sent, omitted fields are _not_ deleted by the server. In order to delete specific fields, the client can assign them a `null` value.

In the case of ActivityPub federated servers, updates should be propagated to the `inbox`es of recipients of the original objects. However, when a federated server passes an `Update` activity to another server's `inbox`, the recipient must assume this is the _complete_ object to be replaced; partial updates are not performed server-to-server.

An `Undo` with the `object` of the previous `Update` can be used to revert changes.

**[[Micropub](https://www.w3.org/TR/social-web-protocols/#bib-Micropub)]** clients perform updates as JSON POST requests, using the `"action": "update"` directive, as well as a `replace`, `add` or `delete` property containing the updates to make, to the Micropub endpoint. `replace` replaces all values of the specified property; if the property does not exist already, it is created. `add` adds new values to the specified property without changing the existing ones; if the property does not exist already, it is created. `delete` removes the specified property; you can also remove properties by value by specifying the value.

If a server also implements [[Webmention](https://www.w3.org/TR/social-web-protocols/#bib-Webmention)] it should propagate the updates to anyone who received Webmentions for the original.

If a server also implements [[WebSub](https://www.w3.org/TR/social-web-protocols/#bib-WebSub)], and the updated resource is part of a `topic`, the server should notify the hub of an update to the topic URL.

### 4.3 Deleting

Content is deleted when a client sends a request to delete an existing object.

**[[Activitypub](https://www.w3.org/TR/social-web-protocols/#bib-Activitypub)]** clients delete an object by sending an HTTP POST request containing an ActivityStreams 2.0 `Delete` activity to the `outbox` of the authenticated user. Servers must either _replace_ the `object` of this activity with a tombstone and return a `410 Gone` status code, or return a `404 Not Found`, from its URL.

An `Undo` with the `object` of the previous `Delete` may be used to restore the object.

**[[Micropub](https://www.w3.org/TR/social-web-protocols/#bib-Micropub)]** delete requests are two key-value pairs, JSON: `"action": "delete"` and `"url": url-to-be-deleted`, sent to the Micropub endpoint. Posts may be resotred with `"action": "undelete"`.

As with [updating](https://www.w3.org/TR/social-web-protocols/#updating), servers implementing ActivityPub federation, Webmention or WebSub should propagate deletes accordingly.

## 5. Subscribing

An agent (client or server) may ask to be notified of changes to a content object (eg. edits, new replies) or stream of content (eg. objects added or removed from a particular stream). This is _subscribing_. Specifications which contain subscription mechanisms are ActivityPub and WebSub.

>Note: Subscription vs delivery
>
>Receiving notifications does not need to rely on implementation of a subscription mechanism. That is, implementations may set themselves up to receive notifications without always being required to explicitly ask for them from a sender or publisher: see [delivery](https://www.w3.org/TR/social-web-protocols/#delivery).

### 5.1 Subscribing with `as:Follow`

**[[Activitypub](https://www.w3.org/TR/social-web-protocols/#bib-Activitypub)]** servers maintain a Followers collection for all users. This collection may be directly addressed, or addressed automatically or by default, in the `to`, `cc` or `bcc` field of any Activity. As a result, federated servers [deliver](https://www.w3.org/TR/social-web-protocols/#delivery) the Activity to the `inbox` of each profile in the collection.

Subscription requests are essentially requests to be added to this collection. They are made by the subscriber's server `POST`ing a `Follow` Activity to the target's `inbox`. This request should be authenticated, and therefore doesn't need additional verification. The target server then should add the subscriber to the target's Followers collection. Exceptions may be made if, for example, the target has blocked the subscriber.

This is a suitable subscription mechanism when:

- The subscriber wants to request updates from a specific profile's `outbox` (rather than objects, streams, feeds, collections, conversation threads).
- The subscriber and publisher both speak ActivityStreams 2.0.
- The publisher is aware of who has subscribed, and capable of delivering content to subscribers itself.

Since delivery is only a requirement for federated servers, prospective subscribers will not be able to `POST` their `Follow` activity to the `inbox` of a profile which is on a non-federated server (expect a `405 Method Not Allowed`), and thus are not able to subscribe to these profiles. In this case, prospective subscribers may wish to periodically pull from the publisher's `outbox` instead.

### 5.2 Subscribing with a hub

**[[WebSub](https://www.w3.org/TR/social-web-protocols/#bib-WebSub)]** provides a mechanism to delegate subscription handling and delivery of content to subscribers to a third-party, called a hub. All publishers need to do is link to their chosen hub(s) using HTTP `Link` headers or HTML `<link>` elements with `rel="hub"`, and then notify the hub when new content is available. The mechanism for notifying the hub is left deliberately unspecified, as publishers may have their own built in hub, and therefore use an internal mechanism.

>Note: Notifying the hub
>
>A mechanism for communcation between publishers and hubs may be standardised in future as an extension.

The subscriber discovers the hub from the publisher, and sends a form-encoded `POST` request containing values for `hub.mode` ("subscribe"), `hub.topic` (the URL to subscribe to) and `hub.callback` (the URL where updates should be sent to, which should be 'unguessable' and unique per subscription). The hub and subscriber carry out a series of exchanges to verify this request.

When the hub is notified of new content by the publisher, the hub fetches the content of the `topic` URL, and sends this to the subscriber's `callback` URL via a POST request. The body of the request is the content of the topic URL, and the `Content-Type` must match. A `rel=hub` `Link` header should be included.

This is a suitable subscription mechanism when:

- The subscriber wants to request updates from any resource (not just user profiles), and of any content type.
- Subscription requests are not authenticated, so you need a way to verify them.
- The publisher wants to delegate distribution of updates to another service (the hub) instead of doing it itself.

>Note: WebSub and LDN
>
>LDN Receivers can be used to receive deliveries from WebSub hubs by using the `inbox` URL as the `hub.callback` URL and either only subscribing to resources published as JSON-LD or accepting content-types other than JSON-LD.

## 6. Delivery

A user or application may wish to push a notification to another user that the receiver has not explicitly asked for. For example to send a message or some new information; because they have linked to (replied, liked, bookmarked, reposted, etc) their content; because they have linked to (tagged, addressed) the user directly; to make the recipient aware of a change in state of some document or resource on the Web. The Social Web Working Group specifications contain several mechanisms for carrying out delivery; they are listed here from general to specialised.

>Note: Delivery vs subscription
>
>We need to leave it open for users to refuse content they have not explicitly [subscribed](https://www.w3.org/TR/social-web-protocols/#subscribing) to, ie. nothing else should rely on implementation of delivery.

### 6.1 Targeting and discovery

The target of a notification is usually the addressee or the subject, as referenced by a URL. The target may also a resource which has previously requested notifications through a [subscription](https://www.w3.org/TR/social-web-protocols/#subscribing) request. Once you have determined your target, you need to discover where to send the notification for that particular target. Discovery is fetching the target URL and looking for a link to an endpoint which will accept the type of notification you want to send (read on, for all of your exciting options).

Bear in mind that many potential targets will not be configured to receive notifications at all. To avoid overloading unsuspecting servers with discovery-related requests, your application should employ a "back-off" strategy when carrying out discovery multiple times to targets on the same domin. This could involve increasing the period of time between subsequent requests, or caching unsuccessful discovery attempts so those domains can be avoided in future. You may wish to send a `User-Agent` header with a reference to the notification mechanism you are using so that recipient servers can find out more about the purpose of your requests.

Your application should also respect relevant cache control and retry headers returned by the target server.

### 6.2 Generic notifications

**[[LDN](https://www.w3.org/TR/social-web-protocols/#bib-LDN)]** is a federation protocol for sending, receiving and consuming notifications which may contain any content, and be triggered by any person or process. Senders, receivers and consumers can all be on different domains. This is a suitable notification mechanism when:

- Notifications need to be identifiable with their own URLs and exposed by the receiver for other applications to discover and re-use.
- Notifications are represented as a JSON-LD payload (ie. a 'fat ping').
- You need to advertise constraints on the type or contents of notifications accepted by a receiver.

[[LDN](https://www.w3.org/TR/social-web-protocols/#bib-LDN)] functionality is divided between senders, receivers and consumers. The endpoint to which notifications are sent is the `inbox`. Any resource (a user profile, blog post, document) can advertise its `inbox` so that it may be discovered through an HTTP `Link` header or the document body in any RDF syntax (including JSON-LD or HTML+RDFa). To this Inbox, senders make a `POST` request containing the JSON-LD (or other RDF syntax per [[Accept-Post](https://www.w3.org/TR/social-web-protocols/#bib-Accept-Post)] negotation with the receiver) payload of the notification. The receiver returns a URL from which the notification data can be retrieved, and also adds this URL to a list which is returned upon a `GET` request to the Inbox (see [3. Reading](https://www.w3.org/TR/social-web-protocols/#reading)). Consumers can retrieve this Inbox listing, and from there the individual notifications, as JSON-LD (optionally content negotiated to another RDF syntax). An obvious type of consumer is a script which displays notifications in a human-readable way.

>Note: LDP compatibility
>
>An existing [[LDP](https://www.w3.org/TR/social-web-protocols/#bib-LDP)] implementation can serve as an [[LDN](https://www.w3.org/TR/social-web-protocols/#bib-LDN)] receiver out of the box; publishers simply advertise any `ldp:Container` as the `inbox` for a resource.

The payload of notifications is deliberately left open so that LDN may be used in a wide variety of use cases. However, receivers with particular purposes are likely to want to constrain the types of notifications they accept. They can do this transparently (such that senders are able to attempt to conform, rather than having their requests rejected opaquely) by advertising data shapes constraints such as [[SHACL](https://www.w3.org/TR/social-web-protocols/#bib-SHACL)]. Advertisement of such constraints also allows consumers to understand the types of notifications in the Inbox before attempting to retrieve them. Receivers may reject notifications on the basis of internal, undisclosed constraints, and may also access control the Inbox for example by requiring an `Authorization` header from both senders and consumers.

[[WebSub](https://www.w3.org/TR/social-web-protocols/#bib-WebSub)] publishers deliver content to their hub, and hubs to their subscribers using HTTP `POST` requests. The body of the request is left to the discretion of the sender in the first case, and in the latter case must match the Content-Type of and contain contents from the `topic` URL.

### 6.3 Activity notifications

**[[Activitypub](https://www.w3.org/TR/social-web-protocols/#bib-Activitypub)]** uses [[LDN](https://www.w3.org/TR/social-web-protocols/#bib-LDN)] to send notifications with some specific constraints. These are:

- The notification payload *MUST* be a single ActivityStreams 2.0 Activity.
- The notification payload *MUST* be compact JSON-LD.
- The receiver *MUST* verify the notification by fetching its source from the origin server.
- All notification `POST` requests are authenticated.

[[Activitypub](https://www.w3.org/TR/social-web-protocols/#bib-Activitypub)] specifies how to define the target(s) to which a notification is to be sent (a pre-requisite to [[LDN](https://www.w3.org/TR/social-web-protocols/#bib-LDN)] sending), via the [[activitystreams-vocabulary](https://www.w3.org/TR/social-web-protocols/#bib-activitystreams-vocabulary)] audience targeting and object linking properties.

[[Activitypub](https://www.w3.org/TR/social-web-protocols/#bib-Activitypub)] also defines side-effects that must be carried out by the server as a result of notification receipt. These include:

- Creating, updating or deleting new objects upon receipt of `Create`, `Update` and `Delete` activities.
- Reversing the side-effects of prior activities upon receipt of the `Undo` activity.
- Updating specialised collections for `Follow`, `Like` and `Block` activities.
- Updating any other collections upon receipt of `Add` and `Remove` activities.
- Carrying out further delivery to propagate activities through the network in the case of federated servers.

>Note: The inbox property
>
>ActivityPub actor profiles are linked to their inboxes via the `https://www.w3.org/ns/activitystreams#inbox` property. This is an alias (in the AS2 JSON-LD context) for LDN's `http://www.w3.org/ns/ldp#inbox`. Applications using a full JSON-LD processor to parse these documents will see these terms as one and the same. Applications doing naive string matching on terms may wish to note that if you find an `ldp:inbox` it will accept `POST` requests in the same way as an `as:inbox`.

### 6.4 Mentioning

**[[Webmention](https://www.w3.org/TR/social-web-protocols/#bib-Webmention)]** provides an API for sending and receiving notifications when a relationship is created (or updated, or deleted) between two documents. A webmention sender is triggered by the creation (or modification) of content which includes the URL of another document. It works when the two documents are on different domains, thus serving as a federation protocol. This is a suitable notification mechanism when:

- You have a document (source) which contains the URL of another document (target).
- The owner of the endpoint has access to view the source (so the request can be verified).
- The only data you need to send over the wire are the URLs of the source and target documents (ie. a 'thin ping').

There are no constraints on the syntax of the source and target documents. Discovery of the [[Webmention](https://www.w3.org/TR/social-web-protocols/#bib-Webmention)] endpoint (a script which can process incoming webmentions) is through a link relation (`rel="webmention"`), either in the HTTP `Link` header or HTML body of the target. This endpoint does not need to be on the same domain as the target, so webmention receiving can be delegated to a third party.

Webmentions are verified by the server dereferencing the source and parsing it to check for the existence of the target URL. If the target URL isn't found, the webmention *MUST* be rejected.

Webmention uses `x-www-form-urlencoded` for the source and target as parameters in an HTTP POST request. Beyond verification, it is not specified what the receiver should do upon receipt of a Webmention. What the webmention endpoint should return on a `GET` request is also left unspecified.

#### 6.4.1 Updates and deletes

In practice, Webmention receivers tend to fetch and store the webmention source. It is often displayed, for example as a reply underneath the target blog post.

If a Webmention is received and this is the first time this `source` and `target` combination has been seen by the receiver, this indicates a relationship between the `source` and `target` has been created. If the receiver has seen these values before, the receiver can fetch and parse the `source` to determine what has changed; either the content of the `source` has been updated (in which case the receiver can update local copies of the content, if it stored them in the first place), or the entire source has been deleted (expect a `410 Gone` response).

### 6.5 Delivery interop

This section describes how implementations of Webmention, ActivityPub and LDN may create bridging code in order to send and receive notifications from the others.

#### 6.5.1 Webmention as AS2 / ActivityPub

A webmention may be represented as a persistent resource with the ActivityStreams 2.0 vocabulary. This could come in handy if a **Webmention sender** mentions a user known to be running an ActivityPub federated server, and wants a generic (ie. not ActivityPub specific) way of notifying about this. In this case, the sender can use an AS2 payload and deliver the notification per [6.5.3 Webmention to LDN](https://www.w3.org/TR/social-web-protocols/#wm-to-ldn).

>Example 1
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

>Example 2
>
>```json
>{
>  "@context": "https://www.w3.org/ns/activitystreams#",
>  "type": "Relationship",
>  "subject": {
>- "id": "https://waterpigs.example/post-by-barnaby",
>- "name": "Hi Aaron, great post."
>  },
>  "object": {
>- "id": "https://aaronpk.example/post-by-aaron",
>- "name": "Aaron's first post."
>  },
>  "relationship": "inReplyTo"
>}
>```

#### 6.5.2 LDN to Webmention

**Webmention receivers** wishing to also accept LDN `POST`s at their Webmention endpoint must:

- Advertise the webmention endpoint via `rel="http://www.w3.org/ns/ldp#inbox"` in addition to `rel="webmention"` (in the `Link` header, HTML body or JSON body of a target).
- Accept `POST` requests with the Content-Type `application/ld+json`. Expect the body of the request to be:

    >Example 3
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

**LDN senders** wishing to send to Webmention endpoints basically just need to implement Webmention sending. The Webmention endpoint is at `rel="webmention"` (either in an HTTP `Link` header or HTML `<link>` element).

Note that Webmention endpoints will only verify a received notification if the `source` is publicly retrievable and contains the URL of the `target`.

#### 6.5.3 Webmention to LDN

**LDN receivers** wishing to also accept Webmentions to their Inbox *MUST*:

- Advertise the Inbox via `rel="webmention"` in addition to `rel="http://www.w3.org/ns/ldp#inbox"` (in the `Link` header, HTML body or JSON body of a target).
- Accept `POST` requests with a content type `application/x-www-form-urlencoded`. Convert these requests from:
    >Example 4
    >
    >```lang-none
    >source=https://waterpigs.example/post-by-barnaby&
    >target=https://aaronpk.example/post-by-aaron
    >```

    to:

    >Example 5
    >
    >```json
    >{
    >  "@context": "http://www.w3.org/ns/webmention#",
    >  "@id": "",
    >  "source": { "@id": "https://waterpigs.example/post-by-barnaby" },
    >  "target": { "@id": "https://aaronpk.example/post-by-aaron" }
    >}
    >```

- and proceed per [[LDN](https://www.w3.org/TR/social-web-protocols/#bib-LDN)]; receivers *MAY* add other triples at their discretion.
- Receivers *MUST* return a 201 Created with a Location header or 202 Accepted.
- Receivers *MUST* verify the request by retrieving the source document and checking a link to the target document is present. If the Webmention is not verified, recievers *MUST NOT* keep it.

**Webmention senders** wishing to send to LDN Inboxes need to send a JSON-LD payload. Discover the Inbox endpoint through a relation of `http://www.w3.org/ns/ldp#inbox` between the `target` and the Inbox. A typical Webmention can be represented as JSON-LD per [this example](https://www.w3.org/TR/social-web-protocols/#wm-json), or as ActivityStreams 2.0 JSON per [this example](https://www.w3.org/TR/social-web-protocols/#wm-as2).

>Note: Bridging services
>
>Look out for Webmention-ActivityPub bridges as services. These will provide endpoints to do the heavy lifting of the spec you don't want to implement yourself. You can use these endpoints as your Webmention or Inbox endpoint respectively. Brainstorming and implementations of such bridges can be found on the [Social Web Community Group](https://www.w3.org/wiki/SocialCG) and the [IndieWeb community](https://indieweb.org/bridge#ActivityPub).

## 7. Profiles

The subject of a profile document can be a person, persona, organisation, bot, location, or other. None of the specifications described here prescribe particular relationships between real-world entities and online profiles. That is, one person can have many profiles, and one profile may be controlled by many people. How/if/when multiple profiles are linked together is implementation specific, and not specified anywhere here.

Most specifications expect that profiles are identified by and retrieved from a URL, and that attributes of the subject of the profile are available from the URL. Ideally they also return a link to at least one stream of content associated with the profile (or embed the content directly), for example activities or blog posts.

**ActivityPub** profiles are JSON-LD documents containing any appropriate ActivityStreams 2.0 properties, as well as links to various endpoints and collections (see [3.3.1 Special streams](https://www.w3.org/TR/social-web-protocols/#streams-special)).

**ActivityStreams 2.0** has various [Actor types](https://www.w3.org/TR/activitystreams-core/#actors), which may be used to represent individuals or groups, and also includes `Profile`.

**Micropub** has a notion of a profile page (URL) that represents a user, but does not specify the format of that page, except for the link to the Micropub endpoint and authorization endpoints for clients to discover.

**Webmention** does not specify any particular profile format, but in practice Webmention implementations typically publish and consume [[h-card](https://www.w3.org/TR/social-web-protocols/#bib-h-card)] profile information to display authors of webmention sources (see [examples in the Webmention spec](https://www.w3.org/TR/webmention/#webmention-verification-p-4)).

### 7.1 Relationships

Semantics and representation of personal relationships are implementation specific. These specifications deal with relationships only when distribution of content is affected, for example when 'following' triggers a subscription request from one server to another. Lists of other relationships may be discoverable from a user profile, should be represented according to the ActivityStreams 2.0 syntax and may (and are likely to) use extension vocabularies as needed.

- **ActivityPub**: When a server receives a `Follow` Activity in its `inbox`, the subject is added to a `Followers Collection`, which is discoverable from the subject's profile. Federated servers use this collection to deliver updates when new content is created by the owner of the collection.

### 7.2 Authentication, authorization, and access control

Authentication and authorization mechanisms were out of scope for the Social Web WG. Please follow the [Community Group](https://www.w3.org/wiki/SocialCG) for development in this space. Meanwhile, some of the WG specifications contain non-normative notes on the topic:

- **ActivityPub**: Points to a Community Group best practices report in [B.1 Authentication and Authorization](https://www.w3.org/TR/activitypub/#authorization).
- **LDN**: Recommends that receivers employ some kind of verification mechanism which may be authentication in [3.3.3 Sender verification](https://www.w3.org/TR/ldn/#sender-verification), with additional security considerations in [5.6 Authenticated inboxes](https://www.w3.org/TR/ldn/#authenticated-inboxes).
- **Micropub**: Requires bearer tokens, and suggests IndieAuth in [5. Authentication and Authorization](https://www.w3.org/TR/micropub/#authentication-and-authorization).
- **Webmention**: Points to an extension for use with access controlled posts in [B.3 Private Webmention](https://www.w3.org/TR/webmention/#private-webmention).
- **WebSub**: Describes optional use of HMAC Signatures in [8.1 Authenticated Content Distribution](https://www.w3.org/TR/websub/#authenticated-content-distribution).

## 8. Related specifcations

Other specifications worth mentioning in relation to the output of the Social Web Working Group are outlined here.

Social Web Working Group Notes:

- **[[IndieAuth](https://www.w3.org/TR/social-web-protocols/#bib-IndieAuth)]**: is an identity layer on top of OAuth 2, and the expected auth mechanism for Micropub clients.
- **[[JF2](https://www.w3.org/TR/social-web-protocols/#bib-JF2)]**: is an alternative JSON syntax for social content, derived from[[microformats2](https://www.w3.org/TR/social-web-protocols/#bib-microformats2)]. It includes individual objects and feeds. If you don't like ActivityStreams 2.0, you might like this instead. At the time of writing it is not referenced by any other Social Web Working Group specifications.
- **[[post-type-discovery](https://www.w3.org/TR/social-web-protocols/#bib-post-type-discovery)]**: specifies an algorithm for determining the type of post by its properties. This may help with bridging between content marked up with [[microformats2](https://www.w3.org/TR/social-web-protocols/#bib-microformats2)], and explicitly typed vocabularies like ActivityStreams 2.0.

External:

- **[[LDP](https://www.w3.org/TR/social-web-protocols/#bib-LDP)]**: was an input to the Social Web Working Group charter. `Container`s on LDP servers can be used directly as LDN receivers, if you happen to have one lying around. The Web Annotation Protocol is also based on LDP.
- **[[microformats2](https://www.w3.org/TR/social-web-protocols/#bib-microformats2)]**: is a way to mark up structured information in HTML. Micropub expects the microformats2 vocabulary, and Webmention receiver implementations often look for microformats2 markup to fetch more information about a source.
- **[[annotation-protocol](https://www.w3.org/TR/social-web-protocols/#bib-annotation-protocol)]**: uses ActivityStreams 2.0 Collections and Paging to model sets of annotations. Annotations themselves use the [[annotation-vocab](https://www.w3.org/TR/social-web-protocols/#bib-annotation-vocab)].

Development of related specifications is ongoing in various communities, notably the [Social Web Community Group](https://www.w3.org/wiki/SocialCG) and the [IndieWeb](https://indieweb.org/) community.

## A. Change Log

### A.1 Changes from 4 May 2017 WD to this version

- Editorial updates throughout.
- Update all spec functionality which had fallen behind (mostly Micropub).
- Add requirements definitions to clarify the sections each spec is listed under, and their relation to charter deliverables.
- Clarify relevence of Federation Protocols to Social API parts (ie. updates triggering new notifications etc).
- Elaborate on Updates and Deletes for AP and Webmention.
- Profiles now describes each spec's use or expectations of profiles.
- Auth section now links to relevent parts of each individual spec.
- Add a section for related specs.

### A.2 Changes from 16 November 2016 WD to this version

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

### A.3 Changes from 1 November 2016 WD to this version

- Update document status of recently published drafts.

### A.4 Changes from 12 October 2016 WD to this version

- Updated WebSub since it was published as FPWD.

### A.5 Changes from 23 August to 12 October 2016

- Added targeting and discovery section, including "backoff" strategy advice.

### A.6 Changes from 3 June to 23 August 2016

- Add new WG drafts as they were published by the group: JF2, PTD, LDN, PuSH.
- Update the publication statuses of existing WG drafts as they advanced.
- Describe LDN in Delivery and Reading.
- Describe PuSH in Subscribing and Delivery.
- Delivery interop:
  - how Webmention senders/receivers and LDN senders/receivers may implement a bridge.
  - how a Webmention could be represented as an AS2 Relationship.
- Refactor Subscribing and Reading to prioritise WG specs and clarify relations between them.
- Editorial improvements to introductory and overview text.

## B. References

### B.1 Informative references

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

[맨 위로](#social-web-protocols)
