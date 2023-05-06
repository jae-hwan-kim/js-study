## 문제

### alert( null || 2 || undefined );
피연산자 중 첫 번째 truthy인 2가 출력됩니다.

### alert( alert(1) || 2 || alert(3) );
얼럿 창엔 1, 2가 차례대로 출력됩니다.

### alert( 1 && null && 2 );
피연산자 중 첫 번째 falsy인 null이 출력됩니다.

### alert( alert(1) && alert(2) );
얼럿 창엔 1, undefined가 차례대로 출력됩니다.

### alert( null || 2 && 3 || 4 );
얼럿 창엔 3이 출력됩니다.
