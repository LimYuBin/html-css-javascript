# 기본구조

_자동완성 : ! + Tab키_

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Document</title>
  </head>
  <body></body>
</html>
```

- html 버전 선언
  - 해당 문서가 html5 버전으로 작성되었음을 선언
- html tag

  - html 파일의 가장 상위에 있는 tag
  - head와 body로 이루어져 있음

- head tag

  - 사용자에게 보여지는 정보가 아닌 metadata들로 이루어져 있음

- body tag

  - 사용자에게 보여지는 정보들로 이루어져 있음
  - body 구조

    ![bodystructure](https://img1.daumcdn.net/thumb/R720x0.q80/?scode=mtistory2&fname=http%3A%2F%2Fcfile24.uf.tistory.com%2Fimage%2F9966A3405C9743C41EF56E)

# Element 구조

- 각 Element는 &#60;opening tag> + content + &#60;/closing tag>로 이루어져 있음

```html
<p>My cat is very grumpy</p>
```

- tag 안에 attribute 지정 가능

```html
<p class="editor-node">My cat is grumpy</p>
```

# Default Display 속성

- block 레벨 tag : 줄 단위
- inline 레벨 tag : 공간이 허용되면 다른 tag 옆에 배치

# &#60;link />

- 외부 리소스의 연결 및 현재 문서와의 관계를 명시
- head의 후손 요소

| 속성       |                  의미                   |                          값 |
| ---------- | :-------------------------------------: | --------------------------: |
| `rel`      | 현재 문서와 외부 리소스와의 관계 (필수) |       `stylesheet, icon` 등 |
| `href`     |            외부 리소스의 URL            |                         URL |
| `type`     |         외부 리소스의 MIME 타입         | `text/css, image/x-icon` 등 |
| `hreflang` |         현재 페이지의 대체 언어         |                 `ko, en` 등 |

# &#60;a>

- 하이퍼링크 설정
- body의 후손 요소
- inline 레벨

| 속성       |                         의미                         |                       값 |
| ---------- | :--------------------------------------------------: | -----------------------: |
| `href`     |                       링크 URL                       |                      URL |
| `target`   |                 링크 URL의 표시 위치                 |       `_self, _blank` 등 |
| `rel`      |             현재 문서와 링크 URL의 관계              | `license, prev, next` 등 |
| `download` | 이 요소가 리소스를 다운로드하는 용도로 사용됨을 의미 |                  Boolean |
| `type`     |                 링크 URL의 MIME 타입                 |           `text/html` 등 |
| `hreflang` |               현재 페이지의 대체 언어                |              `ko, en` 등 |

# &#60;span>

- 특별한 기능을 갖고 있지는 않음, 줄바꿈이 되지 않음
- CSS와 함께 쓰임
- inline 레벨

```html
<html>
  <body>
    <span style="background-color:red">span1</span>
    <span style="background-color:blue">span2</span>
    <span style="background-color:green">span3</span>
  </body>
</html>
```

# &#60;div>

- 특별한 기능을 갖고 있지는 않고, 줄바꿈
- CSS와 함께 쓰임
- block 레벨

```html
<html>
  <body>
    <div style="background-color:cyan">구역1</div>
    <div style="width:100px; height:100px; background-color:#CF0">구역2</div>
  </body>
</html>
```

# &#60;p>

- 하나의 문단을 만들 때 쓰임
- block 레벨

# &#60;li> &#60;ul> &#60;ol>

- &#60;li> : list, 목록을 만듦
- &#60;ul> : unordered list, 순서없이 모양으로 목록을 만듦
- &#60;ol> : ordered list, 번호를 매겨 순서가 있는 목록을 만듦
- block 레벨

# &#60;header>

- 문서의 헤더를 설정
- 보통 로고, 제목, 검색 등 포함
- block 레벨

# &#60;footer>

- 문서의 푸터를 설정
- 보통 작성자, 저작권, 관련 문서 등 포함
- block 레벨

# &#60;nav>

- 다른 페이지 링크를 제공하는 영역을 설정
- Navigation, 보통 메뉴(Home, About, Contact), 목차, 색인 등 설정
- block 레벨

# &#60;section>

- 문서의 일반적인 영역을 설정
- 보통 &#60;h1>~&#60;h6>를 포함하여 식별
- block 레벨

# &#60;article>

- 독립적으로 구분되거나 재사용 가능한 영역을 설정
- 매거진/신문 기사, 블로그 등
- 보통 &#60;h1>~&#60;h6>를 포함하여 식별
- 작성일자와 시간을 &#60;time>의 datetime 속성으로 작성
- block 레벨

```html
<article>
  <header>
    <p>
      작성자:<a href="">나그네</a> at
      <time datetime="2013-01-22T08:45">2013년1월22일 08:45</time>
    </p>
  </header>
  <p>코멘트 내용</p>
</article>
```

# &#60;aside>

- 문서의 별도 콘텐츠를 설정
- 보통 광고나 기타 링크 등의 Side bar를 설정
- block 레벨

# 폼 (Form)

- 웹 폼: 웹 페이지에서 사용자 입력을 받는 폼
- &#60;form>
  - 폼 생성
    | 속성 | 의미 | 값 |
    | ---------- | :--------------------------------------------------: | -----------------------: |
    | `action` | 폼 데이터를 처리할 웹 서버 응용프로그램 URL | URL |
    | `target` | 웹 서버 응용 프로그램으로부터 전송받은 데이터 | 윈도우 이름 |
    | `name` | 폼 이름 | 텍스트|
    | `method` | 폼 데이터를 웹 서버로 전송하는 방식 | `Get, POST` |
- 폼 요소
- &#60;input type="text | password">
  - 한줄 텍스트 입력 창
    | 속성 | 의미 | 값 |
    | ---------- | :--------------------------------------------------: | -----------------------: |
    | `name` | 요소 이름 | 텍스트|
    | `maxlength` | 입력할 수 있는 문자의 최대 개수 | 숫자|
    | `size` | 입력창의 크기(문자 개수) | 숫자|
    | `value` | 초기 텍스트 | 텍스트|
- &#60;input type="checkbox | radio">
  - 선택형 요소: 체크박스, 라디오버튼
  - value는 이 항목이 선택되었을 때 웹 서버에 전송되는 값
  - 속성에 selected 쓰면 초기 선택
  - 라디오버튼은 name 속성 같은 것끼리 그룹 형성, 같은 name을 가진 라디오버튼 중 하나만 선택 가능
- &#60;input type="color">
  - 색 입력하는 컬러 다이얼로그
  - 속성에 onchange= "document.body.style.color=this.value" 하면 사용자가 색 선택 가능
- &#60;input type="month | week | date | time | datetime-local">
  - 시간정보 입력 창
  - value 속성에 초깃값 입력
  - 드롭다운 버튼이나 스핀 버튼으로 변경 가능
- &#60;input type="number">
  - 스핀버튼으로 정교한 값 입력
  ```html
  <input type="number" min="0.0" max="10.0" step="0.5" />
  ```
- &#60;input type="range">
  - 슬라이드 바로 대략적인 값 입력
  ```html
  <input type="range" min="0" max="100" />
  ```
- &#60;input type="email | url | tel | search">
  - 이메일, URL, 전화번호, 검색키워드 등 형식 검사 기능을 가진 텍스트 입력 창
  - placeholder 속성으로 힌트 추가
  ```html
  <input type="email" placeholder="“id@host" />
  <input type=“url” placeholder=“http://”>
  <input type="“tel”" placeholder="“010-1234-5678”" />
  <input type="“search”" placeholder="검색어" />
  ```
- &#60;input type="button | reset | submit">
  - 단순버튼, reset 버튼, submit 버튼
  ```html
  <input type="button" />
  <input type="reset" value="취소" />
  <input type="submit" value="전송" />
  ```
- &#60;textarea>
  - 태그 사이에 초기 출력될 텍스트 입력
    | 속성 | 의미 | 값 |
    | ---------- | :--------------------------------------------------: | -----------------------: |
    | `cols` | 열 개수 | 숫자|
    | `rows` | 행 개수 | 숫자|
    | `name` | 요소 이름 | 텍스트|
    | `wrap` | 줄바꿈 | `OFF, HARD, SOFT` |
- &#60;datalist>

  - 목록 리스트를 작성하는 태그
  - &#60;option> 태그로 항목 하나 표현
  - &#60;input> 태그의 list와 &#60;datalist> 태그의 id 일치시켜서 연결

  ```html
  나라 : <input type="text" list="countries" />
  <datalist id="countries">
    <option value="가나"></option>
    <option value="스위스"></option>
    <option value="브라질"></option>
  </datalist>
  ```

- &#60;select>

  - 드롭다운 리스트에 목록 출력, 목록을 선택하는 입력 방식
  - &#60;option> 태그로 항목 하나 표현
  - &#60;option> 태그의 속성에 selected 쓰면 초기 선택

  ```html
  <select name="china">
    <option value="1">짜장면</option>
    <!--value는 이 항목이 선택되었을 때 웹 서버에 전송되는 값 -->
    <option value="2" selected>짬뽕</option>
    <option value="3">탕수육</option>
  </select>
  ```

- &#60;label>

  - 캡션과 폼 요소를 한 단위로 묶음
  - 캡션과 폼 요소를 모두 &#60;label> 태그 안에 넣을 수 도 있고,

  ```html
  <label>사용자 ID : <input type="text" /> </label>
  ```

  - 캡션만 &#60;label> 태그 안에 넣은 후 &#60;label>의 for와 폼요소의 id 연결할 수도 있음

  ```html
  <label for="loginID"> 사용자 ID : </label> <input type="text" id="loginID" />
  ```

  - "checkbox"나 "radio" 같은 선택형 요소에 &#60;label> 태그 사용하면 캡션 텍스트나 이미지를 선택해도 폼 요소를 선택한 것으로 처리

- 폼 요소 그룹핑
  - &#60;fieldset> 안에 &#60;legend>로 제목입력해서 폼 요소 그룹핑
  ```html
  <fieldset>
    <legend>회원정보</legend>
    이메일 : <input type="email" /><br />
    홈페이지 : <input type="url" /><br />
    전화번호 : <input type="tel" />
  </fieldset>
  ```

# 그 외 태그들

- &#60;title>
- &#60;h1>~&#60;h6>
- &#60;p>: 단락
- &#60;hr>: 수평선
- &#60;br>: 줄 바꾸기
- &#60;pre>: 사용자가 입력한 그대로 출력
- &#60;b>: 진하게
- &#60;strong>: 중요한
- &#60;em>: 강조
- &#60;i>: 이탤릭으로 강조
- &#60;small>: 한단계 작은 문자
- &#60;del>: 가운데줄
- &#60;ins>: 밑줄
- &#60;sup>: 윗첨자
- &#60;sub>: 아래첨자
- &#60;mark>: 하이라이팅
- &#60;q>: 따옴표

---

- &#60;audio>: 오디오 삽입
  - 속성: controls(콘트롤 생성) autoplay(자동 재생)
- &#60;video>: 비디오 삽입
  - 속성: controls(콘트롤 생성) autoplay(자동 재생) loop(반복 재생)
- &#60;iframe>: html 페이지 내에 html 페이지 삽입
  - &#60;a>에서 target 속성에 &#60;iframe>의 name 적어주면 &#60;iframe>의 그 위치에서 열림

```html
<ul>
  <li><a href="section1.html" target="right">HTML 태그</a></li>
  <li><a href="section2.html" target="right">추천 영화</a></li>
  <li><a href="section3.html" target="right">추천 여행지</a></li>
  <li>
    <a href="https://www.naver.com/" target="_blank">네이버</a>
  </li>
</ul>
<iframe
  src="nav.html"
  name="left"
  frameborder="1"
  width="300px"
  height="700px"
></iframe>
<iframe name="right" frameborder="1" width="700px" height="700px"></iframe>
```

- &#60;figure> & &#60;figcaption>
  - &#60;figure>: 사진, 도표, 삽화, 오디오, 비디오, 코드 등을 담는 컨테이너 역할을 하는 태그
  - &#60;figcaption>: &#60;figure>를 설명하는 태그

```html
<figure>
  <img src="img/SteveJobs.jpg" alt="스티브 잡스 이미지" width="300px" />
  <figcaption>스티븐 폴 잡스 (Steven Paul Jobs)</figcaption>
</figure>
```

- &#60;details> & &#60;summary>
  - &#60;details>: 상세 정보를 담는 시맨틱 블록 태그
  - &#60;summary>: &#60;details>로 구성되는 블록의 제목 표현

```html
<article id="say">
  <h2>어록</h2>
  <details>
    <summary>어록1</summary>
    <p>Stay hungry, Stay foolish</p>
  </details>
  <details>
    <summary>어록2</summary>
    <p>"One more thing..."</p>
  </details>
</article>
```

- &#60;table> : 표 전체
  - &#60;caption> : 표 제목
  - &#60;thead> : 헤딩 셀 그룹
  - &#60;tfoot> : 바닥 셀 그룹
  - &#60;tbody> : 데이터 셀 그룹
  - &#60;tr> : 행. 여러 <td>, <th>포함
  - &#60;th> : 열 제목(헤딩) 셀
  - &#60;td> : 데이터 셀

```html
<h2>HTML 태그</h2>
<table border>
  <thead>
    <th>태그명</th>
    <th>태그설명</th>
  </thead>

  <tbody>
    <tr>
      <th>&lt;html&gt; ~ &lt;/html&gt;</th>
      <td>문서의 시작과 끝을 나타내는 태그</td>
    </tr>
    <tr>
      <th>&lt;head&gt; ~ &lt;/head&gt;</th>
      <td>웹 페이지에 나타나지 않는 웹 문서에 대한 설명</td>
    </tr>
    <tr>
      <th>&lt;body&gt; ~ &lt;/body&gt;</th>
      <td>웹 페이지에 나타날 문서의 내용</td>
    </tr>
    <tr>
      <th>&lt;br&gt;</th>
      <td>줄 바꿈 태그</td>
    </tr>
  </tbody>
</table>
```

# 참고자료

https://heropy.blog/2019/05/26/html-elements/  
https://ofcourse.kr/html-course/  
https://webdir.tistory.com/310  
https://img1.daumcdn.net/thumb/R720x0.q80/?scode=mtistory2&fname=http%3A%2F%2Fcfile24.uf.tistory.com%2Fimage%2F9966A3405C9743C41EF56E
