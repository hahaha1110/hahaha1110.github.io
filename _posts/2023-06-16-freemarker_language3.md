---
title: 프리마커 템플릿 언어 (FTL;Freemarker Template Language) - 3
author: ha
date: 2023-06-19 14:30:00 +0900
categories: [Language, Freemarker]
tags: [Language, Freemarker, ftl, html, 템플릿]
render_with_liquid: false
img_path: /assets/img/20230616/
---

## Freemarker 예제

### TLD 파일

- fmtag.tld (WEB-INF 아래 위치)

```xml
<?xml version="1.0" encoding="ISO-8859-1" ?>
<!DOCTYPE taglib
      PUBLIC "-Sun Microsystems, Inc.//DTD JSP Tag Library 1.1//EN"
      "http://java.sun.com/j2ee/dtds/web-jsptaglib_1_1.dtd">
<taglib>
  <tlibversion>2.0<.tlibversion>
  <jspversion>1.1</jspversion>
  <shortname>FreeMarker JSP Support</shortname>

  <tag>
   <name>template</name>
   <tagclass>freemarker.ext.jsp.FreemarkerTag</tagclass>
   <bodycontent>tagdependent</bodycontent>
   <info>Allow evaluation of FreeMarker templates inside JSP</info>
   <attribute>
    <name>cashing</name>
    <required>false</required>
   </attribute>
  </tag>
</taglib>
```

### java 파일

- SimpleBean.java (WEB-INF/classes/freemarker/examples/jsp)
- Custom Tag 수행을 위한 Tag Handler Class

```java
package freemarker.examples.jsp;

public class SimpleBean
{
  private static String[] arr = {"a","b","c","d"};
  private String theString = "Hello from " + toString();

  public void setString(String foo)
  {
    theString = foo;
  }

  public String getString()
  {
    return theString;
  }

  public String[] getArray()
  {
    return arr;
  }
}
```

### jsp 파일

- freemarker2.jsp (View 파일)

```jsp
<%@ page contentType="text/html; charset=euc-kr" %>
<%@ taglib uri="/WEB-INF/fmtag.tld" prefix="fm" %>

<jsp:useBean id="mybean" class="freemarker.examples.jsp.SimpleBean"/>
<jsp:useBean id="mybeanreq" class="freemarker.examples.jsp.SimpleBean" scope="request" />

<fm:template>
<html>
<body>
 <h1>FreeMarker JSP example</h1>
 <hr>
 <p>JSP 페이지</p>

 <#assign mybean = page.mybean>
 <#assign mybeanreq = request.mybeanreq>

 <p>page : ${mybean.string}
 <#list mybean.array as item>
  <br>${item}
 </#list>

 <p><b>Note:</b>
</body>
</html>
</fm.template>
```

출처 :

- [[Freemarker] 프리마커 템플릿 언어 문법(FTL;Freemarker Template Language) 문법](https://soft.plusblog.co.kr/99)

- [https://www.opentutorials.org/module/2/2824](https://www.opentutorials.org/module/2/2824)

- [http://wiki.gurubee.net/pages/viewpage.action?pageId=1343682&](http://wiki.gurubee.net/pages/viewpage.action?pageId=1343682&)

- [http://wiki.gurubee.net/display/SWDEV/FreeMarker?](http://wiki.gurubee.net/display/SWDEV/FreeMarker?)

- [ http://blog.naver.com/singing4u?Redirect=Log&logNo=30011135160](http://blog.naver.com/singing4u?Redirect=Log&logNo=30011135160)
