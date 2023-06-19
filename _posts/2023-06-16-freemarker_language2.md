---
title: 프리마커 템플릿 언어 - 2
author: ha
date: 2023-06-16 14:32:00 +0900
categories: [Language, Freemarker]
tags: [Language, Freemarker, ftl, html, 템플릿]
render_with_liquid: false
img_path: /assets/img/20230616/
---

## Freemarker 문법

자세한 것은 [메뉴얼](http://www.freemarker.org/docs/) 참조.

- ftl tag

```ftl
<# >
```

- 주석

```ftl
<#--주석달기-->
```

### assign

프리마커 템플릿에서 `사용자 정의 로컬변수`를 사용하고 싶을 때, `assign` 디렉티브를 사용할 수 있다.

- 형식 : `<#assign 로컬변수명 = 초기화값>`

- 샘플 1)

```ftl
<#assign CHECK = item_index>
```

---

```ftl
<#assign x=0> <#-- x값을 출력하고자 할때 --> ${x}  -->

<#assign codeBlock>
     this code block assigned
</#assign>
```

라고 명시하면 그 다음부터 `${name}`을 이용하면 `"Dave"`라는 값이 찍히게 된다. 혹은 <#assign>과 </#assign> 사이에 있는 코드 블럭을 변수처럼 할당해서 사용할 수도 있다.

- 형식을 함께 선언할 때 (int 형으로 선언)

```ftl
<#assign x=0 ? int>
```

- 다른 변수를 정의 하고 싶을 때

```ftl
<#setting [새로]=[기존]>
```

- 사이즈를 알고 싶을 때 key 값이 list인 경우

```ftl
<#assign size=list?size>
```

### attempt, recover

자바의 `Try-Catch` 블럭과 유사한 개념이다.

```ftl
<#attempt>
    attempt block
<#recover>
    recover block
</#attempt>
```

우선 `attempt block`의 템플릿 블럭이 실행된다.

그러다가 <b>문제가 생기면 attempt block에서 실행했던 결과는 전부 롤백</b>되고, <b>`recover block`이 실행된다.</b>

자바의 Try-Catch 구문처럼 여러번 중첩해서 사용할 수 있다.

### autoesc

[오토 이스케이핑(Auto Escaping)](https://freemarker.apache.org/docs/dgui_misc_autoescaping.html)(Auto Escaping)과 관련된 기능이다.

```ftl
<#autoesc>
    ...
</#autoesc>
```

XML이나 HTML 같은 문서를 출력할 때, `이스케이핑` 해야하는 문자들이 있다.

예를 들어서 '<' 문자나 '>' 문자는 태그를 열고 닫을 때 사용한다.
따라서 사용자 데이터에 이 문자가 들어있으면 출력되는 결과 문서가 유효한(Valid) XML, HTML 문서가 아니게 된다.

따라서 이런 문자들은 이스케이핑해서` ">", "<"`와 같은 엔티티로 만들어줘야한다.

일반적으로는 freemarker.core.OutputFormat에 HTML, XML, XHTML 등을 설정하거나 text/html, application/xml 같은 MIME 타입을 설정해주면 자동으로 Escaping이 실행되기 때문에 이 디렉티브는 잘 사용하지 않는다.

> 이스케이핑 : 브라우저에 의해 약속된 문자들을 화면에 표시하도록 하는것
> {: .prompt-info }

ex) 줄바꿈 태그 &lt;br /&gt;을 화면에 표시하는 방법

```html
<!DOCTYPE html>
<html>
  <body>
    &lt;br /&gt;은 줄바꿈을 의미하는 태그입니다.
  </body>
</html>
```

참고로 Auto Escaping 기능이 활성화 되지 않은 상황에서 하나의 Interpolation을 Escaping 하려면 `"?esc"`를 붙여주면 된다.

```ftl
${expression?esc}
```

- 참고

|---|---|
|<| lt|
|<=|lte|
|>=|gte|
|> |gt|

### compress

출력 결과에서 불필요한 `공백문자(White-space)`를 제거하는데 사용된다.

```ftl
<#compress>
   ...
</#compress>
```

HTML이나 XML같이 공백 문자가 주요하게 사용되는 경우 사용자 데이터에서 불필요한 공백문자를 지울 필요가 있는데, 이 때 `'#compress'` 디렉티브를 상용하면 된다.

`#compress` 블럭 내에서 2개 이상의 공백 문자가 반복해서 등장하는 경우를 감지해서 하나의 공백문자로 줄여준다. 줄바꿈 문자도 여러개가 등장하면 하나로 줄여준다. 맨 처음과 맨 마지막에 등장하는 공백과 줄바꿈 문자들은 제거된다.

### flush

프리마커 템플릿 엔진이 처리한 결과는 `Output Writer`로 전송된다. 문제는 템플릿의 매 구문마다 바로바로 Output으로 전송되는게 아니라 성능을 위해서 `버퍼링`을 하는데에 있다.

물론 이런 버퍼링은 프리마커 엔진이 아닌, 프리마커 엔진을 사용하는 소프트웨어에서 제어하는 로직이다.

대부분의 경우 이런 버퍼링과 플러쉬(Flush)는 적당한 때에 자동으로 발생한다. 하지만 템플릿의 특정 부분에서 명시적으로 <b>"지금까지 처리한 결과를 플러쉬(Flush)해줘!!"</b>라고 말하고 싶을 때가 있다. 이럴 때 사용하는게 `<#flush>` 디렉티브다.

프리마커 템플릿 엔진이 템플릿을 처리하다가 <#flush> 디렉티브를 만나면, 할당된` java.io.Writer` 인스턴스의 `flush()` 메소드를 호출하게 된다.

### ftl

프리마커 템플릿 파일의 제일 첫 부분에서 사용되는 디렉티브로 <b>템플릿 파일에 대한 정보</b>를 <b>프리마커 엔진</b>에 알려주는 역할을 수행한다.

```ftl
<#ftl param1=value1 param2=value2 ... >
```

특정 파라미터(param1, param2, ...)의 값(value1, value2, ...)을 설정하는 디렉티브다. 파라미터로는 'encoding', 'strip_whitespace', 'strip_text' 등이 사용될 수 있으며, 값으로는 'ISO-8859-5' 같은게 사용될 수 있다.

### function, return

템플릿 파일 <b>내부에서 사용할 함수</b>를 정의한다.` 'macro'` 디렉티브와 비슷한 일을 하지만 function 디렉티브에서는 <b>반드시 return 디렉티브로 반환 값을 명시`</b>해야 한다는 점이 다르다.

```ftl
<#function name param1 param2 ... paramN>
    ...
    <#return returnValue>
    ...
</#function>
```

<b>function 디렉티브 내에서 만들어내는 출력은 모두 무시된다.</b>

내부 로직에 의해서 값을 계산하고 return 디렉티브로 결과를 반환하는 작업만 수행된다.

function 디렉티브 내부에서 if, list 등의 다른 디렉티브는 사용할 수 있다.

### global

`전역 변수`를 만들어 낸다.

```ftl
<#global name=value>
or
<#global name1=value1 name2=value2 ... nameN=valueN>
or
<#global name>
    capture this
</#global>
```

기본적으로 assign 디렉티브와 비슷한 역할을 한다.

<b>다만 assign 디렉티브로 만들어진 변수는 모든 네임스페이스(namespace)에서 보이게 된다.</b>

global 디렉티브로 정의한 변수의 이름이 assign으로 정의한 변수의 이름과 같다면 assign으로 정의한 변수가 유효한 네임스페이스에서는 global 디렉티브로 정의한 변수 대신 assign 으로 정의한 변수가 보이게 된다.

변수의 스코프에 대해서 잘 알고 사용해야 한다.

### if, else, elseif

조건문

- 형식 : `<#if 조건식></#if>`

```ftl
<#if condition>
   ...
<#elseif condition2>
   ...
<#elseif condition3>
   ...
<#else>
   ...
</#if>
```

- 샘플1) string 비교

```ftl
<#if ENTITY.usergrade == "A" >......</#if>
```

- 샘플2) number 비교

```ftl
<#if ENTITY.userclass?number == 3>.....</#if>
```

- 샘플3) boolean 비교

```ftl
<#if ENTITY.isAuth()>.....</#if>
```

<b>조건문을 작성할 때 주의해야 할 점은 `x > 0` 혹은 `x >= 0 `이라는 조건식을 사용할 때, `<#if x > 0> `혹은 `<#if x >= 0>` 으로 작성하면 안된다는 뜻이다. </b>

`'>'` 문자는 프리마커 템플릿 언어의 디렉티브를 닫는 역할을 수행하기 때문이다.

이 문자는 대신 `'gt'`로 대신해야한다.

즉, `<#if x gt 0>` 혹은 `<#if x gte 0>`로 작성해야 맞다는 의미다.

만약 이런 비교가 괄호 안에서 발생한다면 문제는 없다.

즉, <b><#if foo.bar(x > 0)></b>는 문제 없이 동작한다.

### import

다른 템플릿을 불러온다.

```ftl
<#import path as hash>
```

<b>path에 해당하는 템플릿을 불러들여</b> 수행한 다음 <b>hash라는 이름의 네임스페이스</b>로 만들어준다.

path에 해당하는 템플릿에서 만들어진 다양한 변수와 객체들은 hash를 통해서 접근할 수 있다.

ex)

```ftl
<#import "/tmp/test.ftl" as my>
<@my.macro x="abc"/>
```

"/tmp/test.ftl"이라는 템플릿 파일에 정의되어 있는 여러 변수들과 함수(function), 매크로(macro) 정의를 불러들여서 my 라는 네임스페이스 아래에 만들어 준다.

같은 템플릿 파일을 여러번 import 했을 때, 첫 번째 import 만 수행된다. 두 번째부터는 hash 만 생성되고, 같은 네임스페이스를 참조하게 된다. import 를 이용해서 템플릿을 수행하면서 만들어진 출력은 무시된다.

### include

다른 템플릿을 불러온다. <b>import와 다르게 `include` 디렉티브를 이용하면 불러오는 템플릿의 변수와 매크로 등을 공유한다.</b>

즉, 같은 네임스페이스로 불러들인다.

불러오는 템플릿에서 <b>출력되는 Output 내용은 include 태그가 사용된 곳으로 복사</b>된다.

include는 다른 템플릿의 내용을 <b>복사-붙여넣기</b> 하는 개념과 비슷하다.

```ftl
<#include path>
or
<#include path options>
```

include 디렉티브에는 옵션을 줄 수도 있다.

사용할 수 있는 옵션에는 `'parse'`, `'encoding'`, `'ignore_missing'` 등이 있으며, 자세한 내용은 매뉴얼을 참조하면 된다.

### list, else, items, sep, break, continue (반복문)

데이터 모델의 <b>자식 노드들을 순회하는 반복문</b>과 관련된 디렉티브들이다.

배열 형식의 오브젝트를 루핑 처리할때 사용하는 프리마커 지시자이다.

"로컬엘리어스\_index" 라는 변수는 0부터 시작하는 시퀀스번호이다.

- 형식 : `<#list 배열객체 as 로컬엘리어스명></#list>`

- 샘플

```ftl
<#list LIST as item>
번호 : ${item_index+1} | 이름 : ${item.name} | 아이디 : ${item.id}
</#list>
```

1. 가장 간단한 형태의 반복문이다.

```ftl
<#list [Object code에서 key값 ] as [별칭할 값]>
```

ex)

```ftl
<#list sequence as item>
    list block here
</#list>
```

`sequence` 라는 이름의 `컬렉션 데이터`의 각 항목들을 순회하는 코드로 `list` 블럭 내부에서 각 아이템 항목을 `item` 이라는 `변수`로 접근할 수 있다.

예를 들어 ['Dave', 'Tom', 'Nancy'] 라는 users 변수가 있을 때,

```ftl
<#list users as user>
    ${user}
</#list>
```

라고 사용하면, `users`에 들어있는 3명의 이름이 각각 `user`에 할당되어 실행된다.

```ftl
<#list hash as key, value>
    list block here
</#list>
```

만약 <b>해시 맵을 순회</b>하고 싶으면 위 코드처럼 <b>as 뒤에 key, value</b>를 적어주면 된다.

그리고 list 블록안에서 `${key}, ${value}` 형태로 참조해서 사용하면된다. (key, value 말고 다른 변수 이름을 명시해도 좋다)

```ftl
<#list sequence as item>
    Part repeated for each item
<#else>
    Part executed when there are 0 items
</#list>
```

`list` 디렉티브에는 `else` 디렉티브가 짝으로 붙을 수 있다.

list 디렉티브로 순회 할 대상이 없는 경우, 즉 sequence에 해당하는 <b>데이터 모델이 비어있는 경우엔 else 디렉티브의 템플릿 블럭이 실행</b>된다.

```ftl
<#list sequence>
    Part executed once if we have more than 0 items
<#items as item>
    Part repeated for each item
</#items>
    Part executed once if we have more than 0 items
<#else>
    Part executed when there are 0 items
</#list>
```

이렇게 사용하는 경우도 있다.

list 디렉티브를 <b>시작하기 전과 후에 실행할 내용</b>을 표현하고 싶은 경우 <b>items 디렉티브를 list 디렉티브 안쪽에</b> 사용하는 식으로 쓰면 된다.

2. for문 사용

```ftl
for(int i=0;i<10;i++)
<#list  1..10  as i >
      ${i}
<#assign i=i+1?int>
```

### seq

List 디렉티브 내부에서 사용할 수 있는 디렉티브 중에 seq 디렉티브가 있다.

`컬렉션 데이터`를 출력할 때, `구분자`로 사용하고 싶은 문자를 넣을 때 사용된다.

```ftl
<#list users as user>
${user}<#sep>, </#sep>
</#list>
```

이렇게 명시하면 각 user의 출력 사이에 콤마(',') 문자를 준다.

seq 디렉티브가 편한 이유는 <b>마지막 항목에서는 자동으로 구분자를 빼주기 때문</b>이다.

### break

`List` 를 순회하다가 특정 조건을 만났을 때, <b>순회를 종료</b>하려고 할 때 사용된다.

`자바`의 `break;` 와 동일하다

- 샘플1) 루프문을 실행하는 중 5번째에서 escape 하는 예

```ftl
<#list LIST as item>
<#if item_index &gt; 3><#break></#if>
</#list>
```

### continue

list 템플릿 <b>블럭의 이후 부분을 건너뛰고 다음 순회</b>로 넘어가려고 할 때 사용한다. 마찬가지로 `자바`의 `continue;` 와 동일하다.

### local

`assign` 디렉티브와 비슷하게 `변수`를 할당하는 디렉티브다.

```ftl
<#local name=value>
or
<#local name1=value1 name2=value2 ... nameN=valueN>
or
<#local name>
capture this
</#local>
```

하지만 local 디렉티브는 <b>`macro` 디렉티브와 `function` 디렉티브의 안쪽</b>에서만 사용할 수 있다는 제한이 있다.

### macro, nested, return

`매크로(macro)` 변수를 생성한다.

주로 변하지 않는 변수를 생성할 때 사용

- 간단한 예시

```ftl
<#macro green> <#-- 매크로 선언-->
<@green>  <#-- 사용-->
```

`매크로`는 `템플릿 파일의 조각`으로 `사용자 정의 디렉티브(User-defined directive)`로 사용될 수 있다.

```ftl
<#macro name param1 param2 ... paramN>
    ...
<#nested loopvar1, loopvar2, ..., loopvarN>
    ...
<#return>
    ...
</#macro>
```

매크로의 사용처가 매크로의 정의보다 먼저 등장해도 상관없다.

하지만 매크로의 정의가 <b>`include` 디렉티브에 의해서 포함되는 경우라면, 매크로의 사용처보다 include 디렉티브가 먼저 등장</b>해야한다.

---

<h4>샘플</h4>

프리마커 템플릿 전역에서 공통으로 사용되는 UI 디펜던트한 함수는 매크로로 만들어 여러 ftl에서 사용할 수 있도록 해준다. 샘플을 참고하도록 한다.

- 형식 : `<@매크로명 변수1, 변수2, ... />`

- 샘플1) 긴 문자열을 적당한 크기로 자르는 기능의 매크로

- 사용법

```ftl
<@trimX item.title, 20 />
```

- 매크로

```ftl
<#macro trimX src max><#compress>
<#if src?length &gt; max>
${src[OSF:0..max-1]}
<#else>
${src}
</#if>
</#compress></#macro>
```

- 샘플2) YYYYMMDD 형식의 문자열을 YYYY.MM.DD 형식으로 변환하는 매크로

- 사용법

```ftl
<@parseDay item.regdate />
```

- 매크로

```ftl
<#macro parseDay src><#compress>
<#if src?length == 8>
${src[OSF:0..3]}.${src[OSF:4..5]?number}.${src[OSF:6..7]?number}
<#else>
${src}
</#if>
</#compress></#macro>
```

---

### nested

`nested` 디렉티브는 `<#macro>`와 `</#macro>` 사이에 있는 템플릿 조각을 실행하는데 사용된다.

```ftl
<#macro foo >
  * <#nested>
  * <#nested>
</#macro>

<@foo>Hello</@foo>
```

이 템플릿의 경우, `nested` 부분에 `Hello` 가 대체되어서 출력된다.

nested는 `loop` 변수를 포함할 수 있다.

예를 들어

```ftl
<#macro foo>
<#list 1..5 as i>
<#nested i, i * 2, i/2>
</#list>
</#macro>

<@foo ; first, second, thrid>
i = ${first}
i * 2 = ${second}
i / 2 = ${third}
</@foo>
```

매크로의 정의에 있는 `loop` 변수는 3개로 각각 `i`, `i \* 2`, `i / 2`다.

이 들은 사용자 정의 디렉티브에서 사용될 때, 각각 `first`, `second`, `thrid`라는 변수에 할당되어서 사용된다.

### return

`return` 디렉티브를 만나면 `macro`, `function`의 실행을 종료한다.

### noautoesc

`오토 이스케이핑` 기능을 <b>사용하지 않는</b> 구역을 만든다.

`autoesc` 디렉티브의 반대 개념이라고 생각하면 된다.

```ftl
<#noautoesc>
...
</#noautoesc>
```

하나의 `interpolation`에만 적용하려면 `${expression?no_esc}`로 사용하면 된다.

### noparse

<b>프리마커 언어로 해석하지 않는</b> 구역을 만든다.

```ftl
<#noparse>
...
</#noparse>
```

`noparse` 구역에서는 프리마커 언어의 문법이 해석되지 않는다. 다만 `</#noparse>` 구문은 해석된다.

### nt

`No-Trim`의 약자. 이 디렉티브가 있는 라인은 공백 문자를 `Stripping`을 하지 않는다

### outputformat

<b>출력 포맷</b> 설정을 변경한다.

```ftl
<#outputformat formatName>
...
</#outputformat>
```

`formatname`으로는 `"HTML"`, `"XML"` 등이 사용될 수 있다. [outputformat 참조](https://freemarker.apache.org/docs/dgui_misc_autoescaping.html#topic.predefinedOutputFormats)

![buildSucess](outputStream.png)

output 포맷을 적절하게 설정하면, 그 포맷에서 사용하는 <b>특수 문자들을 자동으로 이스케이핑</b> 해준다.

outputformat 디렉티브가 끝나면, 이전에 설정되었던 outputformat으로 자동 복구된다.

### etting

이후 프로세싱에 영향을 미칠 설정 값들을 변경한다.

```ftl
<#setting name=value>
```

이 설정값들은 프리마커 엔진의 해석 방식에 영향을 주게 된다.

예를 들어, 이 디렉티브로 locale, number_format, boolean_format, date_format 등을 변경하게 되면, 이 후에 프리마커 엔진이 데이터를 처리할 때마다 여기에서 바꾼 설정값에 따라 움직이게 된다.

setting 디렉티브로 변경할 수 있는 설정값은 [매뉴얼](https://freemarker.apache.org/docs/ref_directive_setting.html)을 참조하도록 하자.

### stop

템플릿의 프로세싱을 종료한다.

```ftl
<#stop>
or
<#stop reason>
```

에러메시지를 줄 수도 있다.

일반적이지 않은 에러 상황에서만 사용해야 한다.

### switch, case, default, break

자바의 switch, case 문과 동일하다.

```ftl
<#switch value>
<#case refValue1>
...
<#break>
<#case refValue2>
...
<#break>
...
<#case refValueN>
...
<#break>
<#default>
...
</#switch>
```

value의 값에 따라 수행해야하는 블럭이 결정된다.

### t, lt, rt

`공백`문자의 `Trim` 동작에 대한 디렉티브다.

이 디렉티브가 있는 라인은 다음과 같이 동작한다.

- t : 앞 뒤 공백문자를 제거한다.
- lt : 왼쪽에 있는 공백 문자를 제거한다. (공백문자로 시작)
- rt : 오른쪽에 있는 공백 문자를 제거한다. (공백문자들로 종료)

### 사용자 정의 디렉티브(User-defined directive)

`매크로`에서 설명한 내용과 동일하다.

시스템 디렉티브와 다르게 `골뱅이(@)` 문자로 시작한다.

### visit, recurse, fallback

<b>재귀적인 방법으로 트리를 순회하며 데이터를 처리</b>하고 싶을 때 사용하는 디렉티브, 실제로는 `XML 데이터`를 다룰 때 많이 사용한다.

```ftl
<#visit node using namespace>
or
<#visit node>
<#recurse node using namespace>
or
<#recurse node>
or
<#recurse using namespace>
or
<#recurse>
<#fallback>
```

`<#visit node>`를 호출하면 `node?node_name` 에 해당하는 매크로를 찾아서 실행시켜준다.

만약 `node_name`에 해당하는 매크로가 없으면, `@node_type` 이름을 갖는 매크로를 찾아서 실행한다.

만약 이것도 없으면 템플릿 프로세싱은 에러를 내면서 종료한다.

`<#recurse node using ns>`는 `<#list node?children as child><#visit child using ns></#list>`와 동일한 동작을 한다. 짧게 쓰기 위해 사용한다.

visit 디렉티브에 의해서 사용자 정의 디렉티브가 찾아진다.

이 때, fallback 디렉티브를 만나면, 다른 네임스페이스에서 node?node_name에 해당하는 매크로를 찾아보도록 프리마커 엔진에게 알려준다.

같은 이름의 매크로를 오버라이드해서 사용하는 경우 적당한 처리를 위해서 사용할 수 있다.

출처 :

- [[Freemarker] 프리마커 템플릿 언어 문법(FTL;Freemarker Template Language) 문법](https://soft.plusblog.co.kr/99)

- [https://www.opentutorials.org/module/2/2824](https://www.opentutorials.org/module/2/2824)

- [http://wiki.gurubee.net/pages/viewpage.action?pageId=1343682&](http://wiki.gurubee.net/pages/viewpage.action?pageId=1343682&)

- [http://wiki.gurubee.net/display/SWDEV/FreeMarker?](http://wiki.gurubee.net/display/SWDEV/FreeMarker?)

- [ http://blog.naver.com/singing4u?Redirect=Log&logNo=30011135160](http://blog.naver.com/singing4u?Redirect=Log&logNo=30011135160)
