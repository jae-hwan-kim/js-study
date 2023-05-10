# 자료구조

## 배열

### 선언 방식

```js
let arr = new Array();
let arr = [];
```

### 배열 요소의 자료형
제약이 없다.
```js
// 요소에 여러 가지 자료형이 섞여 있다.
let arr = [ '사과', { name: '이보라' }, true, function() { alert('안녕하세요.'); } ];

// 인덱스가 1인 요소(객체)의 name 프로퍼티를 출력.
alert( arr[1].name ); // 이보라

// 인덱스가 3인 요소(함수)를 실행.
arr[3](); // 안녕하세요.
```

### 3가지 종류의 반복문 `for`, `for .. of`, `for .. in`

* for
```js
let arr = ["사과", "오렌지", "배"];

for (let i = 0; i < arr.length; i++) {
  alert( arr[i] );
}
```

* for .. of
```js
let fruits = ["사과", "오렌지", "자두"];

// 배열 요소를 대상으로 반복 작업을 수행
for (let fruit of fruits) {
  alert( fruit );
}
```

* for .. in
```js
let arr = ["사과", "오렌지", "배"];

for (let key in arr) {
  alert( arr[key] ); // 사과, 오렌지, 배
}
```

### 배열을 비우는 방법

length 를 이용하여 배열을 쉽게 비울 수 있다. 이게 가능한 이유는 length 의 길이를 직접 조절할 수 있기 때문이다.

```js
let arr = [1, 2, 3, 4, 5];

arr.length = 2; // 요소 2개만 남기고 잘라봅시다.
alert( arr ); // [1, 2]

arr.length = 5; // 본래 길이로 되돌려 봅시다.
alert( arr[3] ); // undefined: 삭제된 기존 요소들이 복구되지 않습니다.
```

그렇기 때문에 `arr.length = 0;` 을 사용해 아주 간단하게 배열을 비울 수 있다.


