# 2. CSS + JS Clock
## START
- `<input>` 태그의 다양한 type 사용법을 이해한다.
- css에서 전역 변수를 사용하는 법을 이해한다.
- addEventListener에서의 `change`, `mousemove` 를 이해한다.
- html dataset을 이해한다.
- this 속성에 대해 이해한다.
  https://blueshw.github.io/2018/03/12/this/

## PROCESS
- `:root`를 사용해서 style file 내에서 전역 변수를 이용할 수 있다.
  - `:root` 의사 클래스는 문서 트리의 루트 요소를 선택한다. html 선택자와 같다.
- `querySelectorAll()`는 지정된 셀렉터 그룹에 일치하는 다큐먼트의 엘리먼트 리스트를 나타내는 정적 NodeList를 반환한다.
  - 다큐먼트에서 모든 `<p>` 엘리먼트의 `NodeList`를 얻으려면
  ```javascript
  var matches = document.querySelectorAll("p");
  ```
  - 밑 예시에서 다큐먼트 내의 클래스가 "`note`" 또는 "`alert`"인 모든 `<div>` 엘리먼트의 목록을 반환한다.
  ```javascript
  var matches = document.querySelectorAll("div.note, div.alert");
  ```
  ```javascript
  // ID가 test인 컨테이너 안에 위치하고
  var container = document.querySelector("#test");
  // 부모 엘리먼트가 div 엘리먼트이며 클래스가 "highlighted"인 p 엘리먼트의 리스트를 얻는다.
  var matches = container.querySelectorAll("div.highlighted > p");
  ```
  ```javascript
  // "data-src" 속성을 포함하는 iframe 엘리먼트의 리스트를 반환한다.
  var matches = document.querySelectorAll("iframe[data-src]");
  ```
  ```javascript
  // id가 userlist인 리스트 내에서
  var container = document.querySelector("#userlist");
  // data-active 속성 값이 "1"인 리스트 항목의 목록을 반환한다.
  var matches = container.querySelectorAll("li[data-active='1']");
  ```
  ```html
  <div class="outer">
    <div class="select">
      <div class="inner">
      </div>
    </div>
  </div>
  ```
  ```javascript
  var select = document.querySelector('.select');
  var inner = select.querySelectorAll('.outer .inner');
  inner.length; // 1이다. 0이 아니다.
  ```
  - 클래스 `"select"`를 갖는 `<div>` 컨텍스트에서 `".outer .inner"`를 셀렉틱할 때, `.outer`가 탐색을 수행하는 기본 엘리먼트(`".select"`)의 자손이 아님에도 클래스 `".inner"`가 탐색된다.
  - 기본적으로 `querySelectorAll()`은 탐색 범위 내에서 셀렉터의 마지막 엘리먼트만을 검증한다.
  ```javascript
  var select = document.querySelector('.select');
  var inner = select.querySelectorAll(':scope .outer .inner');
  inner.length; // 0
  ```