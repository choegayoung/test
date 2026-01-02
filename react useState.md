 const [data/* 읽기전용변수, 상수값(변경 불가) 
       */, setData /* data의 값을 바꾸어주는 함수 */]
       = useState() /* 배열로 출력됨, 인자값 자리는 index 0, 초기값이다. */

import { useState } from "react";
const Page3 = () => {
    const [array, setArray] = useState([])
    const [txt, setTxt] = useState('')
    const SubmitEvent = e => {
        e.preventDefault() //form의 특성 (어딘가로 이동하려는 특성)을 막는다.
                           //react뿐만 아니라 javascript에서도 이용. 필수임
        if(txt === '') return //예외처리, 입력값이 없으면 실행ㄴㄴ
        setArray([txt, ...array])//새로 들어온 값을 다른 위치에 저장. 새로 들어온 값을 먼저 출력
        setTxt('')//submit이후에 input칸을 초기화, 순서는 논리에 맞게 마지막에 넣기
    }
    return(
        <form onSubmit={SubmitEvent}/* form제출 시 SubmitEvent가 발생한다 */>
          <input type='text' placeholder='글 작성하세요.'
                value={txt} onChange={e => setTxt(e.target.value)}/>
               <button type="submit">입력</button>
               <div>

 array.toReversed()/*배열 순서를 반전하라*/.map((v, i) => <p key={i}>{v}</p>)


useState는 [배열]로 전달하는 것을 받는다

const [a, setA]
a =  setA의 함수가 적용된 값을 담는 변수
setA =  react에게 a의 값을 이걸로 바꿔달라고 **요청**하는 함수


setA와 if문은 useState와 함께 쓸 수가 없다.
**분리해서 쓸 것**
