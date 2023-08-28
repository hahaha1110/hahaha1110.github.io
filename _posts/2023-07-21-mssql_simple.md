---
title: MSSQL 쿼리 정리
author: ha
date: 2023-07-21 15:30:00 +0900
categories: [SQL, MSSQL]
tags: [SQL, MSSQL]
render_with_liquid: false
img_path: /assets/img/20230721/
image: thumb1.png
---

### 날짜 출력 마음대로 요리하기!!

날짜 출력 마음대로 요리하기!! ( 출처 : http://aslike.egloos.com/tb/1627250 )

```sql
--Getdate()
Select Getdate()

--YYYY/MM/DD
Select Convert(varchar(10),Getdate(),111)

--YYYYMMDD
Select Convert(varchar(10),Getdate(),112)

--HH:MM:SS
Select Convert(varchar(8),Getdate(),108)

--HH:MM:SS:mmm
Select Convert(varchar(12),Getdate(),114)

--HHMMSS
Select Replace(Convert(varchar(8),Getdate(),108),':','')

--HHMMSSmmm
Select Replace(Convert(varchar(12),Getdate(),114),':','')

--YYYY/MM/DD HH:MM:SS
Select Replace(Convert(varchar(30),Getdate(),120),'-','/')

--YYYY/MM/DD HH:MM:SS
Select Replace(Convert(varchar(30),Getdate(),121),'-','/')

--YYYY/MM/DD HH:MM:SS
Select Convert(varchar(10),Getdate(),111) + Space(1) + Convert(varchar(8),Getdate(),108)

--YYYYMMDDHHMMSS
Select Convert(varchar(10),Getdate(),112) + Replace(Convert(varchar(8),Getdate(),108),':','')
```

### Oracle 의 LPAD 함수처럼 사용하기

```sql
select replicate('0', 6-LEN('1234'))+'1234'
```

- '1234' 두 부분이 둘다 같이 들어가야함 ( ex : 001234 )

### Oracle 의 LPAD 함수 만들어보기!! ( 출처: joy76.egloos.com/1595438)

```sql
CREATE FUNCTION dbo.Function_lpad( @str AS VARCHAR(8000), @nofchars AS INT, @fillchar AS VARCHAR(8000) = '')

RETURNS VARCHAR(2000)

AS

BEGIN

RETURN

CASE WHEN LEN(@str) >= @nofchars THEN SUBSTRING(@str, 1, @nofchars)

ELSE SUBSTRING(REPLICATE( @fillchar, @nofchars), 1, @nofchars - LEN(@str)) + @str

END

END

GO
```

@str : 입력문자열

@nofchars : 반환할 문자열의 전체길이

@fillchar : 덧붙일 문자열

- 사용예

```sql
SELECT dbo.Function_lpad(seqno+1,3,'0') from cusapp
```

- 오라클 LPAD(seq.nextval) MSSQL으로 변환했던 방법.. 컬럼 max값+1(참고,,)

```sql

-- 오라클
SELECT LPAD(SEQ_TESTSEQ.NEXTVAL, 8, 0) FROM DUAL;

-- mssql
SELECT RIGHT('00000000' + CAST(ISNULL(MAX(CAST(SUBSTRING(TEST_COLUMN, 3, LEN(TEST_COLUMN)) AS INT)), 0) + 1 AS VARCHAR(8)), 8) AS TEST_COLUMN
FROM TEST_TABLE;

```

### 마지막 시퀀스 가져오는 법

```sql
SELECT IDENT_CURRENT('[tableName]')
```

- 출처 : [https://devofhwb.tistory.com/63](https://devofhwb.tistory.com/63)
