---
title: "Javascript와 Conditionals"
categories:
  - WEB
tags:
  - Javascript
last_modified_at: 2023-08-13
---

# Javascript와 Conditionals
## JS10

이번에는 Javascript의 조건문에 대해서 다루어 보려한다.

### 조건문

조건문은 아주 간단한 형태로 되어있다.

다음과 같은 형식으로 되어있다.

if, else 형식
```
if (condition) {
	true 일 때 실행
} else {
	false 일 때 실행
}
```
> condition은 boolean으로 판별 가능해야한다.

if, else if, else 형식
```
if (condition) {
	true 일 때 실행
} else if (condition) { false 일 때 여기로 들어옴 
	true 일 때 실행
} else {
	false 일 때 실행
}
```
위와 같이 else if를 통해서 조건문을 계속 늘려나갈 수 있다.

### 논리 연산자

또한 조건문은 논리 연산자를 활용하여 2개 이상의 조건을 엮어서 사용할 수 있다.

다음은 논리 연산자의 연산 결과 이다.

AND 연산자
```
True && False === False
True && True === True
False && True === False
False && False === False
```

OR 연산자
```
True || False === True
True || True === True
False || True === True
False || False === False
```

### 실습

이번에는 위에서 배운 조건문과 논리 연산자들을 바탕으로 실습을 해보고자 한다.

실습을 위해서 몇 가지 함수를 다룰 것이다.

#### prompt()
`prompt()` 함수는 사용자에게 창을 띄울 수 있게 해주고, string을 입력받고 반환한다.

#### parseInt()
`parseInt()` 함수는 string을 입력받고 number일 경우 number로 형 변환하여 반환해준다.
number가 아닐 경우 NaN을 반환한다.

> NaN이란 데이터 타입은 숫자인데, 표현할 수 없는 숫자를 의미한다.

#### isNaN()
`isNaN()` 함수는 입력되는 argument가 number인지 아닌지 판단하여 boolean으로 반환해준다.

함수의 명칭대로 is Not a Number 이기에 **number가 아닐 경우** true를 **number일 경우** false를 반환한다.

> 만약 Javascript에서 datatype을 알고 싶으면 다음과 같이 입력함으로 알 수 있다.
```
consol.log(typeof variable);
```

그렇다면 여태까지 배운 함수들과 조건문, 논리 연산자를 가지고 **술을 마셔도 되는 나이인지 판별하는
계산기**를 만들어 보겠다.

다음과 같이 할 수 있다.

```
const age = parseInt(prompt("How old are you?"));
// prompt 함수를 통해 "How old are you?"라는 질문을 띄우며, 나이를 입력 받는다.
// prompt 함수의 반환 값은 string이기에 parseInt 함수를 통해 string을 number로 바꿔준다.

if (isNaN(age) || age < 0) { // 음수를 입력받았거나, 숫자가 아닌것을 입력받았을 경우 아래 문구를 출력한다. 아닐 경우 다음 조건문으로 넘어간다.
    console.log("Please write a real positive number");
} else if (age < 18) { // 입력받은 나이가 18살 보다 어릴 경우 아래 문구를 출력한다. 아닐 경우 다음 조건문으로 넘어간다.
    console.log("You are too young.");
} else if (age >= 18 && age <= 50) { // 입력받은 나이가 18이상 50이하면 다음 문구를 출력한다. 50보다 높을 경우 다음 조건문으로 넘어간다.
    console.log("You can drink");
} else if (age > 50 && age <= 80) { // 입력받은 나이가 50초과 80이하면 다음 문구를 출력한다. 80보다 높을 경우 다음 조건문으로 넘어간다.
    console.log("You should exercise");
} else if (age === 100) { // 입력받은 나이가 100과 같다면 아래 문구를 출력한다. 아닐 경우 다음 조건문으로 넘어간다.
	console.log("wow you are wise");
} else if (age > 80) { // 입력받은 나이가 80보다 높을 경우 아래 문구를 출력한다.
    console.log("You can do whatever you want.");
}
```

> = 는 값을 할당하는 것이고, === 는 같다는 것을 의미한다. !== 는 같지 않다는 것을 의미한다.

> `if((a && b) || (c && d)) {}` 와 같은 조건문이 있다면, `c && d` 부터 계산된다고 한다. Javascript의 경우
조건문에서 여러 조건문이 동시에 연결 되어 있으면 가장 마지막에 있는 조건문 부터 계산되는 것 같다.

해당 내용들은 노마드 코더의 강의를 학습한 내용을 정리한 내용들이다.  

자세히 내용을 듣고 싶다면 [이 사이트]를 참고하길 바란다.

[이 사이트]: https://nomadcoders.co/javascript-for-beginners/lectures/2888
