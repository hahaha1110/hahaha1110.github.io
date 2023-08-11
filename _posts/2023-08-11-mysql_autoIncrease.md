---
title: MYSQL auto_increment 사용법
author: ha
date: 2023-08-11 17:30:00 +0900
categories: [SQL, MYSQL]
tags: [SQL, MYSQL]
render_with_liquid: false
img_path: /assets/img/20230811/
image: thumb3.png
---

## 1. 새로운 테이블에 AUTO_INCREMENT 생성

```sql
CREATE TABLE 테이블이름 (
  컬럼1 INT AUTO_INCREMENT PRIMARY KEY,
  컬럼2 STRING,
    ...
);
```

- AUTO_INCREMENT로 이용할 컬럼은 INT 형 자료형을 가지고 있어야 한다
- 중복이 없는 값이기 때문에 주로 기본키(PRIMARY KEY)로 이용한다 (필수는 아님)
- 기본키가 아니라면 null이 들어가는 것을 방지하기 위해 NOT NULL 조건을 추가해야 한다

## 2. 기존 테이블에 AUTO_INCREMENT 추가

### 1) 특정 컬럼에 AUTO_INCREMENT 추가

```sql
ALTER TABLE 테이블명 MODIFY 컬럼명 INT NOT NULL AUTO_INCREMENT PRIMARY KEY FIRST;
```

- AUTO_INCREMENT를 추가하는 컬럼은 기본키 설정을 가지고 있어야 한다. (무조건은 아니다. 하지만 대부분의 경우에서)
- 해당 컬럼이 기본키 설정이 되어있지 않다면, 위와 같이 기본키 설정을 함께 해준다.
- 이때 해당 컬럼에 이미 값이 들어가 있거나, AUTO_INCREMENT로 생성될 번호보다 높은 값이 들어가 있으면 안 된다. 그렇지 않으면 아래와 같은 에러가 뜬다.

### 2) 특정 컬럼이 이미 기본키로 설정되어있을 경우 AUTO_INCREMENT 추가

```sql
ALTER TABLE 테이블명 MODIFY 컬럼명 INT NOT NULL AUTO_INCREMENT;
```

- 특정 컬럼이 이미 기본키로 설정이 되어 있다면, 그 바탕에 AUTO_INCREMENT를 덮어 씌워주면 된다.
- 번거롭게 기본키를 DROP하고 재설정을 해줄 필요는 없다.

## 3. AUTO_INCREMENT 에 값 대입하여 사용

### 1) JDBC의 경우

```sql
// PrepareStatment로 값을 대입하는데, 첫 번째가 AUTO_INCREMENT가 적용될 행이고, 두 번째는 예시항목이다
String query="INSERT INTO 테이블명 VALUES(0, ?)";
```

- 데이터를 삽입하면 자동으로 번호를 생성해주는 AUTO_INCREMENT는, 일반 DB에서 생성할 경우 대입할 컬럼을 제외하고 값을 넣어주면 된다.
- 하지만 JDBC로 값을 대입해야할 경우, 조회할 항목의 컬럼을 받아와야하기 때문에 AUTO_INCREMENT가 추가된 컬럼을 제외할 수 없다. (에러 발생)
- 이때 AUTO_INCREMENT의 값보다 낮은 수를 대입한다. (1부터 시작할 거라면 0)

## 4. AUTO_INCREMENT 값 초기화

### 1) AUTO_INCREMENT 시작 값 초기화

```sql
ALTER TABLE 테이블명 AUTO_INCREMENT = 숫자;
```

### 2) AUTO_INCREMENT 값 초기화 한 후, 데이터 값 재조정

```sql
ALTER TABLE 테이블명 AUTO_INCREMENT = 1;
SET @ COUNT = 0;
UPDATE 테이블명 SET 컬럼명(AUTO_INCREMENT 설정한 컬럼) = @COUNT := @COUNT + 1;
```

- 출처 : [[MYSQL] auto_increment 생성 / 추가 / 사용 등 정리](https://velog.io/@ejayjeon/MYSQL-autoincrement-%EC%83%9D%EC%84%B1-%EC%B6%94%EA%B0%80-%EC%82%AC%EC%9A%A9-%EB%93%B1-%EC%A0%95%EB%A6%AC)
