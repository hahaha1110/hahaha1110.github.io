---
title: mysql에서 예약어를 필드명으로 사용할 때
author: ha
date: 2023-08-11 15:00:00 +0900
categories: [SQL, MYSQL]
tags: [SQL, MYSQL]
render_with_liquid: false
img_path: /assets/img/20230811/
image: thumb3.png
---

- 오류

check the manual that corresponds to your MySQL server version for the right syntax to use near '예약어'

- 해결법

`Single quotation` 으로 감싸주기
다른데는 ' 사용하던데 안돼서 헷갈렸음

- example

```sql
CREATE TABLE TESTTABLE (
    SEQ      BIGINT  AUTO_INCREMENT      PRIMARY KEY,
    USER_ID  VARCHAR(100)     NOT NULL,
    `KEY`    VARCHAR(100)   NOT NULL,
    PARAMS   LONGTEXT  ,
    DATE     TIMESTAMP     NOT NULL
);
```
