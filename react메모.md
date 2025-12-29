**react**

터미널에 설치할 때에는 여러 버전이 있다.
npm create vite@latest my-app -- --template react <*vite버전이 빠르고 많이 사용됨*>
npx create-next-app@latest <*naxt버전도 이용되기는 함*>
리액트에서는 기본적으로 arrow함수를 이용한다.
그 지역에서만 이용되는 변수는 지역변수로 이용한다.

next 버전
- 기본적으로 module 타입이 적용되어있다.
- jsx영역이 존재해 html형식으로 javascript 구성이 가능하다.
- 함수 호출은 <App /> 형식으로 한다.
- 함수 선언은 무조건 함수명이 대문자로 시작하게 한다.

vite 버전
- next 버전과 유사하나 module 타입이 선언되어 있다.
- css파일을 index.html 파일로 호출하면 콘솔 네트워크 css칸에서 확인이 가능하나
  jsx 파일에 있을 경우 css칸이 아닌, js칸에서 확인 가능하다.
  이미지는 img와 sj칸 모두 확인 가능하다


return 값은 jsx자료형(object)만 된다.(javascript에서는 jsx를 object로 보기 때문.)
배열에서는 각 value마다 고유한 key값이 존재해야한다.
ex) <li key = 1>1번</li>
    <li key = 2>2번</li>
    <li key = 3>3번</li>
그래서 key 값과 index(arr[i]) 값에 for문을 이용해 value값을 반복 가능.
