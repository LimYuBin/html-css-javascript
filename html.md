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
  - 예 : &#60;div>, &#60;p>, &#60;li>, &#60;ul>, &#60;ol>, &#60;header>, &#60;footer>, &#60;nav>, &#60;selection>, &#60;article>, &#60;aside>, &#60;video>, &#60;audio>, &#60;map>, &#60;canvas>, &#60;table>, &#60;form> 등
- inline 레벨 tag : 공간이 허용되면 다른 tag 옆에 배치
  - 예 : &#60;a>, &#60;span>, &#60;button>, &#60;input>, &#60;label>, &#60;img>, &#60;map> 등

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

- 문서의 푸터를 설정.
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

- 독립적으로 구분되거나 재사용 가능한 영역을 설정.
- 매거진/신문 기사, 블로그 등
- 보통 &#60;h1>~&#60;h6>를 포함하여 식별
- 작성일자와 시간을 &#60;time>의 datetime 속성으로 작성
- block 레벨

```html
<article>
  <header>
    작성자:<a href="">나그네</a> at
    <time datetime="2013-01-22T08:45">2013년1월22일 08:45</time>
  </header>
  <p>코멘트 내용</p>
</article>
```

# &#60;aside>

- 문서의 별도 콘텐츠를 설정
- 보통 광고나 기타 링크 등의 Side bar를 설정
- block 레벨

# 참고자료

https://heropy.blog/2019/05/26/html-elements/  
https://ofcourse.kr/html-course/  
https://webdir.tistory.com/310  
https://img1.daumcdn.net/thumb/R720x0.q80/?scode=mtistory2&fname=http%3A%2F%2Fcfile24.uf.tistory.com%2Fimage%2F9966A3405C9743C41EF56E
