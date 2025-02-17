# 3주차 미션: React-Messenger💌

<!-- @format -->

# react-messenger-TS

안녕하세요 14기 양기욱입니다다다닫

### 링크

[https://react-messenger-14th-navy.vercel.app/](https://react-messenger-14th-navy.vercel.app/)

### 들어가보자구

react-messenger 과제 첫 주차때 전역 state 관리 기능 다시 살려보겠다고 삽질하다가 그냥 react에서 제공하는 useContext, useReducer 로 전역 state 설정하고 Flux 패턴 구현하니 마음이 정말 편해졌는데요..

이번 과제 하기 전에 미리미리 custom hook에 dispatch 로직 추상화를 해놓으니까 다른 플젝 코드 왕창 보고 돌아와도 크게 스트레스 받지 않고 코드 읽고 다시 과제할 수 있었습니다,,

개인 프로젝트할 때는 hoc 사용하면서 container-presenter 패턴을 적용하고자 했었는데 (_전역 state 관리_ _로직_ + _data fetch_ _로직_ 과 _view 로직_ 분리), 확실히 커스텀 훅을 쓰니 container 위치 신경쓰지 않고 로직을 분리할 수 있어서 좋은 것 같습니다! 단점이 뭔지 잘 모를 정도,,, ~~아 그 정도는 아니라구요? ㅠ~~

### 열린 컴포넌트 가보자구

선종님 코드의 준열님 질문에 지나가다 댓글 남긴 내용처럼 (https://github.com/CEOS-Developers/react-messenger-14th/pull/20#discussion_r751444921) **css-in-js**의 장점을 최대한 살리려고 노력하고자 ,,,했습니다.. 최대한..확장가능하게... ~~물론 제 수준에서 ㅎ~~

저도 사실 컴포넌트 확장성... 잘 모르겠는데요^^! 열린 컴포넌트 잘 만드시는 분 비법 전수 바로 가보자고요 ㅜ ㅜ

어쨌든 노력해본 결과 아래처럼 @shared 디렉토리에 공유 컴포넌트를 많이 만들 수 있었습니다!

근데 일단 제 view가 굉장히 간소화되어있어서 뭐 그렇게 재사용성이 높은진 제대로 파악하기 힘드네요 히히

![디렉토리.png](/static/디렉토리.png)

### TS 가보자구

음 저번 주차 과제에서 create chatroom 하고 나서 생성된 채팅방 관련 정보가 안 오는 오류가 있어서 이거 고쳐보겠다고 한 것 같은데 ~~아닌가?~~ TS 적용하면서 바로 고쳤습니다.. 아니 고쳐졌습니다.. create 할 때 `users:UserI[]` 를 보내야하는데 `[ UserI[] ]` 를 보내고 있었던 것입니다.. 맙소사

아무튼 ts최고 ~~근데 정적타입언어는 싫음~~

TS 얘기 나와서 갑자기 생각난 건데 any 타입으로 점진적으로 type 확장가능한 게 진짜 좋은 것 같아요.. 덜 빡치고..

### 그래서 추가한 피쳐

- 채팅방 들어가면 해당 채팅방 참여자들만 헤더에서 셀렉할 수 있게끔 했습니다

  ![1.png](/static/1.png)
- 참여한 채팅방만 나오게 했습니다

  ![2.png](/static/2.png)
- 채팅방을 만들 수 있습니다!

  ![3.png](/static/3.png)

_끝!_
