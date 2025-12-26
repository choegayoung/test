**프로젝트를 만들기**

폴더 터미널에 npm init 를 쓰면 폴더는 프로젝트가 되며 package.json파일이 생성
각 프로젝트 당 관리를 하기위한 nodemon은 해당 프로젝트 안에 설치.

nodemon 설치 시 해당 프로젝트 안의 파일을 실시간으로 감시하며 변경사항을 도출해준다.

type - commonJS 와 module(ES방식)이 있다.

module 방식
nodemon처럼 요청을 대기한다. 브라우저에서 요청(req)을 하면 응답(res)를 한다.
index파일에  res.writeHead(200, { 'Content-Type': 'text/html; charset=utf-8' }); 코드를 넣으면
html형식으로 한글이 지원


**화면전환**
1) url주소 뒤에 특정 언어를 붙여 if문을 이용해 이동
  if(req.url === "/a"){
    res.end("<h2>a주소 화면</h2>");
  }
  else{
    res.end(text());}
  url전체를 입력할 필요가 없다.
