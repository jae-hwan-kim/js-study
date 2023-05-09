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

모던 자바스크립트에서 지원하는 모든 기능을 활성화하려면 스크립트 맨 위에 'use strict'를 적어줘야 한다.

```js
'use strict';

...
```

'use strict'는 스크립트 최상단이나 함수 본문 최상단에 있어야 한다.

'use strict'가 없어도 코드는 정상적으로 동작한다. 다만, 모던한 방식이 아닌 '하위 호환성’을 지키면서 옛날 방식으로 동작한다. 될 수 있으면 모던한 방식을 사용하자.

참고로, 추후에 배우게 될 클래스와 같은 몇몇 모던 기능은 엄격 모드를 자동으로 활성화한다.

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

## ❒ alert, prompt, confirm

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

### 예시1
<img src="https://user-images.githubusercontent.com/85930183/236407293-83f62b6b-ae5e-446a-b3f1-62685d2f2999.png" width="90%">

<br>

### 예시2
밑에 예시의 변수 a 는 문자열이다. 그래서 switch 문에서 + 를 붙여서 숫자형으로 바꿔줘야 case 에 들어가게 된다.

하지만 그냥 a 를 넣게 되면 case 에 들어가지 않고, default 가 실행된다.
```
let a = "1";
let b = 0;

switch (+a) {
  case b + 1:
    alert("표현식 +a는 1, 표현식 b+1는 1이므로 이 코드가 실행됩니다.");
    break;

  default:
    alert("이 코드는 실행되지 않습니다.");
}
```
<img src="https://user-images.githubusercontent.com/85930183/236604353-4d6ab3d1-04b5-4cf1-8cc8-105d6a22b87a.png" width="90%">


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

<br>

---

## ❒ 인수 유무에 따른 매개 변수 값 할당 차이

다음은 showMessage 함수이다.

```js
function showMessage(from, text = anotherFunction()) {
  // anotherFunction()은 text값이 없을 때만 호출됨
  // anotherFunction()의 반환 값이 text의 값이 됨
}
```

showMessage 함수에 인자를 어떻게 넣느냐에 따라 할당되는 값이 달라진다.
```js
// 1. 두 번째 인자가 없을 경우, showMessage 의 text 매개 변수는 anotherFunction() 의 반환값을 할당한다.
showMessage("Ann");

// 2. 두 번째 인자가 있을 경우, showMessage 의 text 매개 변수는 "Hi" 를 할당한다.
showMessage("Ann", "Hi");

```

### ❓ 궁금한 것...
테스트를 통해 인자의 유무에 따른 console 값을 확인했다. 그런데 의문이 드는건 `undefiend 가 왜 호출되는 것일까?` 이다.
```js
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
<script>
    
function anotherFunction() {
    console.log("anotherFunction() is called");
}

function showMessage(from, text = anotherFunction()) {
    console.log(text);
}

showMessage("Ann");
showMessage("Ann", "Hi");

</script>
</body>
</html>
```
도대체 왜❓❗️❓❗️❓❗️❓❗️❓❗️❓
<img src="https://user-images.githubusercontent.com/85930183/236607577-3fb7e855-ad3e-4740-8f93-02d695ea1fcc.png" width="90%">

### ☝🏻 옛날 방식에서 매개 변수 기본값 설정 방법
오... 이 방식은 굉장히 익숙하다ㅋㅋㅋ C 와 C++ 의 방식이 아니던가?!

```js
// 1.
function showMessage(from, text) {
  if (text === undefined) {
    text = 'no text given';
  }

  alert( from + ": " + text );
}
```

이 방식은 참신했다. false 값을 반환하는 `||` 연산을 활용할 생각을 하다니, 대단스...!
```js
// 2.
function showMessage(from, text) {
  // text의 값이 falsy면 기본값이 할당됨
  // 이 방식은 text == ""일 경우, text에 값이 전달되지 않은것과 같다고 간주한다..
  text = text || 'no text given';
  ...
}
```

### ☝🏻 || 과 ?? 을 사용하는 방법

만약 text 에 숫자 0을 넘기고 싶을 때는 `??` 을 사용해야한다. `||` 는 0 을 `false` 로 인식하기 때문이다.

```js
function showMessage(text) {
  // 첫 번째로 값이 true 인 것을 반환. 0 을 false 로 인식
  alert(text || 'no text given'); // no text given

  // 첫 번째로 값이 있는 것을 반환. 0 을 숫자로 인식
  alert(text ?? 'no text given'); // 0
}

showMessage(0);
```

<br>

---

## ❒ 주석

### 1. 주석에 들어가면 좋은 내용
  * 고차원 수준 아키텍처 <br>
    컴포넌트 간 상호작용에 대한 설명, 상황에 따른 제어 흐름 등은 주석

  * 함수 용례 <br>
    Doxgen
    ```js
    /**
    * x를 n번 곱한 수를 반환함
    *
    * @param {number} x 거듭제곱할 숫자
    * @param {number} n 곱할 횟수, 반드시 자연수여야 함
    * @return {number} x의 n 거듭제곱을 반환함
    */
    function pow(x, n) {
      ...
    }
    ```
  * 명확해 보이지 않는 해결 방법에 대한 설명 <br>
    유지 보수에 도움이 된다.

<br>

### 2. 주석에 들어가면 좋지 않은 내용
  * 코드의 동작과 역할에 대한 설명

<br>

---

