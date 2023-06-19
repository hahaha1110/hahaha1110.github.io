---
title: 프리마커 템플릿 언어 (FTL;Freemarker Template Language) - 1
author: ha
date: 2023-06-16 16:30:00 +0900
categories: [Language, 기타]
tags: [Language, Freemarker, ftl, html, 템플릿]
render_with_liquid: false
img_path: /assets/img/20230616/
---

## Freemarker란?

`자바 템플릿 엔진(Java Template Engine)`인 `프리마커(Freemarker)`를 이용해 템플릿을 작성할 때 사용하는 `프리마커 템플릿 언어(Freemarker Template Language, FTL)`은 다양한 문법과 기능을 제공한다.

이 문법을 잘 알고 있으면 효율적으로 템플릿을 작성할 수 있다.

공식 메뉴얼 페이지 : [Freemarker 메뉴얼](https://freemarker.apache.org/docs/ref.html)

- 프리마커는 자바 서블릿을 위한 `오픈소스 HTML 템플릿 엔진`이다.
- 프리마커에서는 HTML을 템플릿으로 저장하는데 이들은 결국 템플릿 객체로 컴파일 된다.
- 이 템플릿 객체들은 서블리셍서 제공하는 데이터들을 이용하여 HTML을 동적으로 생성한다.
- 프리마커 객체들은 서블릿에서 제공하는 데이터들을 이용하여 HTML을 동적으로 생성한다.

## Freemarker 구조

![freemarker](freemarker.png)

FreeMarker는 표현의 결과물을 HTML(템플릿)로 관리하고 여기에 자바 객체를 연결하여 최종적인 결과를 만들어낸다.

## FreeMarker 셋팅

- 다운로드 : [http://www.freemarker.org/freemarkerdownload.html](http://www.freemarker.org/freemarkerdownload.html)

- 설치

1. freemarker.jar 파일을 WEB-INF/lib 안에 넣는다.
2. ecilpse에서는 프로젝트 마다 lib안에 import 시킨다.
3. Java 코딩 시

```java
import freemarker.template.*;
```

## FreeMarker 함수

### [OSF: x...y]

문자열의 일정 범위를 자를때 사용하는 함수

- 형식 : `${문자열[OSF: 1..5 ]}`

- 샘플1)

```ftl
${item.name[OSF:1..5]}
```

### ?has_content

리스트형 오브젝트가 <b>`null`이 아니고 최소 1개 이상의 컨텐츠를 가지고 있는지</b> 체크하는 함수

`?has_content`는 `?exists`와 `?size>0` 두가지 체크를 동시에 해주는 함수이다.

- 형식 : `리스트오브젝트?has_content`

- 샘플

```ftl
<#if LIST?has_content>.....</#if>
```

### ?exists

`NULL`체크 함수. `if_exists`는 `<#if` 지시자 없이도 사용할 수 있게 해주는 표현식이다.

> ?? : 물음표(?) \*2 로 간단하게 표현할수도 있다.

- 형식 : `오브젝트?exists`

- 샘플1)

```ftl
<#if ENTITY.username?exists>${ENTITY.username?substring(0, 5)}</#if>
```

- 샘플2)

```ftl
<#if LIST?exists && LIST?size &gt; 0>.....</#if>
```

- 샘플3)

```ftl
${ENTITY.username?if_exists}
```

### ?default

`NULL`값을 대체해주는 함수

> !"" : 느낌표(!)와 " " 로 간단하게 표한가능하다.

- 형식 : `오브젝트?default(디폴트값)`

- 샘플1)

```ftl
${item.userclass?default("99")}
```

- 샘플2)

```ftl
${item.age?default(20)}
```

### ?string

문자열로 형변환하는 함수

- 형식 : `오브젝트?string`

- 샘플1)

```ftl
<#if item.age?string == "29">.....</#if>
```

- 샘플2)

```ftl
${item.regdate?string("yyyy/MM/dd HH:mm")}
```

- 샘플3) 숫자를 통화표시로 나타내는 예

```ftl
<#assign MONEY = 1234567>
${MONEY?string(",##0")}
```

### ?number

숫자로 형변환하는 함수

- 형식 : `오브젝트?number`

- 샘플1)

```ftl
<#if item.userclass?number &gt; 3>.....</#if>
```

- 샘플2)

```ftl
${LIST_POINTS[OSF:item.gid?number].entityname?default("")}
```

### ?js_string

문자열을 자바스크립트에 유효하도록 <b>필터링</b>해주는 함수.

문자열내에 `싱글쿼테이션(')`등이 포함되어 스크립트에 <b>오류가 나는것을 방지</b>하기 위하여 사용되는 함수이다.

화면상에는 HTML 태그로 취급된다.

- 형식 : `오브젝트?js_string`

- 샘플1)

문자열 &lt;img src='/image/enterprise.gif'&gt; 을 js_string으로 처리했을때 소스보기를 하면

&lt;img src=\'/image/enterprise.gif\'&gt; 으로 출력된다.

- 샘플2)

```ftl
<a href="javascript:getName('${item.homeurl?js_string}');">
```

### ?html

문자열을 `HTML Symbolic Entity`로 필터링해주는 함수.

문자열내의 HTML태그등을 깨뜨려 화면상으로 출력되도록 할때 사용하는 함수이다.

화면상에 <b>HTML태그가 아닌 일반 문자열로</b> 취급된다.

- 형식 : `오브젝트?html`

- 샘플1)

문자열 &lt;img src='/image/enterprise.gif'&gt;을 html로 처리하면

화면상에 &lt;img src='/image/enterprise.gif'&gt; 로 출력되고

소스보기를 하면 &lt;img src='/image/enterprise.gif'&gt;로 출력된다.

### ?index_of

특정 문자(열)가 <b>시작되는 위치를 정수형으로 반환</b>한다.

인덱스는 0부터 시작됨.

- 형식 : `오브젝트?index_of(특정문자)`

- 샘플1)

`"abcde"?index_of("c")` 는 2를 반환한다.

### ?replace

문자열의 일부를 주어진 문자로 대체하는 함수

- 형식 : `오브젝트?replace(찾을문자열, 대체할문자열)`

- 샘플1)

```ftl
${item.content?replace(">", "&gt;")}
```

### item_has_next

리스트 객체의 <b>다음 컨텐츠가 존재하는지(EOF)</b> 체크하는 함수

- 형식 : `리스트엘리어스이름_has_next`

- 샘플1) 이름과 이름사이에 , 를 찍어주되 마지막은 찍지 않는 경우의 예

```ftl
<#list LIST as item>
${item.name?default("")}<#if item_has_next>,</#if>
</#list>
```

출처 :

- [[Freemarker] 프리마커 템플릿 언어 문법(FTL;Freemarker Template Language) 문법](https://soft.plusblog.co.kr/99)

- [https://www.opentutorials.org/module/2/2824](https://www.opentutorials.org/module/2/2824)

- [http://wiki.gurubee.net/pages/viewpage.action?pageId=1343682&](http://wiki.gurubee.net/pages/viewpage.action?pageId=1343682&)

- [http://wiki.gurubee.net/display/SWDEV/FreeMarker?](http://wiki.gurubee.net/display/SWDEV/FreeMarker?)

- [ http://blog.naver.com/singing4u?Redirect=Log&logNo=30011135160](http://blog.naver.com/singing4u?Redirect=Log&logNo=30011135160)
