---
title: MYSQL 데이터 타입
author: ha
date: 2023-08-11 17:00:00 +0900
categories: [SQL, MYSQL]
tags: [SQL, MYSQL]
render_with_liquid: false
img_path: /assets/img/20230811/
image: thumb3.png
---

## 문자형 데이터 타입

- Oracle

<table style="border-collapse: collapse; width: 99.186%; height: 297px;" border="1" data-ke-style="style12" data-ke-align="alignLeft">
<tbody>
<tr style="height: 20px;">
<td style="width: 32.1023%; height: 20px; text-align: center;">데이터 타입</td>
<td style="width: 67.8977%; height: 20px; text-align: center;">설명</td>
</tr>
<tr style="height: 20px;">
<td style="width: 32.1023%; height: 20px;">CHAR(n)</td>
<td style="width: 67.8977%; height: 20px;">&nbsp;고정길이 문자 / 최대 2,000byte / 디폴트 값은 1byte</td>
</tr>
<tr style="height: 20px;">
<td style="width: 32.1023%; height: 20px;">VARCHAR2(n)</td>
<td style="width: 67.8977%; height: 20px;">&nbsp;가변길이 문자 / 최대 4,000byte / 디폴트 값은 1byte</td>
</tr>
<tr style="height: 20px;">
<td style="width: 32.1023%; height: 20px;">NCHAR(n)</td>
<td style="width: 67.8977%; height: 20px;">&nbsp;고정길이 유니코드 문자(다국어 입력가능) / 최대 2,000byte / 디폴트 값은 1byte</td>
</tr>
<tr style="height: 20px;">
<td style="width: 32.1023%; height: 20px;">NVARCHAR(n)</td>
<td style="width: 67.8977%; height: 20px;">&nbsp;가변길이 유니코드 문자(다국어 입력가능) / 최대 2,000byte / 디폴트 값은 1byte</td>
</tr>
<tr style="height: 20px;">
<td style="width: 32.1023%; height: 20px;">LONG</td>
<td style="width: 67.8977%; height: 20px;">&nbsp;최대 2GB 크기의 가변길이 문자형</td>
</tr>
<tr style="height: 20px;">
<td style="width: 32.1023%; height: 20px;">CLOB</td>
<td style="width: 67.8977%; height: 20px;">&nbsp;대용량 텍스트 데이터 타입(최대 4Gbyte)</td>
</tr>
<tr style="height: 20px;">
<td style="width: 32.1023%; height: 20px;">NCLOB</td>
<td style="width: 67.8977%; height: 20px;">&nbsp;대용량 텍스트 유니코드 데이터 타입(최대 4Gbyte)</td>
</tr>
</tbody>
</table>

- Mysql

<table style="border-collapse: collapse; width: 99.186%; height: 180px;" border="1" data-ke-style="style12" data-ke-align="alignLeft">
<tbody>
<tr style="height: 20px;">
<td style="width: 32.1023%; height: 20px; text-align: center;">데이터 타입</td>
<td style="width: 67.8977%; height: 20px; text-align: center;">설명</td>
</tr>
<tr style="height: 20px;">
<td style="width: 32.1023%; height: 20px;">CHAR(n)</td>
<td style="width: 67.8977%; height: 20px;">&nbsp;고정 길이 문자 / n은 1 ~ 255( 2^8-1)byte&nbsp;</td>
</tr>
<tr style="height: 20px;">
<td style="width: 32.1023%; height: 20px;">VARCHAR(n)</td>
<td style="width: 67.8977%; height: 20px;">&nbsp;가변길이 문자 / N은 1 ~ 65,535(2^16-1)byte</td>
</tr>
<tr style="height: 20px;">
<td style="width: 32.1023%; height: 20px;">TINYTEXT(n)</td>
<td style="width: 67.8977%; height: 20px;">&nbsp;문자열 데이터 / 최대 255(2^8-1)byte</td>
</tr>
<tr style="height: 20px;">
<td style="width: 32.1023%; height: 20px;">TEXT(n)</td>
<td style="width: 67.8977%; height: 20px;">&nbsp;문자열 데이터 / 최대 65,535(2^16-1)byte</td>
</tr>
<tr style="height: 20px;">
<td style="width: 32.1023%; height: 20px;">MEDIUMTEXT(n)&nbsp;</td>
<td style="width: 67.8977%; height: 20px;">&nbsp;문자열 데이터 / 최대 16,777,215(2^32-1)byte</td>
</tr>
<tr style="height: 20px;">
<td style="width: 32.1023%; height: 20px;">LONGTEXT(n)</td>
<td style="width: 67.8977%; height: 20px;">&nbsp;문자열 데이터 / 최대 4,294,967,295(2^32-1)</td>
</tr>
<tr style="height: 20px;">
<td style="width: 32.1023%; height: 20px;">ENUM('vaue1', 'vaue2'...)</td>
<td style="width: 67.8977%; height: 20px;">&nbsp;열거형 <br/> 정해진 몇가지의 값들 중 하나만 저장 <br/> 최대 65,535개의 개별갑을 가질 수 있고, 내부적으로 정수 값으로 표현됩니다.</td>
</tr>
<tr style="height: 20px;">
<td style="width: 32.1023%; height: 20px;">SET('value1', 'value2'...)</td>
<td style="width: 67.8977%; height: 20px;">&nbsp;집합형 <br/> 정해진 몇가지의 값들 중 여러 개를 저장<br/> 최대 64개의 요소로 구성될 수 있고, 내부적으로 정수 값으로 표현됩니다.&nbsp;</td>
</tr>
</tbody>
</table>

## 숫자형 데이터 타입

- Oracle

<table style="border-collapse: collapse; width: 99.186%; height: 180px;" border="1" data-ke-style="style12" data-ke-align="alignLeft">
<tbody>
<tr style="height: 20px;">
<td style="width: 32.1023%; height: 20px; text-align: center;">데이터 타입</td>
<td style="width: 67.8977%; height: 20px; text-align: center;">설명</td>
</tr>
<tr style="height: 20px;">
<td style="width: 32.1023%; height: 20px;">NUMBER(P,S)</td>
<td style="width: 67.8977%; height: 20px;">&nbsp;가변숫자 / P (1 ~ 38, default : 38) / S (-84 ~ 127, default : 0) / 최대 22byte</td>
</tr>
<tr style="height: 20px;">
<td style="width: 32.1023%; height: 20px;">FLOAT(P)</td>
<td style="width: 67.8977%; height: 20px;">&nbsp;NUMBER의 하위 타입 / P (1 ~ 128, default : 128) / 이진수 기준 / 최대 22byte</td>
</tr>
<tr style="height: 20px;">
<td style="width: 32.1023%; height: 20px;">BINARY_FLOAT</td>
<td style="width: 67.8977%; height: 20px;">&nbsp;32bit 부동소수점 수 / 최대 4byte</td>
</tr>
<tr style="height: 20px;">
<td style="width: 32.1023%; height: 20px;">BINARY_DOUBLE</td>
<td style="width: 67.8977%; height: 20px;">&nbsp;64bit 부동소수점 수 / 최대 8byte</td>
</tr>
</tbody>
</table>

- MySQL

<table style="border-collapse: collapse; width: 99.186%; height: 180px;" border="1" data-ke-style="style12" data-ke-align="alignLeft">
<tbody>
<tr style="height: 20px;">
<td style="width: 32.1023%; height: 20px; text-align: center;">데이터 타입</td>
<td style="width: 67.8977%; height: 20px; text-align: center;">설명</td>
</tr>
<tr style="height: 20px;">
<td style="width: 32.1023%; height: 20px; text-align: left;">BIT(n)</td>
<td style="width: 67.8977%; height: 20px; text-align: left;">&nbsp;비트 값 유형 <br/> n은 값 당 bit 수를 나타내며 1~64 사이의 값을 나타냅니다.</td>
</tr>
<tr style="height: 20px;">
<td style="width: 32.1023%; height: 20px; text-align: left;">BOOL, BOOLEAN</td>
<td style="width: 67.8977%; height: 20px; text-align: left;">&nbsp;해당 유형은 TINYINT(1)의 동의어 입니다 <br/> 0은 false, 0이 아닌 값은 true로 간주 합니다.</td>
</tr>
<tr style="height: 20px;">
<td style="width: 32.1023%; height: 20px; text-align: left;">TINYINT(n)</td>
<td style="width: 67.8977%; height: 20px; text-align: left;">&nbsp;정수형 데이터 타입(1byte) <br/> -128 ~ +127 또는 0 ~ 255수 표현 가능</td>
</tr>
<tr style="height: 20px;">
<td style="width: 32.1023%; height: 20px; text-align: left;">SMALLINT(n)</td>
<td style="width: 67.8977%; height: 20px; text-align: left;">&nbsp;정수형 데이터 타입(2byte) <br/> -32,768 ~ 32,767 또는 0 ~ 65,536수 표현 가능</td>
</tr>
<tr style="height: 20px;">
<td style="width: 32.1023%; height: 20px; text-align: left;">MEDIUMINT(n)</td>
<td style="width: 67.8977%; height: 20px; text-align: left;">&nbsp;정수형 데이터 타입(3byte) <br/> -8,388,608 ~ +8,388,607 또는 0 ~ 16,777,215수 표현 가능</td>
</tr>
<tr style="height: 20px;">
<td style="width: 32.1023%; height: 20px; text-align: left;">INT(n)</td>
<td style="width: 67.8977%; height: 20px; text-align: left;">&nbsp;정수형 데이터 타입(4byte) <br/> -2,147,483,648 ~ +2,147,483,647 또는 0 ~ 4,294,967,295수 표현 가능</td>
</tr>
<tr style="height: 20px;">
<td style="width: 32.1023%; height: 20px; text-align: left;">BIGINT(n)</td>
<td style="width: 67.8977%; height: 20px; text-align: left;">&nbsp;정수형 데이터 타입(8byte) / 무제한 수 표현 가능</td>
</tr>
<tr style="height: 20px;">
<td style="width: 32.1023%; height: 20px; text-align: left;">FLOAT(n,d)&nbsp; &nbsp; &nbsp;</td>
<td style="width: 67.8977%; height: 20px; text-align: left;">&nbsp;부동 소수형 데이터 타입(4byte) / 고정 소수점 사용 형태</td>
</tr>
<tr>
<td style="width: 32.1023%; text-align: left;">DOUBLE(n,d)<br/> DOUBLE PRECISION(n,d) <br/> REAL(n,d)</td>
<td style="width: 67.8977%; text-align: left;">&nbsp;부동 소수형 데이터 타입고정(8byte) / DOUBLE을 문자열로 저장</td>
</tr>
<tr>
<td style="width: 32.1023%; text-align: left;">FLOAT(p)</td>
<td style="width: 67.8977%; text-align: left;">&nbsp;부동 소수점 숫자 <br/> p는 비트 정밀도를 가리키지만, MySQL은 결과 데이터 타입으로 <br/>FLOAT 또는 DOUBLE을 사용할 지를 결정할 때에만 이 값을 사용</td>
</tr>
<tr>
<td style="width: 32.1023%; text-align: left;">DECIMAL(n,d)</td>
<td style="width: 67.8977%; text-align: left;"><span>&nbsp;묶음 고정 소수점 숫자 <br/> n은 전체 자릿수(Precision : 정밀도), d는 소수점 뒷자리수(Scale : 배율)</span><br><span>- DECIMAL(5)의 경우 : -99,999 ~ 99,999</span><br><span>- DECIMAL(5,1)의 경우 : -9,999.9 ~ 9,999.9</span><br><span>- DECIMAL(5,2)의 경우 : -999.99 ~ 999.99</span><br><span>최대 65자리까지 지원</span></td>
</tr>
<tr>
<td style="width: 32.1023%; text-align: left;">DEC(n,d) <br/> NUMERIC(n,d) <br/> FIXED(n,d)</td>
<td style="width: 67.8977%; text-align: left;">&nbsp;DECIMAL과 동의어 <br/>FIXED(n,d)는 다른 데이터베이스 시스템과의 호환을 위해서 사용</td>
</tr>
</tbody>
</table>

## 날짜형 데이터 타입

- Oracle

<table style="border-collapse: collapse; width: 99.186%; height: 100px;" border="1" data-ke-style="style12" data-ke-align="alignLeft">
<tbody>
<tr style="height: 20px;">
<td style="width: 32.1023%; height: 20px; text-align: center;">데이터 타입</td>
<td style="width: 67.8977%; height: 20px; text-align: center;">설명</td>
</tr>
<tr style="height: 20px;">
<td style="width: 32.1023%; height: 20px;">DATE</td>
<td style="width: 67.8977%; height: 20px;">&nbsp;BC 4712년 1월 1일부터 9999년 12월 31일, 연, 월, 일, 시, 분, 초 까지 입력 가능</td>
</tr>
<tr style="height: 20px;">
<td style="width: 32.1023%; height: 20px;">TIMESTAMP</td>
<td style="width: 67.8977%; height: 20px;">연도, 월, 일, 시, 분, 초 + 밀리초까지 입력가능</td>
</tr>
</tbody>
</table>

- MySQL

<table style="border-collapse: collapse; width: 99.186%; height: 180px;" border="1" data-ke-style="style12" data-ke-align="alignLeft">
<tbody>
<tr style="height: 20px;">
<td style="width: 32.1023%; height: 20px; text-align: center;">데이터 타입</td>
<td style="width: 67.8977%; height: 20px; text-align: center;">설명</td>
</tr>
<tr style="height: 20px;">
<td style="width: 32.1023%; height: 20px;">DATE</td>
<td style="width: 67.8977%; height: 20px;">&nbsp;날짜(년도, 월, 일) 형태의 기간 표현 데이터 타입(3byte)</td>
</tr>
<tr style="height: 20px;">
<td style="width: 32.1023%; height: 20px;">TIME</td>
<td style="width: 67.8977%; height: 20px;">&nbsp;시간(시, 분, 초) 형태의 기간 표현 데이터 타입(3byte)</td>
</tr>
<tr style="height: 20px;">
<td style="width: 32.1023%; height: 20px;">DATETIME</td>
<td style="width: 67.8977%; height: 20px;">&nbsp;날짜와 시간 형태의 기간 표현 데이터 타입(8byte)</td>
</tr>
<tr style="height: 20px;">
<td style="width: 32.1023%; height: 20px;">TIMESTAMP</td>
<td style="width: 67.8977%; height: 20px;">&nbsp;날짜와 시간 형태의 기간 표현 데이터 타입(4byte) <br/> 시스템 변경 시 자동으로 그날짜와 시간이 저장</td>
</tr>
<tr>
<td style="width: 32.1023%;">YEAR</td>
<td style="width: 67.8977%;">&nbsp;년도 표현 데이터 타입(1byte)</td>
</tr>
</tbody>
</table>

## 날짜형 데이터 타입

- Oracle

<table style="border-collapse: collapse; width: 99.186%; height: 100px;" border="1" data-ke-style="style12" data-ke-align="alignLeft">
<tbody>
<tr style="height: 20px;">
<td style="width: 32.1023%; height: 20px; text-align: center;">데이터 타입</td>
<td style="width: 67.8977%; height: 20px; text-align: center;">설명</td>
</tr>
<tr style="height: 20px;">
<td style="width: 32.1023%; height: 20px;">CLOB</td>
<td style="width: 67.8977%; height: 20px;">&nbsp;문자형 대용량 객체 고정길이와 가변길이 문자집합 지원</td>
</tr>
<tr style="height: 20px;">
<td style="width: 32.1023%; height: 20px;">NCLOB</td>
<td style="width: 67.8977%; height: 20px;">&nbsp;유니코드를 지원하는 문자형 대용량 객체</td>
</tr>
<tr>
<td style="width: 32.1023%;">BLOB</td>
<td style="width: 67.8977%;">&nbsp;이진형 대용량 객체</td>
</tr>
<tr>
<td style="width: 32.1023%;">BFILE</td>
<td style="width: 67.8977%;">&nbsp;대용량 이진 파일에 대한 위치, 이름 저장</td>
</tr>
</tbody>
</table>

- MySQL

<table style="border-collapse: collapse; width: 99.186%; height: 100px;" border="1" data-ke-style="style12" data-ke-align="alignLeft">
<tbody>
<tr style="height: 20px;">
<td style="width: 32.1023%; height: 20px; text-align: center;">데이터 타입</td>
<td style="width: 67.8977%; height: 20px; text-align: center;">설명</td>
</tr>
<tr style="height: 20px;">
<td style="width: 32.1023%; height: 20px;"><span>BINARY(n)&nbsp;</span><br><span>BYTE(n)</span></td>
<td style="width: 67.8977%; height: 20px;">CHAR의 형태의 이진 데이터 타입 (최대 255byte)</td>
</tr>
<tr style="height: 20px;">
<td style="width: 32.1023%; height: 20px;">VARBINARY(n)</td>
<td style="width: 67.8977%; height: 20px;">VARCHAR의 형태의 이진 데이터 타입 (최대 65,535byte)</td>
</tr>
<tr>
<td style="width: 32.1023%;">TINYBLOB(n)</td>
<td style="width: 67.8977%;">이진 데이터 타입 (최대 255byte)</td>
</tr>
<tr>
<td style="width: 32.1023%;">BLOB(n)</td>
<td style="width: 67.8977%;"><span style="color: #333333;">이진 데이터 타입 (최대 65,535byte)</span></td>
</tr>
<tr>
<td style="width: 32.1023%;">MEDIUMBLOB(n)</td>
<td style="width: 67.8977%;"><span style="color: #333333;">이진 데이터 타입 (최대 16,777,215byte)</span></td>
</tr>
<tr>
<td style="width: 32.1023%;">LONGBLOB(n)</td>
<td style="width: 67.8977%;"><span style="color: #333333;">이진 데이터 타입 (최대 4,294,967,295byte)</span></td>
</tr>
</tbody>
</table>

Reference

- https://coding-factory.tistory.com/416
- http://blog.naver.com/PostView.nhn?blogId=islove8587&logNo=221036036689&parentCategoryNo=&categoryNo=&viewDate=&isShowPopularPosts=true&from=search
- http://www.incodom.kr/DB_-_%EB%8D%B0%EC%9D%B4%ED%84%B0_%ED%83%80%EC%9E%85/MYSQL

- 출처 : [https://kimvampa.tistory.com/72](https://kimvampa.tistory.com/72)
