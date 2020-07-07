[목차로 돌아가기](SocialWebProtocolsContents.md)

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