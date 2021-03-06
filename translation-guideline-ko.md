[README로 돌아가기](README.md)

# Social Web Protocols 문서 한글 번역 가이드라인

- 임시로 작성한 문서입니다.
- ActivityPub / Activity-Vocabulary / ActivityStreams2.0 번역 가이드라인들과 내용이 유사합니다.

## 1. 번역 단어관련

- 번역하면서 자주 등장하고 오역이 흔했던 단어들 위주로 작성하였습니다.
- 다음 번역은 번역시 작성한 참고사항 표 이며, 절대적인 번역 기준이 아닙니다.

번역방식

- 원문
- 음차
- 번역
- 원문/한글 혼용

원문 | 번역방식 | 번역 | 챕터 | 비고
-- | -- | -- | -- | --
Social Web | 원문 | | Intro
Section | 음차 | 섹션 | Intro
Specifications | 번역 | 규격? 명세서? | Contents
targeting | 음차 | 타겟팅 | Contents
Notes | 번역, 음차 | 참고사항, 노트 | 1
Social Web Community Group | 원문 | | 1
payload | 음차 | 페이로드 | 2
endpoint | 음차 | 엔드포인트 | 2, 7
bridge | 음차 | 브릿지 | 2
type(s) | 번역, 음차 | 유형, 타입 | 2
application | 음차 | 어플리케이션 | 3
Content-Type | 원문 | | 3 | Content-Type 헤더
actor | 음차 | 액터 | 3
content | 번역, 음차 | 내용, 컨텐츠 | 3
return | 번역 | 반환 | 3
content types | 음차 | 컨텐츠 타입 | 3
application | 음차 | 어플리케이션 | 6
entity | 번역 | 엔티티 | 7
subject | 번역 | 주제, 대상, 수신자, ... | 7
activity | 음차 | 액티비티 | 7
semantic | 음차 | 시맨틱 | 7
charter | 번역 | 헌장 | 2,8 
Webmention | 원문 | | 8
WebSub | 원문 | | 8
Web Annotation Protocol | 원문 | | 8

## 2. 번역 일관성

## 3. markdown 등 그 외 관련

@ 종합본 에서는 다음과 같은 양식을 사용했습니다 :

```language-none
번역본
```

@ 개별 챕터 번역본에서는 다음과 같은 양식을 사용했습니다 :

```language-none
원문
번역본
주석
```

@ 예시에서는 다음과 같은 양식을 사용했습니다 :

>예시 N번
>
>```json
>{
>   "무슨무슨 속성": "name이나 summary처럼 번역해도 무관한것들만 번역"
>}
>```

@ `[WORD](LINK)`

- WORD
  - {번역한 단어}를 사용하되, 의미전달이 애매할 경우는 {번역(원문)}
- LINK
  - 개별 파일에서는 원문 링크를 따르기
    - 예: `[Extensibility](https://www.w3.org/TR/activitystreams-core/#extensibility)`
  - [종합본](ActivityVocabulary.md)에는 최대한 내부링크로
    - 예: `[extensibility](#5.-Extensibility)`

@ \`...\`

- 단어 자체가 강조된 부분이므로 번역하지 않고 `백틱`안에 원어 그대로 적기
- 간혹가다 "`object`를... object를..." 처럼 백틱된 단어가 한 문장/문단안에 있는 경우
  - "`object`를... 객체(object)를..." 처럼 해당 `백틱` 이후 첫 등장하는 단어에 번역(원문)으로 적기

@ 주석 양식

- `[//TODO]: # "TODO"`
- `[//Comment]: # "Comment"`
- `[//Link]: # "Link"`

@ Markdown triple-backtick (fence)에 사용한 언어 타입들

- json
- lang-none
