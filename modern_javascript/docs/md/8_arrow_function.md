# 화살표 함수

함수 표현식보다 단순하고 간결한 함수 문법이 있다. 바로 화살표 함수이다!!

## 구문
화살표 함수는 다음과 같은 형태이다. 매개변수로 `(arg1, arg2, ... argN)` 를 받고 `expression` 을 실행하는 함수 `func` 을 선언한다.

```js
// 화살표 함수
let func = (arg1, arg2, ... argN) => expression

// 함수 표현식
let func = function(arg1, arg2, ...argN) {
    expression
    return ...
};
```

매개변수가 하나 일때는 괄호가 없어도 되지만, 매개변수가 없을 때는 괄호가 필요하다.

```js
// 매개변수가 하나일 때
let func = n => {
    expression
    return ...
}

// 매개변수가 없을 때
let func = () => {
    expression
    return ...
}

// ☝🏻 expression 이 한 줄일 때는 중괄호가 필요없다.
let func = () => expression
```
