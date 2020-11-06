# 1. Drum Kit
## START
- data-key : `<div>` 속성 중 data-key는  어떤 키를 눌러서 실행시킬 수 있는지 설정하는 것. 본 강의에서는 audio, div에 속성을 부여해서 script 태그 안에서 해당 태그들을 찾을 수 있게 해놓았다.
- `<kbd>` : 키보드 입력을 지정할 때 쓰는 코드이다.
- css에서 `text-transform: uppercase`를 하면 대문자로 바꿔준다.

## PROCESS
- querySelector
  - 리턴되는 값은 인자를 받아 일치하는 baseElement의 자손의 엘리먼트를 가져온다.
  - 이 엘리먼트를 갖고 오면 js로 html의 값들을 변경할 수 있다.
  - id, class, 태그명 등으로 가져올 수 있다.
  - 예제
    ```html
    <body>
      <div class="test">
        <h1>Hello Selector </h1>
      </div>

      <script src="main.js"></script>
    </body>
    ```
    ```Javascript
    const myDiv = document.querySelector(".test"),
          myH1 = myDiv.querySelector("h1");
    
    console.log(myDiv);
    console.log(myH1);
    // h1을 갖고 올 때는 myDiv 자손 엘리먼트 중 h1을 갖고 온다.
    ```
- 콜백 함수로 함수 명을 넘겨도 event를 받을 수 있다는 점을 기억하자.
  ```javascript
  window.addEventListener('keydown', playSound);

  function playSound(e) {
    console.log(e);
  }
  ```