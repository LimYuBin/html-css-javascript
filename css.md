# CSS

- Cascading Style Sheet
- 웹 문서의 전반적인 스타일을 미리 저장해 둔 스타일시트

# 작성방법

1. &#60;style> 태그 이용

   - HTML 문서 안의 &#60;head> 태그 안에 &#60;style> 태그에 CSS 작성
   - 보통 CSS 문서 따로 작성해서 &#60;link> 태그로 연결

   ```html
   <!--<style> 태그에 CSS 작성-->
   <head>
     <style>
       <!--여기에 CSS 작성-->
     </style>
   </head>

   <!--<link> 태그로 연결-->
   <link href="" type="text/css" rel="stylesheet" />
   ```

2. 태그 안의 속성 이용

   - 여러 style을 적용하고 싶을 때에는 세미콜론(;) 사용

   ```html
   <a href="" style="color:red;text-decoration:underline"></a>
   ```

3. 우선순위 (높은순서)

- style 속성에 선언된 스타일 (inline)
- &#60;style>&#60;/style> 태그에 선언된 스타일 (internal)
- .css 파일에 선언된 스타일 (external)
- 브라우저의 디폴트 스타일

# 기본문법

![cssStructure](https://media.vlpt.us/images/minho/post/2bdea730-b7bb-43e3-94a6-e917b85feb7c/css-declaration.png)

# Selectors

- `*` : 모든 태그
- `Tag` : 특정 태그만

  - `:state` : Tag 옆에 state 지정 가능
    | state | 설명 |
    | ---------- | :--------------------------------------------------: |
    | `:hover` | 마우스가 올라갈 때 스타일 적용 |
    | `:active` | 마우스로 누르고 있는 상황에서 스타일 적용 |
    | `:focus` | 폼 요소가 키보드나 마우스 클릭으로 포커스를 받을 때 스타일 적용 |
    | `:link` | 방문하지 않은 링크에 스타일 적용 |
    | `:visited` | 방문한 링크에 스타일 적용 |
    | `:first-letter` | 블록형 태그의 첫 글자에 스타일 적용 |
    | `:first-line` | 블록형 태그의 첫 라인에 스타일 적용 |
    | `:nth-child(even)` | 짝수 번째 모든 자식 태그에 스타일 적용 |
    | `:nth-child(1)` | 첫 번째 자식 태그에 스타일 적용 |

    ```css
    button:hover {
      color: red;
    }
    ```

  - `[ ]` : Tag 옆에 attribute 지정 가능
    ```css
    a[href^="naver"] {
      color: red;
    }
    ```

- `#id` : 특정 id만, 유일하게 적용할 때 사용
  - tag명#id명 하면 그 tag의 id만 적용
- `.class` : 특정 class만, 여러 태그를 하나의 그룹으로 묶어 적용할 때 사용
  - tag명.class명 하면 그 tag의 class만 적용
- 자식 셀렉터 : >, 직계인 경우 사용
- 자손 셀렉터 : 나열

# 색 관련 Property

- `color`: 색; (텍스트 글자색)
- `background-color`: 색; (배경 색)
  - background-image: url("주소")
  - background-repeat: repeat-y repeat-x no-repeat repeat(디폴트)
- `border-color`: 색; (테두리 색)

# 텍스트 꾸미기 Property

- `text-indent`: &#60;length> | &#60;percentage>; (들여쓰기)
- `text-align`: left | right | center | justify; (정렬)
- `text-decoration`: none | underline | overline | line-through; (텍스트 꾸미기)
- `text-shadow`: h-shadow v-shadow blur-radius color; (텍스트 그림자)
  - h-shadow : 원본 텍스트와 그림자 텍스트 사이의 수평 거리 - 필수
  - v-shadow : 원본 텍스트와 그림자 텍스트 사이의 수직 거리 - 필수
  - blur-radius: 그림자 blur 길이
  - color: 그림자 색

# 폰트 Property

- `font` : font-style font-weight font-size font-family;
  - font-size, font-family 외 생략 가능
- `font-size`:40px; (폰트 크기)
- `font-family`: Arial, "Times New Roman", Serif; (폰트 종류 선언)
  - 콤마로 나열, Arial 폰트가 없는 경우 "Times New Roman", "Times New Roman"이 없는 경우 Serif
- `font-style`: italic; (폰트 스타일)
- `font-weight`: 300; (폰트 굵기)

# 표 꾸미기 Property

- `border`: 1px solid blue; (표 테두리)
- `border-collapse`: collapse; (중복된 테두리 합치기)

# 박스(Box) 꾸미기 Property

![cssBoxModel](https://encrypted-tbn0.gstatic.com/images?q=tbn%3AANd9GcRxpGWzSMVQVOtXRlJ0JHPv0wpcyHBdFOS-ZQ&usqp=CAU)

- box 모델에서 Property value를 지정할 때, top right bottom left 순서로 지정, 또는 top/bottom left/right 순서로 지정00
- `border` : 1px solid black; (테두리)
  - 테두리 스타일 : solid(실선) dotted(점선) dashed(파선) double(이중선) none hidden(두께0)
- `border-radius` : 모서리 둥근 정도;
- `box-shadow`: h-shadow v-shadow blur-radius spread-radius color; (박스 그림자)
  - h-shadow : 원본 텍스트와 그림자 텍스트 사이의 수평 거리 - 필수
  - v-shadow : 원본 텍스트와 그림자 텍스트 사이의 수직 거리 - 필수
  - blur-radius: 그림자 blur 길이
  - spread-radius: 그림자 크기
  - color: 그림자 색

# 박스(Box) 배치 Property

- `display`: block | inline | inline-block;
  - display: block; 이나 display: inline-block은 width와 height 지정 가능, padding/border/margin 조정 가능
- `position` : static(디폴트) | relative | absolute | fixed | sticky;
  - position: static;
    - 기본값
  - position: relative;
    - 상대 위치 지정 요소
    - 내 아이템의 원래 위치에서의 거리를 지정
  - position: absolute;
    - 절대 위치 지정 요소
    - 위치의 기준점이 되는 조상 요소의 모서리로부터의 거리를 지정
    - 즉, 내 아이템과 가장 가까이에 있는 박스 안에서의 위치 변경
  - position: fixed;
    - 윈도우(웹 페이지) 안에서의 위치 변경
  - position: sticky;
    - 평소에는 상대 위치 지정 요소로 처리하지만, 컨테이닝 블록이 자신의 플로우 루트(스크롤 컨테이너)에서 지정한 임계값을 넘으면 화면에 고정
    - 즉, 스크롤링을 했을 때 원래의 위치에 고정
    - 고정 상태는 컨테이닝 블록의 반대편 모서리를 만나면 해제됨
- `float`: left | right;
  - 브라우저의 왼쪽이나 오른쪽에 고정
  - 고정된 방향에서 반대 방향으로 float, 위에서 아래로 float
  - clear: left | right | both;
    - float로 인해 다른 요소가 가려서 보이지 않을 때, 가리지 않기 위해 사용
- `z-index`: 숫자;
  - 겹쳐서 박스를 배치할 때 박스의 순서를 정하기 위해 사용
  - position: absolute; 또는 positon: relative; 로 설정해 놓아야 함
  - z-index 값이 가장 큰 것이 맨 위로 올라옴
- `visibility`: visible(디폴트) | hidden;
  - 공간은 차지하지만 텍스트는 보이지 않음
- `overflow`: visible | hidden | scroll;
  - overflow: visible;
    - content가 박스를 넘어가서도 출력
  - overflow: hidden;
    - 박스를 넘어가는 내용이 잘려 보이지 않음
  - overflow: scroll;
    - 박스에 스크롤바를 붙여 출력

# Position

- 문서 상에 요소를 배치하는 방법을 지정
- top, right, bottom, left 속성이 요소를 배치할 최종 위치를 결정

* `position: static;`
  - 기본값
* `position: relative;`
  - 상대 위치 지정 요소
  - 내 아이템의 원래 위치에서의 거리를 지정
* `position: absolute;`
  - 절대 위치 지정 요소
  - 위치의 기준점이 되는 조상 요소의 모서리로부터의 거리를 지정
  - 즉, 내 아이템과 가장 가까이에 있는 박스 안에서의 위치 변경
* `position: fixed;`
  - 윈도우(웹 페이지) 안에서의 위치 변경
* `position: sticky;`
  - 평소에는 상대 위치 지정 요소로 처리하지만, 컨테이닝 블록이 자신의 플로우 루트(스크롤 컨테이너)에서 지정한 임계값을 넘으면 화면에 고정
  - 즉, 스크롤링을 했을 때 원래의 위치에 고정
  - 고정 상태는 컨테이닝 블록의 반대편 모서리를 만나면 해제됨

# Flex (Box)

- Flex는 한 방향 레이아웃 시스템 (1차원)
- Flexbox에는 2개의 축이 있음, Item을 진열해놓은 방향에 따라 달라짐
  - main axis (주 축)
  - cross axis (교차 축)

![Flexbox](https://media.vlpt.us/images/choonghee-lee/post/3271a7f8-c123-4708-a649-e1d4b65250c9/flex1.png)

- Container에 꾸며줄 수 있는 속성

  - `display`
    - `먼저 이걸로 Flexbox로 바꿔줌`
    - flex : Block 특성의 Flex Container를 정의
    - inline-flex : Inline 특성의 Flex Container를 정의
  - `flex-direction`
    - `Flex Items의 주 축(main-axis)을 설정`
    - row : Itmes를 수평축(왼쪽에서 오른쪽으로)으로 표시
    - row-reverse : Items를 row의 반대 축으로 표시
    - column : Items를 수직축(위에서 아래로)으로 표시
    - column-reverse : Items를 column의 반대 축으로 표시
  - `flex-wrap`
    - `Flex Items의 여러 줄 묶음(줄 바꿈) 설정`
    - nowrap : 모든 Itmes를 여러 줄로 묶지 않음(한 줄에 표시)
    - wrap : Items를 여러 줄로 묶음
    - wrap-reverse : Items를 wrap의 역 방향으로 여러 줄로 묶음
  - `flex-flow`: flex-direction flex-wrap;
    - `flex-direction와 flex-wrap의 단축 속성`
    ```css
    .container {
      flex-wrap: column nowrap;
    }
    ```
  - `justify-content`
    - `주 축(main-axis)의 정렬 방법을 설정`
    - flex-start : Items를 시작점(flex-start)으로 정렬
    - flex-end : Items를 끝점(flex-end)으로 정렬
    - center : Items를 가운데 정렬
    - space-around : Items를 둘러싸게 spacing을 넣어 정렬
    - space-evenly : Items를 균등한 간격으로 정렬 (시작점과 끝점에도 spacing 있음)
    - space-between : 시작 Item은 시작점에, 마지막 Item은 끝점에 정렬되고 나머지 Items는 사이에 고르게 정렬됨
  - `align-items`
    - `교차 축(cross-axis)에서 Items의 정렬 방법을 설정(1줄)`
    - stretch : Container의 교차 축을 채우기 위해 Items를 늘림
    - flex-start : Items를 각 줄의 시작점(flex-start)으로 정렬
    - flex-end : Items를 각 줄의 끝점(flex-end)으로 정렬
    - center : Items를 가운데 정렬
    - baseline : Items를 문자 기준선에 정렬 (텍스트가 동일 라인에 오도록 정렬)
  - `align-content`
    - `교차 축(cross-axis)의 정렬 방법을 설정(2줄 이상)`
    - stretch : Container의 교차 축을 채우기 위해 Items를 늘림
    - flex-start : Items를 시작점(flex-start)으로 정렬
    - flex-end : Items를 끝점(flex-end)으로 정렬
    - center : Items를 가운데 정렬
    - space-around : Items를 둘러싸게 spacing을 넣어 정렬
    - space-evenly : Items를 균등한 간격으로 정렬 (시작점과 끝점에도 spacing 있음)
    - space-between : 시작 Item은 시작점에, 마지막 Item은 끝점에 정렬되고 나머지 Items는 사이에 고르게 정렬됨

- Item에 꾸며줄 수 있는 속성
  - `order`: 숫자(순서);
    - `Flex Item의 순서를 설정, 숫자가 클수록 후 순위`
  - `flex-grow`: 숫자(비율);
    - `Flex Item의 증가 너비 비율을 설정, Container의 사이즈에 맞게 늘어남`
  - `flex-shrink`: 숫자(비율);
    - `Flex Item의 감소 너비 비율을 설정, Container의 사이즈에 맞게 줄어듦`
  - `flex-basis`: auto, 단위(px, em, cm, % 등);
    - `Flex Item의 (공간 배분 전) 기본 너비 설정`
  - `flex`: flex-grow flex-shrink flex-basis;
    - `flex-grow, flex-shrink, flex-basis의 단축 속성`
    ```css
    .item {
      flex: 1 1 20px;
    }
    ```
  - `align-self`
    - `교차 축(cross-axis)에서 개별 Item의 정렬 방법을 설정`
    - auto : Container의 align-items 속성을 상속받음
    - stretch : Container의 교차 축을 채우기 위해 Item을 늘림
    - flex-start : Item을 각 줄의 시작점(flex-start)으로 정렬
    - flex-end : Item을 각 줄의 끝점(flex-end)으로 정렬
    - center : Item을 가운데 정렬
    - baseline : Item을 문자 기준선에 정렬

# Grid (Box)

- Grid는 두 방향(가로, 세로) 레이아웃 시스템 (2차원)

- Container에 꾸며줄 수 있는 속성

  - `display` : 그리드 컨테이너를 정의
    - grid, inline-grid
  - `grid-template-rows` : 자식들의 row의 수와 각각의 크기를 지정
    - fr, repeat(반복횟수, 배열)
    ```css
    .container {
      grid-template-rows: repeat(2, 100px); /* 100px 100px */
      grid-template-columns: repeat(3, 1fr 2fr); /* 1fr 2fr 1fr 2fr 1fr 2fr */
    }
    ```
  - `grid-template-columns` : 자식들의 column 의 갯수와 각각의 크기를 지정
    - fr, repeat(반복횟수, 배열)
  - `gap` : 자식들의 간격을 지정

    ```css
    .container {
      gap: 20px 10px; /* row간격 column간격 */
    }
    ```

  - `row-gap` : 행과 행 사이의 간격을 지정
  - `column-gap`: 열과 열 사이의 간격을 지정
  - `grid-auto-rows` : grid-template-rows 에서 크기를 지정하지 않은 자식 item들에 대해서 자동으로 크기를 부여
  - `grid-auto-columns` : grid-template-columns 에서 크기를 지정하지 않은 자식 item들에 대해서 자동으로 크기를 부여
  - `grid-auto-flow` : grid-template-columns와 grid-template-rows 에서 설정한 개수 외에 자식 엘리먼트들이 추가적으로 초과될경우 row에 붙을지 column에 붙을지 설정
    - row : 각 행 축을 따라 차례로 배치
    - column : 각 열 축을 따라 차례로 배치
    - row dense : 각 행 축을 따라 차례로 배치, 빈 영역 메움
    - column dense : 각 열 축을 따라 차례로 배치, 빈 영역 메움
  - `align-content` : 그리드 콘텐츠를 수직 정렬
    - normal, start, center, end, space-around, space-between, space-evenly
  - `justify-content` : 그리드 콘텐츠를 수평 정렬
    - normal, start, center, end, space-around, space-between, space-evenly
  - `align-items` : 그리드 아이템들을 수직 정렬
    - normal, start, center, end
  - `justify-items` : 그리드 아이템들을 수평 정렬
    - normal, start, center, end

- Item에 꾸며줄 수 있는 속성

  - `grid-row-start, grid-row-end, grid-column-start, grid-column-end` : 그리드 선의 시작 위치와 끝 위치 지정

    - 숫자, span

    ```css
    .item:nth-child(1) {
      /* Row 1번에서 3번(1+2=3)까지 */
      grid-row-start: 1;
      grid-row-end: span 2;

      /* Column 2번에서 3번(2+1=3)까지 *_*/
      grid-column-start: 2;
      /* grid-column-end: span 1; (생략) */
    }
    ```

  - `grid-row` : &#60;grid-row-start> / &#60;grid-row-end>의 단축속성
  - `grid-column` : &#60;grid-column-start> / &#60;grid-column-end>의 단축속성
  - `grid-area` : &#60;grid-row-start> / &#60;grid-column-start> / &#60;grid-row-end> / &#60;grid-column-end>의 단축 속성

    ```css
    .item {
      grid-area: 2 / span 2 / 3 / -1;
    }
    ```

  - `justify-self` : 그리드 아이템을 수평 정렬
    - normal, start, center, end
  - `align-self` : 그리드 아이템을 수직 정렬
    - normal, start, center, end

# 미디어 쿼리

- 반응형 디자인을 CSS를 통해 구현
- CSS 내부에 삽입하거나 &#60;link> 태그로 연결

```html
<!--CSS 내부에 삽입-->
<style>
  @media (min-width: 800px) {
    div {
      display: none;
    }
  }
</style>

<!--<link> 태그로 연결-->
<link rel="stylesheet" media="(max-width:800px)" href="" />
```

# CSS3의 표준 단위

| 단위  |                 의미                  |
| ----- | :-----------------------------------: |
| `em`  |         배수 (상위 요소 기준)         |
| `em`  | 배수 (문서의 최상위 요소인 html 기준) |
| `%`   |                퍼센트                 |
| `px`  |                픽셀 수                |
| `cm`  |               센티미터                |
| `mm`  |               밀리미터                |
| `in`  |       인치, 1in = 2.54cm = 96px       |
| `pt`  |     포인터, 1pt = 1in의 1/72 크기     |
| `pc`  |       피카소(picas), 1pc = 12pt       |
| `deg` |                 각도                  |

# 참고자료

https://terms.naver.com/entry.nhn?docId=1179641&cid=40942&categoryId=32854
https://media.vlpt.us/images/minho/post/2bdea730-b7bb-43e3-94a6-e917b85feb7c/css-declaration.png  
https://encrypted-tbn0.gstatic.com/images?q=tbn%3AANd9GcRxpGWzSMVQVOtXRlJ0JHPv0wpcyHBdFOS-ZQ&usqp=CAU  
https://developer.mozilla.org/ko/docs/Web/CSS/position  
https://heropy.blog/2018/11/24/css-flexible-box/  
https://media.vlpt.us/images/choonghee-lee/post/3271a7f8-c123-4708-a649-e1d4b65250c9/flex1.png  
https://dydals5678.tistory.com/69  
https://heropy.blog/2019/08/17/css-grid/
