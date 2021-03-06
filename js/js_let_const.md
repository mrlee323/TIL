# let, const

## ES5  변수
ES5에는 변수로 var만이 존재 했다. 이로인해 생기는 문제점들 이있었다.

1. 함수 레벨 스코프  
블록스코프로는 오로지 함수 코드 블록 스코프만 인정되었다. 그외에 변수 선언은 전역변수로 선언되었다. 또한 for문의 변수또한 외부에서 참조할 수있었다. 
2. var 키워드 생략 허용  
암묵적 전역변수르 양산할 가능성이 컸다.
3. 변수 중복 선언 허용  
의도하지 않은 변수값의 변경이 일어날 가능성이 컸다.

전역변수는 유효 범위가 넓어서 어디에서 어떻게 사용될 것인 지 파악하기 어려우며 의도치 않게 변경될 수 있어 복잡성을 증가시컨다. 변수는 스코프가 좁을 수록 문제에 대체하기 쉽다.

EX6는 var의 단점을 보완하기위해 let과 const를 도입했다

## let, const
let과 cosnt는 이전vvar다른 특징은 스코프를 가진다. var의 경우 코드 블록 내에서 선언되더라도 전역 변수로 사용된다. 하지만 let과 const는 블록내에서만 유효한 범위를 가지고 호출이 가능하다. 

또한 let과 const는 중복선언이 되지않는다. var는 한번 선언한 변수의 이름을 가지고 재선언하더라도 문제가 생기지 않는다. 하지만 let과 const는 변수를 중복 선언하면 문법에러가 발생한다. 

또한 let과 const는 호이스팅이 일어났을때 참조 에러가 발생한다. 이것은 let과 const의 실행 컨텍스트에서 실행 순서때문에 발생한다. 

let과 const에도 차이가 있다. 둘다 블록스코프를 가지는 변수이지만 let은 재할당이 가능한반면 const는 재할당이 불가능하다. 쉽게말해 const는 처음 할당 값이외에 값을 받지 않는다. 그렇기 때문에 const는 처음 선언과 동시에 할당이 이루어져야한다. 

하지만 const의 변수타입이 객체인경우 객체의 내용은 변경할 수있다. 객체의 내용이 변경되더라도 객체 타입 변수에 할당된 주소값은 변경되지 않는다. `객체타입변수선언에는 const를 사용하는것이 좋다.` 


## let, const 호이스팅
호이스팅에서의 참조 에러는 실행컨텍스트에 실행 순서때문이다. 변수의 실행컨텍스트 평가 순서로 변수를 선언하고 메모리를 할당할 공간을 만드는 초기화 단계 이후 코드실행흐 변수를 할당한다. 

var의 경우는 변수 선언과 동시에 초기화가 동시에 진행되어 변수가 선언되기 전에 호이스팅이 되면 undefined값이 가진다. 메모리공간은 있지만 아직 값이 없는 상태이다

하지만 let,const는 코그평가시 선언만 되고 초기화가 진행되지않는다. 그러므로 변수의 이름은 있으나 초기화되지 않아 메모리공간을 할당하지 않았다. 초기화 이전에 변수에 접근하면 참조에러가 발생한다. 스코프의 시작지점부터 초기화 시작지ㅈㅁ까지의 구간을 <strong>일시적 사각지대(TDZ)</strong>라고 부른다. 


## ES6 변수사용
ES6에서는 더이상 var키워드를 추천하지않는다. let과 const를 사용하여 전연변수 사용을 최대한 줄이는게 좋다. let과 const 사용에 있어 재할당이 필요한 경우에 한정해 let 키워드를 사용하고 이때 변수의 스코프를 최대한 좁게 만든다. 변경이 발생하지 않는 원시값과 객체에는  const를 사용하면 재할당이 되지않으므로 var, let보다 안전하다.

변수 선언 시점에서 변수에 재할당 여부를 알수 없을 수 있다. 그럴때는 일단 const를 사용하고 재할당이  필요할때 해당 변수를 let으로 바꾸는 것이 좋다.   