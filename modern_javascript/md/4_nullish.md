# nullish 병합 연산자 ??

nullish 병합 연산자 ??를 사용하면 피연산자 중 ‘값이 할당된’ 변수를 빠르게 찾을 수 있다.

```js
let firstName = null;
let lastName = null;
let nickName = "바이올렛";

// null이나 undefined가 아닌 첫 번째 피연산자
alert(firstName ?? lastName ?? nickName ?? "익명의 사용자"); // 바이올렛
```

`||` 연산과 유사하다. 하지만 중요한 차이점은 다음과 같다.
* ||는 첫 번째 truthy 값을 반환한다.
* 첫 번째 정의된(defined) 값을 반환한다.

```js
let height = 0;

alert(height || 100); // 100
alert(height ?? 100); // 0
```