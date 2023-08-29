---
title: DBMS별 like 검색 쿼리문 정리
author: ha
date: 2023-08-29 15:30:00 +0900
categories: [SQL, etc]
tags: [SQL, Mybatis, MSSQL, Oracle, DB2]
render_with_liquid: false
img_path: /assets/img/20230829/
---

- Oracle, DB2

```sql
AND TESTCOLUMN LIKE '%' || #{searchWord} || '%'
```

- MSSQL

```sql
AND TESTCOLUMN LIKE '%' + #{searchWord} + '%'
```

- MySQL

```sql
AND TESTCOLUMN LIKE concat('%', #{searchWord}, '%')
```
