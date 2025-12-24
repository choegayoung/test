**js파일로 화면을 출력하기**

var page = "" /*출력할 전반적인 부분의 변수*/

for(let i = 0 ; i <25 ; i++){
    if(i%2===0){
         page += '<div class="bg2"></div>' /*div는 문자열이 아니기때문에 문자열로 바꿔야함*/
    }
    else {page += '<div class="bg1"></div>'};
}
document.getElementsByTagName("section")[0]. innerHTML = page;
"문서야, 기본네임택을 가져와. ("이 구역 네임택")의 [세부적인 위치] HTML에 넣어 = 니가 만든거(변수명)"

문서는 위에서부터 읽기때문에 js파일에 태그를 넣고 
html head부분에 <script src="./study01.js"></script>를 넣어도 동작하지 않는다.
--> html <body onload = "함수명()">을 넣고 js파일에 코드를 (함수명)함수로 묶는다.

여러 함수를 따로 관리할 수 있다.

1. 켜는 버튼
function load(){
var page = ""
for(let i = 0 ; i <25 ; i++){
    if(i%2===0){page += '<div class="bg2"></div>';}
    else {page += '<div class="bg1"></div>'};}
document.getElementsByTagName("section")[0]. innerHTML = page;
}

2. 끄는 버튼
function clean(){
    document.getElementsByTagName("section")[0]. innerHTML = " ";
}

3. 만능 버튼
function btn(){
var s = false;
    if(!s){load()
       s = true; }
    else{clean()
       s = false; }
}

이런 식으로 여러 함수를 만들어 놓고 필요한 부분에서만 호출하여 이용.

