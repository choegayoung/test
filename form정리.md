**form**

<input type="text"> - 글 입력란 생성
*placeholder 입력란 안에 보이는 글자 입력란

<input type="submit"> - 네트워크로 input에 입력한 정보를 보내는 버튼 생성
*<butten type="submit">제출</butten>과 동일한 기능을 가진다.

<input type="radio"> - 여러 항목 중 택일만 가능한 리스트 생성
*<value> 값이 필수. 
ex) <form>
  <input type="radio" name="gender"/*정보의 묶음파일*/ value="M" /*컴퓨터에 보낼 값*/> 남자
  <input type="radio" name="gender" value="F"> 여자
  <button type="submit">전송</button>
</form>

<input type="" name=""/> 필수
type에 따라 속성이 달라 배치가 의도와 달라질 수 있음

<input type="checkbox">

코드 정리

object-fit: cover
이미지 비율을 유지하면서 부모 영역을 꽉 채움
필요하면 이미지 일부 잘림

text-decoration: none;
밑줄 제거
*단 <a>태그를 지울 경우 <a>태그 안에 넣어줄 것

요소 겹치기
부모 태그에 class="position-relative" 코드 넣고
겹칠 요소 태그에 style="position: absolute;" 넣을 것

UI제작 시 <style>부분을 따로 빼서 css확장명으로 저장가능
html 파일에는 <head>부분에 <link rel="stylesheet" href="/*css확장 파일명*/"> 입력

input의 사이즈 제한 = {max-width: /*필요한 값*/}
정렬이 필요할 땐 부모요소에 넣어주는 것이 편함


