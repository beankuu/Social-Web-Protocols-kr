[목차로 돌아가기](SocialWebProtocolsContents.md)

# [소셜 웹 프로토콜 (Social Web Protocols)](https://www.w3.org/TR/social-web-protocols/)

<abbr title="World Wide Web Consortium">W3C</abbr> Working Group Note 25 December 2017

2017년 12월 25일 <abbr title="World Wide Web Consortium">W3C</abbr> Working Group 노트

**This version:**
- https://www.w3.org/TR/2017/NOTE-social-web-protocols-20171225/

**현재 버전**
- https://www.w3.org/TR/2017/NOTE-social-web-protocols-20171225/

**Latest published version:**
- https://www.w3.org/TR/social-web-protocols/

**최신 게시 버전**
- https://www.w3.org/TR/social-web-protocols/

**Latest editor's draft:**
- https://w3c-social.github.io/social-web-protocols

**최신 편집자 초안**
- https://w3c-social.github.io/social-web-protocols

**Previous version:**
- https://www.w3.org/TR/2017/WD-social-web-protocols-20170504/

**이전 버전**
- https://www.w3.org/TR/2017/WD-social-web-protocols-20170504/

**Editor:**
- [Amy Guy](http://rhiaro.co.uk/), [University of Edinburgh](http://inf.ed.ac.uk/), amy@rhiaro.co.uk

**편집자:**
- [Amy Guy](http://rhiaro.co.uk/), [University of Edinburgh](http://inf.ed.ac.uk/), amy@rhiaro.co.uk

**Repository:**
- [Git repository](https://github.com/w3c-social/social-web-protocols)
- [Issues](https://github.com/w3c-social/social-web-protocols/issues)
- [Commits](https://github.com/w3c-social/social-web-protocols/gh-pages)

**저장소**
- [Git 저장소](https://github.com/w3c-social/social-web-protocols)
- [이슈들](https://github.com/w3c-social/social-web-protocols/issues)
- [커밋들](https://github.com/w3c-social/social-web-protocols/gh-pages)

[Copyright](https://www.w3.org/Consortium/Legal/ipr-notice#Copyright) © 2017 [<abbr title="World Wide Web Consortium">W3C</abbr>](https://www.w3.org/)® (<abbr title="Massachusetts Institute of Technology">[MIT](https://www.csail.mit.edu/)</abbr>, <abbr title="European Research Consortium for Informatics and Mathematics">[ERCIM](https://www.ercim.eu/)</abbr>, [Keio](https://www.keio.ac.jp/), [Beihang](http://ev.buaa.edu.cn/)). <abbr title="World Wide Web Consortium">W3C</abbr> [liability](https://www.w3.org/Consortium/Legal/ipr-notice#Legal_Disclaimer), [trademark](https://www.w3.org/Consortium/Legal/ipr-notice#W3C_Trademarks) and [permissive document license](https://www.w3.org/Consortium/Legal/2015/copyright-software-and-document) rules apply.

[Copyright](https://www.w3.org/Consortium/Legal/ipr-notice#Copyright) © 2017 [<abbr title="World Wide Web Consortium">W3C</abbr>](https://www.w3.org/)® (<abbr title="Massachusetts Institute of Technology">[MIT](https://www.csail.mit.edu/)</abbr>, <abbr title="European Research Consortium for Informatics and Mathematics">[ERCIM](https://www.ercim.eu/)</abbr>, [Keio](https://www.keio.ac.jp/), [Beihang](http://ev.buaa.edu.cn/)). <abbr title="World Wide Web Consortium">W3C</abbr> [법적 책임](https://www.w3.org/Consortium/Legal/ipr-notice#Legal_Disclaimer), [상표](https://www.w3.org/Consortium/Legal/ipr-notice#W3C_Trademarks)와 [문서 허용 라이센스](https://www.w3.org/Consortium/Legal/2015/copyright-software-and-document) 규칙이 적용됩니다.

-----

## [요약 (Abstract)](#소셜-웹-프로토콜-social-web-protocols)

The Social Web Protocols are a collection of standards which enable various aspects of decentralised social interaction on the Web. This document describes the purposes of each, and how they fit together.

Social Web Protocols은 웹에서의 분산된 소셜들의 다양한 상호작용 방법들을 가능하게 하는 표준들의 집합체입니다. 이 문서에서는 각 표준들의 용도와 이들이 어떻게 조화를 이루는지에 대해 설명합니다.

## [이 문서의 상태 (Status of This Document)](#소셜-웹-프로토콜-social-web-protocols)

_This section describes the status of this document at the time of its publication. Other documents may supersede this document. A list of current <abbr title="World Wide Web Consortium">W3C</abbr> publications and the latest revision of this technical report can be found in the [<abbr title="World Wide Web Consortium">W3C</abbr> technical reports index](https://www.w3.org/TR/) at https://www.w3.org/TR/._

_이 섹션에서는 현 문서의 발행 당시의 상태에 대하여 기술합니다. 다른 문서가 이 문서를 대체 할 수 있습니다. 현재 <abbr title="World Wide Web Consortium">W3C</abbr> 출판물 목록 및 이 기술보고서의 최신 개정판은 https://www.w3.org/TR/ 에 있는 [<abbr title="World Wide Web Consortium">W3C</abbr> 기술보고서 색인](https://www.w3.org/TR/)에서 찾아볼 수 있습니다._

This document was published by the [Social Web Working Group](https://www.w3.org/Social/WG) as a Working Group Note. Comments regarding this document are welcome. Please send them to public-socialweb@w3.org ([subscribe](public-socialweb-request@w3.org), [archives](https://lists.w3.org/Archives/Public/public-socialweb/)).

이 문서는 [Social Web Working Group](https://www.w3.org/Social/WG)에 의하여 작성된 Working Group 노트입니다. 이 문서에 관한 의견은 언제나 환영합니다. 의견이 있을시 public-socialweb@w3.org ([구독](public-socialweb-request@w3.org), [기록들](https://lists.w3.org/Archives/Public/public-socialweb/))로 보내주시길 바랍니다.

Publication as a Working Group Note does not imply endorsement by the <abbr title="World Wide Web Consortium">W3C</abbr> Membership. This is a draft document and may be updated, replaced or obsoleted by other documents at any time. It is inappropriate to cite this document as other than work in progress.

Working Group 노트로 게시된 것은 <abbr title="World Wide Web Consortium">W3C</abbr> 멤버십에 의해 수용되었다는 의미가 아닙니다. 이 문서는 초안 문서이며 언제든지 다른 문서에 의해 업데이트, 교체 또는 폐기될 수 있습니다. 이 문서를 진행 중인 작업 이외의 다른 문서로 인용하는 것은 적절하지 않습니다.

This document was produced by a group operating under the [<abbr title="World Wide Web Consortium">W3C</abbr> Patent Policy](https://www.w3.org/Consortium/Patent-Policy/). <abbr title="World Wide Web Consortium">W3C</abbr> maintains a [public list of any patent disclosures](https://www.w3.org/2004/01/pp-impl/72531/status) made in connection with the deliverables of the group; that page also includes instructions for disclosing a patent. An individual who has actual knowledge of a patent which the individual believes contains [Essential Claim(s)](https://www.w3.org/Consortium/Patent-Policy/#def-essential) must disclose the information in accordance with [section 6 of the <abbr title="World Wide Web Consortium">W3C</abbr> Patent Policy](https://www.w3.org/Consortium/Patent-Policy/#sec-Disclosure).

이 문서는 [<abbr title="World Wide Web Consortium">W3C</abbr> 특허 정책](https://www.w3.org/Consortium/Patent-Policy/)에 따라 운영되는 그룹이 작성하였습니다. <abbr title="World Wide Web Consortium">W3C</abbr>는 그룹의 성과물에 관한 [모든 공개 특허 공개 목록](https://www.w3.org/2004/01/pp-impl/72531/status)을 관리합니다. 이곳에서는 특허 공개에 대한 지시사항도 포함됩니다. [필수 주장(들)](https://www.w3.org/Consortium/Patent-Policy/#def-essential)을 포함한다고 생각되는 특허에 대하여 실제 지식을 보유한 개인은 [<abbr title="World Wide Web Consortium">W3C</abbr> 특허 정책의 섹션6](https://www.w3.org/Consortium/Patent-Policy/#sec-Disclosure)에 의하여 정보를 공개하여야 합니다.

This document is governed by the [1 March 2017 <abbr title="World Wide Web Consortium">W3C</abbr> Process Document](https://www.w3.org/2017/Process-20170301/).

이 문서는 [2017년 3월 1일 <abbr title="World Wide Web Consortium">W3C</abbr> 프로세스 문서](https://www.w3.org/2017/Process-20170301/)를 적용받습니다.

[맨 위로](#소셜-웹-프로토콜-social-web-protocols)
