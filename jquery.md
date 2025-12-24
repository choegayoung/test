**Jquery 기본 문법**
$(document/*문서야*/).ready/*준비가 되면(jquery함수)*/(function(){
  // jQuery 영역
}/*이거를 실행해*/);

function fn(){}
//callback함수

const fn2 = () => {}
//arrow 함수


간단한 버전
- $(function(){
  // jQuery 영역
});

- $(document).ready(() => {console.log("study02.js")});


**의미**
$(document).ready(() => { ... }) 
-> "페이지가 다 만들어지면 이 안에 코드를 실행해"
 function view1() {              
 -> 함수(묶음)선언."이런 일을 하는 기능을 만들게"
 var html =                      
 ->"div들을 담을 상자를 준비했어"
 $("section").html(html);        
 ->"이제 화면에 div들을 그려!"
 $("button").click(function(e){  
 ->"버튼 누르면 짜잔 할 준비"
 const index = $("button").index(e.target);
 ->"지금 누른 버튼이 몇 번째 버튼이야?"
 if(index===0) {
    view1();   } 
 ->"첫 번째 버튼이면 짜잔 해"
