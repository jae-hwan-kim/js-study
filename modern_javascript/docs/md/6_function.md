# ⭐️ function?? 선언식, 표현식

## 함수 선언식 (Function Declartion)

```js
function sayHi() {
  alert( "Hello" );
}
```

<br>

---
## 함수 표현식 (Function Expression)

```js
let sayHi = function() {
  alert( "Hello" );
};
```

### ⭐️ 자바스크립트에서 함수는 특별한 동작을 하는 구조가 아니다??
자바스크립트는 함수를 값으로 취급한다. 함수 표현식이 이를 보여준다. `sayHi` 라는 변수에 함수를 생성하기 때문이다. ( 엄밀하게 말하면 **`동작을 나타내는 값`**이다. )

---

### ❒ alert( sayHi ) 와 alert( sayHi() ) 의 차이
자바스크립트에서는 함수를 실행하기 위해서 함수 이름 뒤에 `()` 를 꼭 붙여줘야 한다. 그렇지 않으면 함수의 코드를 의미하게 된다.

이 함수는 이런 결과를 가져온다.
```js
function sayHi() {
  alert( "Hello" );
}

alert( sayHi );
```
<img src="https://user-images.githubusercontent.com/85930183/236609463-27668e1d-07ba-4067-818e-36df4207b480.png" width="90%">

<br>

함수의 실행 결과를 보기 위해서는 다음과 같이 고쳐주자.
```js
function sayHi() {
  alert( "Hello" );
}

alert( sayHi() );
```
<img src="https://user-images.githubusercontent.com/85930183/236609498-0676aeee-d1f6-456e-be1a-40b2a736408f.png" width="90%">

---

## 함수 표현식 vs 함수 선언문

### 1. 문법

문법의 차이는 위에서 확인할 수 있다.

<br>

### 2. 자바스크립트 엔진이 함수를 생성하는 시기

- 함수 표현식은 실제 실행 흐름이 해당 함수에 도달했을 때 함수를 생성한다. 따라서 실행 흐름이 함수에 도달했을 때부터 해당 함수를 사용할 수 있다.

- 함수 선언식은 함수 선언문은 함수 선언문이 정의되기 전에도 호출할 수 있다. 자바스크립트의 내부 알고리즘에 의해 스크립트를 실행하기 전, 준비 단계에서 전역에 선언된 함수 선언문을 찾고, 해당 함수를 생성한다. <br> ( 스크립트는 함수 선언문이 모두 처리된 이후에서야 실행되며, 따라서 스크립트 어디서든 함수 선언문으로 선언한 함수에 접근할 수 있다. )

이러한 차이로 다음과 같은 특징이 생긴다.

#### ↘︎ 함수 선언식
함수를 나중에 선언해도 작동한다.

```js
sayHi("JaeKim"); // Hello, JaeKim

function sayHi(name) {
alert( `Hello, ${name}` );
}
```

#### ↘︎ 함수 표현식 : 함수를 나중에 선언하면 작동 안한다.

```js
sayHi("JaeKim"); // 작동 안함!

let sayHi = function(name) {
    alert( `Hello, ${name}` );
};
```

<br>

### 3. 스코프

함수 선언식은 선언된 블록 내에서만 접근 가능하다. 하지만 함수 표현식은 변수 선언을 블록 밖에서 하면 함수를 어디에서 선언하든 어디서든 접근 가능하다.

#### 함수 선언식 예시

1. 에러 발생 예시
    ```js
    let age = prompt("나이를 알려주세요.", 18);

    if (age < 18) {

    function welcome() {
        alert("안녕!");
    }

    } else {

    function welcome() {
        alert("안녕하세요!");
    }

    }

    welcome(); // 에러 발생!!

    ```

2. 작동 예시
    ```js
    let age = 16;

    if (age < 18) {
    welcome(); // 안녕!

    function welcome() {
        alert("안녕!");
    }
    welcome(); // 안녕!

    } else {

    function welcome() {
        alert("안녕하세요!");
    }
    }

    welcome(); // 에러 발생!
    ```

#### 함수 표현식 예시

```js
let age = prompt("나이를 알려주세요.", 18);

let welcome;

if (age < 18) {

  welcome = function() {
    alert("안녕!");
  };

} else {

  welcome = function() {
    alert("안녕하세요!");
  };

}

welcome(); // 작동한다.
```

---

## 함수 선언문과 함수 표현식 중 무엇을 선택할까?
함수 선언문을 이용해 함수를 선언하는 걸 먼저 고려하는 게 좋다. 함수 선언문으로 함수를 정의하면, 함수가 선언되기 전에 호출할 수 있어서 코드 구성을 좀 더 자유롭게 할 수 있다.

또한 함수 선언문을 사용하면 가독성도 좋아진다. 코드에서 `let f = function(…) {…}` 보다 `function f(…) {…}` 을 찾는 게 더 쉽지 않을까?

