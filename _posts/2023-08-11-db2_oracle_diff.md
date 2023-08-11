---
title: DB2와 오라클 차이(날짜, dual)
author: ha
date: 2023-08-11 15:00:00 +0900
categories: [SQL, DB2]
tags: [SQL, DB2]
render_with_liquid: false
img_path: /assets/img/20230811/
image: thumb2.png
---

## dual

- oracle

```sql
select 1 from dual;
```

- DB2

```sql
select 1 from sysibm.dual;
```

## 숫자 타입별 차이 정리

### 날짜, 시간

![orracle_db2_date_diff](orracle_db2_date_diff.png)

### Db2 integer example

> First, create a table named db2_integers that consists of some integer columns:

```sql
CREATE TABLE db2_integers(
    smallint_col SMALLINT,
    int_col INT,
    bigint_col BIGINT
);
```

> Second, insert some values into the table:

```sql
INSERT INTO db2_integers (
    smallint_col,
    int_col,
    bigint_col )
VALUES (
    32767,
    2147483647,
    9223372036854775807
);
```

> Third, query data from the db2_integers table:

```sql
SELECT * FROM db2_integers;
```

참고 :

- [https://www.db2tutorial.com/db2-basics/db2-integer/](https://www.db2tutorial.com/db2-basics/db2-integer/)
- [https://for-my-wealthy-life.tistory.com/10](https://for-my-wealthy-life.tistory.com/10)
