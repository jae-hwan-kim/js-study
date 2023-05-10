# 자료형

자바스크립트에서 원시값(문자열, 숫자 등)은 객체가 아니다. 하지만 객체처럼 다룰 수 있게 한다. 예를 들면 원시값에서도 메서드를 호출할 수 있다.

## ↘︎ 원시값이란?
문자(string), 숫자(number), bigint, 불린(boolean), 심볼(symbol), null, undefined형으로 총 일곱 가지

## ↘︎ 객체란?
프로퍼티에 다양한 종류의 값을 저장할 수 있다. 함수를 포한한다.

```js
let john = {
  name: "John",
  sayHi: function() {
    alert("친구야 반갑다!");
  }
};

john.sayHi(); // 친구야 반갑다!
```

<br>

### ☝🏻 객체의 특징
객체는 원시값보다 무겁고, 내부 구조를 유지하기 위해 추가 자원을 사용하기 때문에 시스템 자원을 많이 소모한다. (다양한 프로퍼티와 메서드)

<img src="https://github.com/JaeHwan-s-WebServeClass/webserver-nginx/assets/85930183/282d71bf-44e6-44d6-aa9d-2204dd39f6d5" width="90%">

<br>

### ☝🏻 원시값을 객체처람 사용하기?
원시값에 메서드를 활용할 수 있게 하기 위해 **`원시 래퍼 객체 (object wrapper)`**를 만들었다.

예시 )  원시값인 str 을 원시 래퍼 객체로 감싸고 `toUpperCase()` 라는 메서드를 호출했다.
```js
let str = "Hello";
alert(str.toUpperCase());
```

<br>

### ☝🏻 null 과 undefined
원시값 null 과 undefined 은 원시 래퍼 객체가 없다. 어떤 의미에서는 `가장 원시적` 이다.

<br>

### ☝🏻 추가 정보
* 원시값에 메서드를 호출하면 임시 객체가 만들어진다. 이떄 자바스크립트 엔진은 내부 최적화가 잘 되어있어서 메서드를 호출해소 많은 리소스를 사용하지 않는다.

* 원시값에 프로퍼티 추가는 어렵다.

* 원시값을 `new` 로 생성하지 말자.

    -> 원시값은 객체가 아닌데, 객체로 판단한다.

<br>

---

## 숫자형
정수, 부동 소수점 숫자 등의 숫자를 나타낼 때 사용합니다. 정수의 한계는 ±253 입니다.

```js
let billion = 1000000000; // 10억

// 'e' 는 e 왼쪽의 수에 e 오른쪽에 있는 수만큼의 10의 거듭제곱을 곱하는 효과가 있다.
let billion = 1e9;  // 10억, 1과 9개의 0
alert( 7.3e9 );  // 73억 (7,300,000,000)

1e3 = 1 * 1000
1.23e6 = 1.23 * 1000000

let ms = 0.000001;
let ms = 1e-6;

// 10을 세 번 거듭제곱한 수로 나눔
1e-3 = 1 / 1000 (=0.001)

// 10을 여섯 번 거듭제곱한 수로 나눔
1.23e-6 = 1.23 / 1000000 (=0.00000123)
```

### ↘︎ isNaN

인수를 숫자로 변환한 후 NaN 인지 테스트한다.

```js
alert( isNaN(NaN) ); // true
alert( isNaN("str") ); // true
```

`isNaN` 대신에 `=== NaN` 을 쓰면 되지않을까? 라는 의문이 들겠지만, `NaN` 은 아래처럼 자기 자신을 포함하여 어떤 값과 비교해도 `false` 를 반환한다.

```js
alert(NaN === NaN); // false
```


### ↘︎ isFinite

인수를 숫자로 변환하고 `NaN/Infinity/-Infinity` 가 아니면 `true` 를 반환한다.

```js
alert( isFinite("15") ); // true
alert( isFinite("str") ); // false, NaN이기 때문
alert( isFinite(Infinity) ); // false
```

<br>

---

## 문자형
빈 문자열이나 글자들로 이뤄진 문자열을 나타낼 때 사용합니다. 단일 문자를 나타내는 별도의 자료형은 없습니다.

### ↘︎ length 는 프로퍼티이다.
length는 함수가 아니고, 숫자가 저장되는 프로퍼티이다. 그래서 뒤에 괄호를 붙일 필요가 없습니다.

```js
let str = "abc";

console.log(str.length()); // X
console.log(str.length);    // O
```

### ↘︎ 특정 글자에 접근
* `charAt()`
* `[ ]`

특정 문자에 접근할 때는 `[ ]` 와 `charAt()` 을 사용할 수 있다. 두 가지의 차이점은 반환한 글자가 없을 때이다.

```js
let str = `Hello`;

alert( str[1000] ); // undefined
alert( str.charAt(1000) ); // '' (빈 문자열)
```

### ↘︎ 부분 문자열 찾기

* `indexOf(substr, pos)`
* `includes(substr, pos)`
* `startsWith(substr, pos)`
* `endsWith(substr, pos)`

### ↘︎ 부분 문자열 추출하기
* `str.slice(start [, end])`
* `str.substring(start [, end])`
* `str.substr(start [, length])`



## 불린형
true, false를 나타낼 때 사용합니다.

## bigint
길이 제약 없이 정수를 나타낼 수 있습니다.
## null
null 값만을 위한 독립 자료형입니다. null은 알 수 없는 값을 나타냅니다.

## undefined
undefined 값만을 위한 독립 자료형입니다. undefined는 할당되지 않은 값을 나타냅니다.

## 객체형
복잡한 데이터 구조를 표현할 때 사용합니다.

## 심볼형
객체의 고유 식별자를 만들 때 사용합니다.

## typeof
연산자는 피연산자의 자료형을 알려줍니다.

typeof x 또는 typeof(x) 형태로 사용합니다.
피연산자의 자료형을 문자열 형태로 반환합니다.
null의 typeof 연산은 "object"인데, 이는 언어상 오류입니다. null은 객체가 아닙니다.