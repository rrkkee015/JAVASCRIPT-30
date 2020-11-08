# 2. CSS + JS Clock
## START
- `display: flex`: 기존의 웹페이지를 만들 때 사용하던 올드한 레이아웃 제작방법을 개선하고자 flexbox가 생겼다. 속성 적용 후에 자식 요소들의 배치가 inline화(한 줄 배치) 됨을 기억하고, 직계 자손에게만 적용이 된다.
  - https://thrillfighter.tistory.com/489
- JS 내에 Date 클래스를 이용하여 구현한다.

## PROCESS
- querySelector
  - querySelector로 가져온 객체에 `.style`로 접근하여 style 태그를 직접 조작할 수 있다.