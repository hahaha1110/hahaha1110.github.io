---
title: React.js공부 - 1. 자바스크립트 기초
author: ha
date: 2023-06-29 10:30:00 +0900
categories: [Language, React]
tags: [Language, React, javaScript]
render_with_liquid: false
img_path: /assets/img/20230629/
image: React-logo.png
---

## 형 변환

### 명시적 형 변환

- 숫자형으로 형 변환

1. `Number()` : 문자열 포함되면 NaN반환

2. `parseInt(문자열, 진수)` : 문자를 포함한 문자열 변환 가능 <br/>하지만 첫 시작이 문자로 시작하면 NaN반환

![number](number1.png)

![number](number2.png)
_Number() 사용_

![parseInt](number3.png)
_parseInt(문자열, 진수) 사용_

- 문자열로 형 변환

1. `String()`

## 연산자

### null 병합 연산자 (??)

`null 병합 연산자` : 값이 확정된 변수를 찾을 때 사용하는 연산자

`null 병합연산자`인 `??` 를 사용하면 `값이 확정된 변수(null, undefined 제외)`를 쉽게 찾아 낼 수 있음

![nullOperator](nullOperator.png)

![nullOperatorLog](nullOperatorLog.png)

- 둘다 값이 확정되었을 경우 : 연산자 기준 왼쪽 값
- 하나만 확정되었을 경우 : 확정된 값

> 예제) 변수 user에 해당 사용자의 이름이 있다면 이름을, 이름이 없다면 닉네임을 저장

![nullOperatorEx](nullOperatorEx.png)
_이름이 없을 경우_
![nullOperatorExLog](nullOperatorExLog.png)

![nullOperatorEx2](nullOperatorEx2.png)
_이름이 있을 경우_
![nullOperatorExLog2](nullOperatorExLog2.png)

### 동적 타이핑과 typeof 연산자

- `동적 타이핑` : 자바스크립트는 변수에 `값을 저장할 때마다 변수의 자료형이 동적으로 변경`됨.
  이 때문에 변수의 자료형을 정확히 인지하지 못해서 오류가 발생할 수도 있음
- `typeof`연산자 : `타입을 확인`할 때 쓰는 것

![typeOf](typeOf.png)

![typeOfLog](typeOfLog.png)

## 반복문

### 반복문 강제 종료하기, 건너뛰기

- `break` : 조건과 상관없이 반복문 `강제 종료`
- `continue` : 반복을 종료하는 대신 `다음 반복 과정으로 건너뜀`

## 함수

### 함수와 호이스팅

- `호이스팅` : 프로그램에서 `변수나 함수를 호출하거나 접근하는 코드`가 `함수 선언`보다 `위에 있음`에도 불구하고, 마치 `선언코드가 위에 있는 것 처럼 동작`하는 자바스크립트만의 독특한 기능

![hoisting](hoisting.png)

![hoistingLog](hoistingLog.png)
_함수 functionA를 선언하기전에 호출하지만 오류가 발생하지 않음_

### 함수 표현식

`함수`를 `생성`하고 `변수`에 값으로 `저장`

- 아래 코드에서는 함수 이름을 생략함. 변수이름으로 호출하기떄문.
- 이런식으로 `이름을 정의하지 않은 함수`를 `익명함수`라고 함

![function1](function1.png)

- 함수를 변수에 할당할 때는 `()를 붙이지 않고` `함수이름`으로 할당한다.

![function2](function2.png)

- `함수표현식`으로 만든 함수는 함수선언으로 만든 함수와는 달리 `값으로 취급`되기떄문에 `호이스팅 되지 않음`

![function3](function3.png)

### 콜백함수

- 위에서 봤듯 `함수를 값으로` 취급해 `변수`로 저장가능
- 따라서 `함수`는` 다른 함수의 인수`로도 전달 가능.
- 이를 `콜백함수` 라고 한다.

![callbackFunc](callbackFunc.png)

![callbackFuncLog](callbackFuncLog.png)

- `콜백함수를 인수로 받는 함수`를 `고차함수`라고 함.
- 콜백함수의 사용 이유
  1. 중복코드 방지.
  2. 같은 함수인데 여러 동작방식으로 동작하게 할 수 있음
