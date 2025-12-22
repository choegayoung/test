**if문 알아보기**

-기본 구조
if(!/*!는 반대개념을 의미 = false와 같은 개념*/true){ console.log("참");
  } else{ console.log("거짓");
  }

var a = 10;
if(a > 0) /*안에 값을 비교하는 기호 >, >= <, <=, %*/

// 한 if안에 다른 조건을 추가하려면  ||->or , && -> and

if(i===0) continue; ->이 계산값은 건너뛴다. 중괄호 생략가능

-홀수 구하기
for(let i = 0 ; i <= 10;i++){
    if(i==0) continue; /*도출될 값이 0일때 건너뛴다*/
    if(i%2 !== i%2===0 일 때에는 짝수 출력*/) console.log(i)
}

**예제문제 4번**
let 값 = "";
let a = "O";
let b = "X";

for(let i = 0; i < 10 ; i++){
    if(i%2==0){값 = 값+a}
    else {값 = 값 +b}
    /*값 = (i%2==0) ? 값 + a : 값 + b; 으로 바꿔서도 이용 가능*/
    console.log(값)
}
내가 틀린 이유 1. 변수값을 모두 정하지 않았다. let a, let b, let 값 을 지정하지않음
              2. else를 이용하지 않았다. 반대의 경우 출력값을 지정하지 않음



