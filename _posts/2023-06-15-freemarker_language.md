---
title: 프리마커 템플릿 언어 문법(FTL;Freemarker Template Language) 문법
author: ha
date: 2023-06-16 18:00:00 +0900
categories: [개발, 기타]
tags: [Freemarker, ftl, 템플릿]
render_with_liquid: false
img_path: /assets/img/20230615/
---

## Freemarker란?

자바 템플릿 엔진(Java Template Engine)인 프리마커(Freemarker)를 이용해 템플릿을 작성할 때 사용하는 프리마커 템플릿 언어(Freemarker Template Language, FTL)은 다양한 문법과 기능을 제공한다. 이 문법을 잘 알고 있으면 효율적으로 템플릿을 작성할 수 있다.

공식 메뉴얼 페이지 : [Freemarker 메뉴얼](https://freemarker.apache.org/docs/ref.html)

## 문법 정리

### assign

프리마커 템플릿에서 변수를 사용하고 싶을 때, assign 디렉티브를 사용할 수 있다.

```
<#assign name="Dave">

<#assign codeBlock>
     this code block assigned
</#assign>
```

라고 명시하면 그 다음부터 ${name}을 이용하면 "Dave"라는 값이 찍히게 된다. 혹은 <#assign>과 </#assign> 사이에 있는 코드 블럭을 변수처럼 할당해서 사용할 수도 있다.

### attempt, recover

자바의 Try-Catch 블럭과 유사한 개념이다.

```
<#attempt>
    attempt block
<#recover>
    recover block
</#attempt>
```

우선 attempt block의 템플릿 블럭이 실행된다. 그러다가 문제가 생기면 attempt block에서 실행했던 결과는 전부 롤백되고, recover block이 실행된다.
자바의 Try-Catch 구문처럼 여러번 중첩해서 사용할 수 있다.

### autoesc

[오토 이스케이핑(Auto Escaping)](https://freemarker.apache.org/docs/dgui_misc_autoescaping.html)(Auto Escaping)과 관련된 기능이다.

```
<#autoesc>
    ...
</#autoesc>
```

XML이나 HTML 같은 문서를 출력할 때, 이스케이핑 해야하는 문자들이 있다. 예를 들어서 '<' 문자나 '>' 문자는 태그를 열고 닫을 때 사용한다. 따라서 사용자 데이터에 이 문자가 들어있으면 출력되는 결과 문서가 유효한(Valid) XML, HTML 문서가 아니게 된다.
