---
title: 오라클과 MYSQL구문의 차이
author: ha
date: 2023-08-11 15:00:00 +0900
categories: [SQL, MYSQL]
tags: [SQL, MYSQL]
render_with_liquid: false
img_path: /assets/img/20230811/
image: thumb3.png
---

### NULL 대체

[오라클]

```sql
NVL(열명, '대체값')
```

[MYSQL]

```sql
IFNULL(열명, '대체값')
```

### SELECT 결과 갯수 제한(페이징처리)

[오라클]

```sql
ROWNUM <= 숫자
```

[MYSQL]

```sql
LIMIT 시작위치, 가져올 데이터 건수
```

### 가상테이블 DUAL

[오라클]

```sql
SELECT 1 FROM DUAL;
```

[MYSQL]

```sql
SELECT 1;
```

### 현재날짜

[오라클]

```sql
SELECT SYSDATE FROM DUAL;
```

[MYSQL]

```sql
SELECT NOW();
```

### 조건식 (IF)

[오라클]

```sql
-- 칼럼이 값과 일치하면 TRUE, 일치하지 않으면 FALSE
SELECT DECODE(칼럼, 값, TRUE일때 출력할 값, FALSE일때 출력할 값) FROM TABLE;
```

[MYSQL]

```sql
SELECT IFNULL(조건식, TRUE일때 값, FALSE일때 값) FROM TABLE;
```

### 날짜 형식

[오라클]

```sql
SELECT TO_CHAR(SYSDATE, 'YYYY-MM-DD') FROM DUAL;
```

[MYSQL]

```sql
SELECT DATE_FORMAT(NOW(), '%Y-%m-%d');
```

### 시퀀스

[오라클]

```sql
CREATE SEQUENCE [시퀀스명]
INCREMENT BY [증감숫자]
START WITH [시작숫자]
NOMINVALUE / MINVALUE [최소값]
NOMINVALUE / MINVALUE [최소값]
CYCLE / NOCYCLE
CACHE / NOCACHE
INSERT TABLE
(SEQ_NBR)
VALUES
(시퀀스명.NEXTVAL)
;
```

[MYSQL]

```sql
-- INSERT 시 자동으로 값이 생성되어 들어감.
CREATE TABLE
( SEQ_NBR INT NOT NULL AUTO_INCREMENT PRIMARY KEY);
```

### 문자열 합치기

[오라클]

```sql
SELECT "A" || "B" FROM DUAL;
SELECT CONCAT("A", "B") FROM DUAL;
```

[MYSQL]

```sql
SELECT CONCAT("A", "B") FROM DUAL;
```

### 문자열 자르기

[오라클]

```sql
SELECT SUBSTR( 문자열/칼럼, 시작위치, 잘라낼 문자열의 길이) FROM DUAL;
```

[MYSQL]

```sql
SELECT SUBSTRING(문자열/칼럼, 시작위치, 잘라낼 문자열의 길이);
```

- 출처 양바른, 업무에 바로 쓰는 SQL 튜닝, 한빛미디어

- 출처 : [https://mantaray.tistory.com/38](https://mantaray.tistory.com/38)
