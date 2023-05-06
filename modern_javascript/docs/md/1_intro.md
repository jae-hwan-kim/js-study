# 자바스크립트

## 자바스크립트란?
생동감을 불어넣기 위해 만들어진 언어이다. 자바스크립트로 만들어진 프로그램을 스크립트라고 부른다. 이 언어는 클라이언트와 서버 모두에서 사용될 수 있다. 클라이언트에서 사용될 때, 즉 브라우저에서 사용될 때는 엔진이 필요하다. 

## 자바스크립트 엔진?
브라우저에 자바스크립트 가상 머신과 엔진이 있다. 스크립트는 엔진을 거쳐서 브라우저에 실행된다. 다양한 엔진 코드가 있는데 대표적인 2가지는 `V8` 과 `SpiderMonkey` 가 있다.

### 자바스크립트 엔진 작동 원리
1. 엔진이 스크립트를 읽는다. (파싱)
2. 읽어 들인 스크립트를 기계어로 전환한다. (컴파일)
3. 전환한 코드를 실행한다.

## 자바스크립트 강점
1. HTML/CSS 와 통합하여 사용할 수 있다.
2. 모든 주요 브라우저에서 지원하며 기본 언어로 사용한다.

## 자바스크립트로 컴파일 되어 사용되는 언어들
자바스크립트는 모든 사용자들의 요구사항을 만족할 수 없다. 그래서 새로운 언어들이 많이 생겼다. 이 언어들은 자바스크립트로 컴파일되는 과정이 있어야 실행된다. 대표적인 예시는 다음과 같다.

* TypeScript
* Dart
* Flow
* CoffeeScript

이 외에도 자바스크립트로 '트랜스파일’할 수 있는 언어는 많다. 각 언어마다 고유한 기능을 제공한다. 이러한 면에서 웹 개발을 한다면 자바스크립트에 대한 지식은 필수라고 할 수 있다.

## 명세서
JS 에 익숙해지면 더욱 자세한 자세한 정보가 필요할 수 있다. 아래를 참고하자.

* ECMA-262 명세서 <br>
https://www.ecma-international.org/publications-and-standards/standards/ecma-262/

* ECMA-262 공식 버전 초안 <br>
https://tc39.es/ecma262/

* 명세서에 등록된 기능 또는 등록될 기능 <br>
https://github.com/tc39/proposals

## 메뉴얼
궁금한게 생겼을 때는 검색 엔진이나 chatGPT 를 사용하자.
* 구글 검색 엔진을 사용할 때는 [ MDN + 궁금한 것 ] 의 형태로 검색하자
* chatGPT 는... 말해뭐해~~

## 호환성
자바스크립트는 자바스크립트 엔진이 있는 브라우저에서 작동하고, 브라우저마다 갖고 있는 엔진이 다르다.

엔진에 따라 사용이 가능하거나 제약이 있는 자바스크립트 기능이 있을 수 있다. 이때는 다음 사이트에서 확인하자.

* 브라우저가 특정 기능을 지원하는지 확인
https://caniuse.com/

* 암호화 관련 기능 cryptography 사용 가능 여부
https://caniuse.com/cryptography

* 기능에 대한 엔진
https://kangax.github.io/compat-table/es6/