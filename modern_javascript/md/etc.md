# 알쓸신잡

## ❒ ; (세미콜론)
statement 구분은 `;` 또는 `줄 바꿈` 으로 이루어진다. js 는 줄 바꿈이 있으면 암시적으로 `;` 이라고 해석한다.


```js
// 1, 2, 3 은 모두 같은 기능을 한다.
// 1.
alert('Hello'); alert('World');

// 2.
alert('Hello');
alert('World');

// 3.
alert('Hello')
alert('World')
```

물론 statement 가 불완전하다고 판단하면 줄 바꿈을 `;` 으로 안본다. 아래 코드는 6을 alert 한다.
```js
alert(1 +
2
+ 3);
```

자바스크립트가 세미콜론을 자동으로 삽입해주지 못하여 에러가 발생하는 상황도 있다. `[ ]` 가 있다면 줄 바꿈을 `;` 으로 판단하지 않아서 에러가 생긴다.

```js
// 1.
alert("에러가 발생.")
[1, 2].forEach(alert)

// 2.
alert("에러가 발생 안함.");
[1, 2].forEach(alert)
```
위와 같은 상황이 얘기치 않게 발생할 수 있기 때문에 줄 바꿈으로 statement 를 나눴더라도, statement 사이엔 세미콜론을 넣는 것이 좋다.

<br>

---

## ❒ 주석
주석을 달면 코드의 전체적인 길이가 증가한다. 하지만 이는 기능적이 면에서 문제가 되지 않는다.

프로덕션 서버에 배포하기 전에 코드를 압축해주는 도구가 있고, 이 도구들은 주석을 삭제해주기 때문이다.

실행 중인 스크립트엔 주석이 들어가지 않으므로, 주석은 최종으로 배포되는 코드에 부정적인 영향을 끼치지 않는다.

<br>

---

## ❒ 변수 팁
* 변수명에는 문자, 숫자, $, _ 만 들어갈 수 있다.

* 첫 글자는 숫자가 될 수 없다.

* 변수 재사용하기 vs 새로 선언하기

    변수를 재사용하면 변수 선언이 필요없어서 편하지만, 디버깅에 더 많은 시간이 든다.

    모던 자바스크립트 압축기와 브라우저는 코드 최적화를 잘해주기 때문에, 변수를 추가한다고 해서 성능 이슈가 생기지 않는다. 오히려 변수를 다르게 선언하면 코드 최적화에 도움이 될 수 있다.

---

## ❒ 엄격 모드
`'use strict';` 는 예전 버전의 JS 기능을 사용 못하게 한다.

<br>

---

## ❒ 동적 타입 언어
자료의 타입은 있지만 변수에 저장되는 값의 타입은 언제든지 바꿀 수 있는 언어

<br>

---

## ❒ 수학 연산 안전성 보장
자바스크립트에서 행해지는 수학 연산은 '안전’하다고 볼 수 있다.

0으로 나눈다거나 숫자가 아닌 문자열을 숫자로 취급하는 등의 이례적인 연산이 자바스크립트에선 가능하다.

말이 안 되는 수학 연산을 하더라도 스크립트는 터지지 않고 NaN을 반환하며 연산이 종료될 뿐이다.

<br>

---

## ❒ undefined
undefined는 '값이 할당되지 않은 상태’를 나타낼 때 사용한다. 변수는 선언했지만, 값을 할당하지 않았다면 해당 변수에 undefined가 자동으로 할당된다.

```js
let age;

alert(age); // 'undefined'가 출력됩니다.
```

개발자가 변수에 undefined를 명시적으로 할당하는 것도 가능하다.

```js
let age = 100;

// 값을 undefined로 바꿉니다.
age = undefined;

alert(age); // "undefined"
```

하지만 이렇게 undefined를 직접 할당하는 걸 권장하진 않는다.

undefined는 값이 할당되지 않은 변수의 초기값을 위해 예약어로 남겨두고,

변수가 ‘비어있거나’ ‘알 수 없는’ 상태라는 걸 나타내려면 null을 사용하자.

---

## alert, prompt, confirm

<br>

### ↘︎ alert
메시지를 보여준다.

<br>

### ↘︎ prompt
사용자에게 텍스트를 입력하라는 메시지를 띄워줌과 동시에, 입력 필드를 함께 제공한다.

확인을 누르면 prompt 함수는 사용자가 입력한 문자열을 반환하고, 취소 또는 Esc를 누르면 null을 반환한다.

<br>

### ↘︎ confirm
사용자가 확인 또는 취소 버튼을 누를 때까지 메시지가 창에 보여진다.

사용자가 확인 버튼을 누르면 true를, 취소 버튼이나 Esc를 누르면 false를 반환합니다.

---

<br>

## ❒ 단항 연산자 + - 와 숫자형으로의 변환
<img src="https://user-images.githubusercontent.com/85930183/236407293-83f62b6b-ae5e-446a-b3f1-62685d2f2999.png" width="90%">

<br>

---

## ❒ 일치 연산자 (strict equality operator)
동등 연산자 (equality operator) `==` 는 0 과 false 를 구분하지 못한다. 왜냐하면 `==` 는 자료형이 다른 피연산자를 비교할 때 숫자형으로 바꾸기 때문이다.

이럴 때 일치 연산자 `===` 를 사용하면 숫자형으로 바뀌지 않고 비교할 수 있다.
```js
// true
console.log(0 == false);
console.log('' == false);
console.log(null == undefined);

// false
console.log(0 === false);
console.log(null === undefined);

```

<br>

---

## ❒ null 과 undefined 의 연산 에지 케이스
```js
console.log( null > 0 );  // false
console.log( null == 0 ); // false
console.log( null >= 0 ); // true

console.log( undefined > 0 ); // false 
console.log( undefined < 0 ); // false 
console.log( undefined == 0 ); // false 

console.log( undefined == null ); // true
console.log( undefined === null ); // false
```

일치 연산자 ===를 제외한 비교 연산자의 피연산자에 undefined나 null이 오지 않도록 특별히 주의하자.

또한, undefined나 null이 될 가능성이 있는 변수가 <, >, <=, >=의 피연산자가 되지 않도록 주의하자. 만약 변수가 undefined나 null이 될 가능성이 있다고 판단되면, 이를 따로 처리하는 코드를 추가하자.

❗️ null은 오직 undefined와 같다. (`==` 일때만)

<br>

---

## ❒ !!
`!!` 을 사용하면 값을 불린형으로 변환할 수 있다.

```js
console.log( !!"non-empty string" ); // true
console.log( !!null ); // false
```
