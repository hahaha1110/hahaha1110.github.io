---
title: MYSQL 날짜 형식 (유형, format )
author: ha
date: 2023-08-11 15:00:00 +0900
categories: [SQL, MYSQL]
tags: [SQL, MYSQL]
render_with_liquid: false
img_path: /assets/img/20230811/
image: thumb3.png
---

- DATETIME 타입 : `YYYYMMDDhhmmss` 형식

- DATE 타입 : `YYYYMMDD` 형식. `DATE_FORMAT` 으로 `%Y-%m-%d %h:%m:%s` 형식을 지정하면 시분초값은 0으로 채워진다.

[Mysql 공식 문서 12.7 Date and Time Functions](https://dev.mysql.com/doc/refman/8.0/en/date-and-time-functions.html)

### DATE_FORMAT 표

<table><thead><tr><th>FORMAT</th><th>설명</th></tr></thead><tbody><tr><td>%M</td><td>Month 월(Janeary, February ...)</td></tr><tr><td>%m</td><td>Month 월(01, 02, 03 ...)</td></tr><tr><td>%W</td><td>Day of Week 요일(Sunday, Monday ...)</td></tr><tr><td>%D</td><td>Month 월(1st, 2dn, 3rd ...)</td></tr><tr><td>%Y</td><td>Year 연도(1999, 2000, 2020)</td></tr><tr><td>%y</td><td>Year 연도(99, 00, 20)</td></tr><tr><td>%X</td><td>Year 연도(1999, 2000, 2020) %V와 같이쓰임</td></tr><tr><td>%x</td><td>Year 연도(1999, 2000, 2020) %v와 같이쓰임</td></tr><tr><td>%a</td><td>Day of Week요일(Sun, Mon, Tue ...)</td></tr><tr><td>%d</td><td>Day 일(00, 01, 02 ...)</td></tr><tr><td>%e</td><td>Day 일(0, 1, 2 ..)</td></tr><tr><td>%c</td><td>Month(1, 2, 3 ..)</td></tr><tr><td>%b</td><td>Month(Jen Feb ...)</td></tr><tr><td>%j</td><td>n번째 일(100, 365)</td></tr><tr><td>%H</td><td>Hour 시(00, 01, 24) 24시간 형태</td></tr><tr><td>%h</td><td>Hour 시(01, 02, 12) 12시간 형태</td></tr><tr><td>%I(대문자 아이)</td><td>Hour 시(01, 02 12) 12시간 형태</td></tr><tr><td>%l(소문자 엘)</td><td>Hour 시(1, 2, 12) 12 시간 형태</td></tr><tr><td>%i</td><td>Minute 분(00, 01 59)</td></tr><tr><td>%r</td><td>hh:mm:ss AP</td></tr><tr><td>%T</td><td>hh:mm:ss</td></tr><tr><td>%S, %s</td><td>Second 초</td></tr><tr><td>%p</td><td>AP, PM</td></tr><tr><td>%w</td><td>Day Of Week (0, 1, 2) 0부터 일요일</td></tr><tr><td>%U</td><td>Week 주(시작: 일요일)</td></tr><tr><td>%u</td><td>Week 주(시작 월요일)</td></tr><tr><td>%V</td><td>Week 주(시작: 일요일)</td></tr><tr><td>%v</td><td>Week 주(시작:월요일)</td></tr></tbody></table>

### 예시

- 데이터: YYYY-MM-DD
- 출력물: YY-MM-DD

```sql
 SELECT
        DATE_FORMAT(CREATE_DATE, '%y-%m-%d') AS CREATE_DATE
  FROM test

+-------------+
| CREATE_DATE |
+-------------+
| 20-03-16    |
+-------------+
```

- 데이터: YYYY-MM-DD hh:mm:ss
- 출력물: YYYY-MM-DD PM / AM hh:mm

```sql
SELECT
    (CASE
         WHEN INSTR(DATE_FORMAT(CREATE_DATE, '%Y-%m-%d %p %h:%i'), 'PM') > 0
         THEN REPLACE(DATE_FORMAT(CREATE_DATE, '%Y-%m-%d %p %h:%i'), 'PM', '오후')
         ELSE REPLACE(DATE_FORMAT(CREATE_DATE, '%Y-%m-%d %p %h:%i'), 'AM', '오전')
         END) AS CREATE_DATE
FROM test

+----------------------+
|      CREATE_DATE     |
+----------------------+
| 2020-03-16 오후 06:20 |
+----------------------+
```

- 출처 : [[MySQL] DATETIME 원하는 유형으로 변경 (YYMMDD)](https://velog.io/@donghoim/MySQL-DATETIME-%EC%9B%90%ED%95%98%EB%8A%94-%EC%9C%A0%ED%98%95%EC%9C%BC%EB%A1%9C-%EB%B3%80%EA%B2%BD-YYMMDD)
