# 5. Flex Panels Image Gallery
## START
- panels를 flex 속성을 줘서 flexbox로 만들고 paenl에 `flex: 1`을 줘서 해당 박스 안에 모든 요소를 비례하게 배치한다. (참고로 IE의 경우엔 잘 못 되는 경우가 많으니 주의 참고 : https://blueshw.github.io/2019/07/28/advanced-flexbox/)
## Proccess
- 아래와 같이 border를 주면 글씨를 담는 박스가 빨간색 선이 그어지는 것이 확인가능하다.
  ```css
  .panel > * {
    margin: 0;
    width: 100%;
    transition: transform 0.5s;
    border: 1px solid red;
  }
  ```
  - 우리는 이를 화면 중심으로 옮겨야한다. 위에다가 `align-items: center`을 해도 안된다.
  - 왜냐면 `display: flex`를 하지 않았기 때문이다. 이 두 개를 같이 하면 적용된다. (단 `.panels`에 해야 한다.)
  - 또한 `.panels`에 `flex-direction: column`을 해야 글자들이 수직으로 배치가 된다. (https://developer.mozilla.org/ko/docs/Web/CSS/flex-direction)
- `style.css` 파일을 보면 `.open-active`라는 클래스가 있는데 해당 클래스가 적용이 되면, 해당 클래스의 속성 css를 적용시키겠단 뜻이다. 즉, 우리는 JS로 이를 적용했다가 뺏다가만 하면, 쉽게 translate를 시킬 수 있다.
- `.open`도 마찬가지다.
---
## About CSS
- CSS 적용 우선순위
  1. 속성 값 뒤에 `!important`를 붙인 속성
  2. `HTML`에서 `style`을 직접 지정한 속성
  3. `#id`로 지정한 속성
  4. `.클래스`, `:추상클래스`로 지정한 속성
  5. `태그이름`으로 지정한 속성
  6. 상위 객체에 의해 상속된 속성
- 레이아웃 구성
  https://ofcourse.kr/css-course/%EB%A0%88%EC%9D%B4%EC%95%84%EC%9B%83-%EA%B5%AC%EC%84%B1
- `display`의 속성인 `none`, `block`, `inline`, `inline-block`의 차이
  https://ofcourse.kr/css-course/display-%EC%86%8D%EC%84%B1

