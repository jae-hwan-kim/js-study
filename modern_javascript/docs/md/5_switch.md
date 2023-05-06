# switch 문

여러가지 switch 문에 대해서 알아보자.

## switch 문과 break

switch 문은 break 가 없다면, 실행한 case 이후의 모든 case 를 실행한다. (default 도 실행한다.) 그렇기 때문에 특별한 목적이 없다면 아래 코드와 같이 매 case 에 break 를 넣어주자.

case 4 만 실행한다.

```js
let a = 2 + 2;

switch (a) {
  case 3:
    alert( '비교하려는 값보다 작습니다.' );
    break;
  case 4:
    alert( '비교하려는 값과 일치합니다.' );
    break;
  case 5:
    alert( '비교하려는 값보다 큽니다.' );
    break;
  default:
    alert( "어떤 값인지 파악이 되지 않습니다." );
}
```

## break 가 없는 switch

case 4 부터 default 까지 실행한다.

```js
let a = 2 + 2;

switch (a) {
  case 3:
    alert( '비교하려는 값보다 작습니다.' );
  case 4:
    alert( '비교하려는 값과 일치합니다.' );
  case 5:
    alert( '비교하려는 값보다 큽니다.' );
  default:
    alert( "어떤 값인지 파악이 되지 않습니다." );
}
```

## switch 문에 들어올 수 있는 인수

switch 문에는 어떤 표현식이든 올 수 있다. 아래처럼 `+a + 1`과 `b + 1` 도 들어갈 수 있다. (개인적으로 조금 당황했다...)
```js
let a = "0";
let b = 0;

switch (+a + 1) {
  case b + 1:
    alert("표현식 +a는 1, 표현식 b+1는 1이므로 이 코드가 실행됩니다.");
    break;

  default:
    alert("이 코드는 실행되지 않습니다.");
}
```

## switch 문에서 중요한 자료형
switch 문은 자료형이 같아야 case 로 들어간다. prompt 는 문자열을 반환한다. 아래 코드를 보자. 0, 1 을 입력하면 `case '0'` 과 `case '1'` 로 들어간다. 하지만 3 을 입력하면 `case 3` 으로 가지 않는다.

```js
let arg = prompt("값을 입력해주세요.");
switch (arg) {
  case '0':
  case '1':
    alert( '0이나 1을 입력하셨습니다.' );
    break;

  case '2':
    alert( '2를 입력하셨습니다.' );
    break;

  case 3:
    alert( '이 코드는 절대 실행되지 않습니다!' );
    break;
  default:
    alert( '알 수 없는 값을 입력하셨습니다.' );
}
```

`case 3` 으로 들어가기 위해서는 prompt 또는 arg 를 Nubmer 로 변환시켜줘야한다.

1. `let arg = Number(prompt("..."));`
2. `switch (Number(arg)) { ... }`