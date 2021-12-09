자바스크립트 메모리 준비
===

## 메모리 준비 과정
```js
var b = {나이:20}
```

1. 콜스택 0에서 시작해서 렉시컬 환경에서  Global 환경레코드로 넘어간다.

2. 변수가 var이기때문에 object로 환경레코드에서 window로 넘어가서 식별자 b를 셋팅하고 undefined 할당하는 초기화하고 arguments 객체(function 객체)를 생성한다. 

3. 다시 처음으로 돌아와서 Declarative 환경레코드 생성하고 변수나 함수가 없기때문에 null이 할당된다. (var는 전연변수로 object로들어간다.)           

4. this 바인딩을 한다. 

5. outer 환경 참조를 설정한다. 없을 경우 null. (외부 lexical환경에 접근할 수 있음을 의미한다. 현재 환경에서 변수를 찾을수 없다면 외부 환경에서 변수를 찾을수 있다.)

6. global 코드 실행  b 변수에 값을 할당     


```js
var b = 30;
let a = 100;

if (a > 50) {
  let a = 10;
  console.log(a);
}
```
1. 콜스택0에서 시작 Global 환경레코드 -> object 환경레코드 -> window에서 식별자 b 셋팅 하고 undefined 초기화 -> argument 생성

2. 처음으로 돌아와서 declarative 환경레코드에서 식별자 a를 셋팅한다. (let은 변수 선언문이에 도달했을때 초기화가 이루어지기 때문에 undefined가 아니다. 그냥 a만 셋팅 -> 변수를 위한 메모리 공간 확보하지 않음)

3. this 바인딩한다. 

작성중...