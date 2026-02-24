# HTML

과목: Web
학습일자: 2026년 2월 24일

# HTML

## WWW (World Wide Web)

- 인터넷으로 연결된 컴퓨터들이 정보를 공유하는 거대한 정보 공간

---

## Web

- Web site, Web application 등을 통해 사용자들이 정보를 검색하고 상호 작용하는 기술

---

## Web site

- 인터넷에서 여러 개의 Web page가 모인 것으로, 사용자들이 정보나 서비스를 제공하는 공간

---

## Web page

- HTML, CSS 등의 웹 기술을 이용하여 만들어진, ‘Web site’를 구성하는 하나의 요소
- 구성요소
    - HTML ‘Structure’
    - CSS ‘Styling’
    - Javascript ‘Behavior’

---

## HTML (HyperText Markup Language)

- 웹 페이지의 의미와 구조를 정의하는 언어

---

### HyperText

- 웹 페이지를 다른 페이지로 연결하는 링크
- 참조를 통해 사용자가 한 문서에서 다른 문서로 즉시 접근할 수 있는 텍스트
- 비선형성 / 상호연결성 / 사용자 주도적 탐색

---

### Markup Language

- 태그 등을 이용하여 문서나 데이터의 구조를 명시하는 언
- 인간이 읽고 쓰기 쉬운 형태이며, 데이터의 구조와 의미를 정의하는 데 집중
- ex) HTML, Markdown

---

## HTML 구조

### <!DOCTYPE html>

- 해당 문서가 html로 문서라는 것을 나타냄

### <html></html>

- 전체 페이지의 콘텐츠를 포함

### <title></title>

- 브라우저 탭 및 즐겨찾기 시 표시되는 제목으로 사용

### <head></head>

- HTML 문서에 관련된 설명, 설정 등 컴퓨터가 식별하는 메타데이터를 작성
    - 메타데이터 : 데이터를 설명하는 데이터
- 사용자에게 보이지 않음

### <body></body>

- HTML 문서의 내용을 나타냄
- 페이지에 표시되는 모든 콘텐츠를 작성
- 한 문서에 하나의 body 요소만 존재

```html
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<title>my page</title>
</head>
<body>
  <p>웹페이지 입니다.</p>
</body>
</html>
```

---

## HTML Element(요소)

- 하나의 요소는 여는 태그와 닫는 태그 그리고 그 안의 내용으로 구성
- 닫는 태그는 태그 이름 앞에 슬래시가 포함됨
    - 닫는 태그가 없는 태그도 존재 → = 내용이 없다

```html
<p>My cat is very grumpy</p>
```

---

## HTML Attributes (속성)

- 사용자가 원하는 기준에 맞도록 요소를 설정하거나 다양한 방식으로 요소의 동작을 조절하기 위한 값
- 목적
    - 나타내고 싶지 않지만 추갖거인 기능, 내용을 담고 싶을 때 사용
    - CSS에서 스타일 적용을 위해 해당 요소를 선택하기 위한 값으로 활용
- 작성 규칙
    1. 속성은 요소 이름과 속성 사이에 공백이 있어야 함
    2. 하나 이상의 속성들이 있는 경우엔 속성 사이에 공백으로 구분
    3. 속성 값은 열고 닫는 따옴표로 감싸야 함

```html
<p class="editor-note">My cat is very grumpy</p>
```

---

## HTML 구조 예시

- 자동완성 : ! + Enter

### <p></p>

- Paragraph(문단)의 약자
- 텍스트 문단을 만드는 태그

### <a></a>

- Anchor(닻)의 약자
- 다른 페이지로 이동시키는 하이퍼링크 태그

### <img></img>

- image(이미지)의 약자
- src에 저장된 그림을 보여주는 태그

### <strong></strong>

- 볼드 처리
- 중요함을 강조

### <b></b>

- 단순히 볼드 처리

### <li></li>

- 순서가 있는 목록 (ordered list)
- 넘버링 처리

### <ul></ul>

- 순서가 없는 목록(unordered list)

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
</head>
<body>
  <p>My page</p>
  <a href="https://www.google.com">Google</a>
  <!-- <img src="이미지 경로" alt="대체 텍스트(이미지 경로에 문제가 발생했을 때 출력되는 텍스트)"> -->
  <!-- <img src="images/sample.png" alt="샘플 이미지" >
  <img src="https://picsum.photos/200/300" alt> -->

  <h1>메인 대제목</h1>
  <h2>중제목</h2>
  <p>안녕  <strong>하세요</strong> <em>송기현</em>입니다.</p>
  <p>반갑습니다. <b>누구누구</b>입니다.</p>
  <ol>
    <li>파이썬</li>
    <li>알고리즘</li>
    <li>웹</li>
  </ol>

  <ul>
    <li>파이썬</li>
    <li>알고리즘</li>
    <li>웹</li>
  </ul>
</body>
</html>
```

---

## HTML Text Structure

- HTML의 주요 목적 중 하나는 테스트 구조와 의미를 제공하는 것
- h1 요소는 단순히 텍스트를 크게 만드는 것이 아닌 현재 문서의 최상위 제목이라는 의미를 부여

```html
<h1>Heading</h1>
```

---

# 웹 스타일링

## CSS

- Cascading Style Sheet
- 웹 페이지의 디자인과 레이아웃을 구성하는 언어
- 적용 방법
    - 인라인(Inline) 스타일
    - 내부(Internal) 스타일 시트
    - 외부(External) 스타일 시트

---

### 1. 인라인(Inline) 스타일

- HTML 요소 안에 style 속성 값으로 작성

```html
<!DOCTYPE html>
<html lang="en">
...
<head>
<body>
  <h1 style="color : blue; background-color: yellow;">Inline Style</h1>
  <h2>Internal Style</h2>
  <h3>External Style</h3>
</body>
</html>
```

---

### 2. 내부(Internal) 스타일 시트

- head 태그 안에 style 태그에 작성

```html
<!DOCTYPE html>
<html lang="en">

<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
 <style>
    h2{
      color:red
    }
  </style>
</head>
```

---

### 3. 외부(External) 스타일 시트

- 별도 CSS 파일 생성 후  HTML link 태그를 사용해 불러오기

```html
<!DOCTYPE html>
<html lang="en">

<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
  <link rel="stylesheet" href="style.css">
</head>

<body>
</body>

</html>

```

```html
/* style.css */

h3 {
  color:brown
}
```

---

## CSS 구문

### 선택자

- ‘누구를’ 꾸밀지 지정하는 부분

### 선언(Declaration)

- ‘어떻게’ 꾸밀지 에 대한 구체적인 한 줄의 명령
- 속성과 값이 한 쌍으로 이루어지며, 세미콜론으로 끝남

### 속성

- 바꾸고 싶은 스타일의 종류를 나타냄

### 값

- 속성에 적용할 구체적인 설정을 나타냄

---

### CSS Selectors

- HTML 요소를 선택하여 스타일을 적용할 수 있도록 하는 선택자

### CSS Selectors 종류

- 기본 선택자
    - 전체 선택자
    - 요소 선택자
    - 클래스 선택자
    - 아이디 선택자
    - 속성 선택자
- 결합자
    - 자손 결합자
    - 자식 결합자

```html
<!DOCTYPE html>
<html lang="en">

<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
  <style>
    /* 전체 선택자 */
    *{
      color:red
    }
    /* 요소 선택자 */
    h2 {
      color:orange
    }
    h3{
      color:blue
    }
    /* class 선택자 */
    .green{
      color:green
    }
    /* id 선택자 */
    #purple{
      color:purple
    }
    /* 자식 결합자 */
    .green > span{
      font-size: 50px;
    }
    /* 자손 결합자 */
    .green li{
      color:brown
    }
    /* 속성 선택자 */
    [class^="y"] {
      color: yellow;
    }
  </style>
</head>

<body>
  <h1 class="green">Heading</h1>
  <h2>선택자</h2>
  <h3>연습</h3>
  <h4>반가워요</h4>
  <p id="purple">과목 목록</p>
  <ul class="green">
    <li>파이썬</li>
    <li>알고리즘</li>
    <li>웹
      <ol>
        <li>HTML</li>
        <li>CSS</li>
        <li>PYTHON</li>
      </ol>
    </li>
  </ul>
  <p class="green">Lorem, <span>ipsum</span> dolor.</p>
  <p class="yellow">TEST</p>
</body>

</html>
```

---

## CSS Selectors: 기본 선택자

### 전체 선택자 (*)

- HTML 모든 요소 선택

### 요소 선택자

- 지정한 모든 태그 선택

### 클래스 선택자 (.)

- 주어진 클래스 속성을 가진 모든 요소 선택

### 아이디 선택자(#)

- 주어진 아이디 속성을 가진 요소 선택
- 문서에는 주어진 아이디를 가진 요소가 하나만 있어야 함

### 속성 선택자 ([ ])

- 주어진 속성이나 속성 값을 가진 모든 요소 선택
- 속성의 존재 여부, 값의 일치/포함 등 다양한 조건으로 요소를 정교하게 선택 가능

## CSS 결합자

### 자손 결합자(’ ‘)

- 첫 번째 요소의 자손요소들 선택

### 자식 결합자(’>’)

- 첫 번째 요소의 직계 자식만 선택

---

## 명시도

- 결과적으로 요소에 적용할 CSS 선언을 결정하기 위한 알고리즘

### Cascade

- 계단식
- 한 요소에 동일한 가중치를 가진 선택자가 적용될 때
- CSS에서 마지막에 나오는 선언이 사용

---

### 명시도가 높은 순서

1. Importance
    - !important
2. Inline 스타일
3. 선택자
    - id 선택자 > class 선택자 > 요소 선택자
4. 소스 코드 선언 순서

```html
<!DOCTYPE html>
<html lang="en">

<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
  <style>
    h2 {
      color: darkviolet !important;
    }

    p {
      color: blue;
    }

    .orange {
      color: orange;
    }

    .green {
      color: green;
    }

    #red {
      color: red;
    }
  </style>
</head>

<body>
  <p>1</p>
  <p class="orange">2</p>
  <p class="green orange">3</p>
  <p class="orange green">4</p>
  <p id="red" class="orange">5</p>
  <h2 id="red" class="orange">6</h2>
  <p id="red" class="orange" style="color: brown;">7</p>
  <h2 id="red" class="orange" style="color: brown;">8</h2>
</body>

</html>
```

---

### !important

- 다른 우선순위 규칙보다 우선하여 적용하는 키워드
- 권장 X

---

# 선언 : 값의 단위

### CSS Declaration

- 선택된 요소에 적용할 스타일을 구체적으로 명시하는 부분

### 속성

- 스타일링하고 싶은 기능이나 특성을 의미
- CSS가 미리 정의해 둔 키워드 사용
- font-size, background-color, width, marign, padding

### 값

- 속성에 적용될 구체적인 설정
- 속성이 받을 수 있는 값의 종류는 정해져 있음
- 16px, lightgray, 100%, 10rem

---

## 값의 단위

### 절대 단위

- 다른 요소의 영향을 받지 않는 고정된 크기
- ex) px, pt, cm 등..

### 상대 단위

- 다른 요소(부모, 화면 표시 영역 등)의 크기에 따라 상대적으로 결정
- ex) %, em, rem, vw, vh 등..

---

### px

- 화면을 구성하는 가장 작은 단위인 ‘픽셀’을 기준으로 하는 절대 단위
- 모니터 해상도에 따라 크기가 결정
- 직관적이고 예측이 쉬움
- 장점
    - 디자인 시안과 거의 동일한 결과물 만들 수 있음
    - 요소의 크기를 명확하게 고정하고 싶을 때 유용
- 단점
    - 사용자가 브라우저의 기본 폰트 크기를 변경해도 요소의 크기가 함께 조절되지 않아 접근성 불리
    - 다양한 디바이스 크기에 연하게 대응하는 반응형 디자인에 한계

---

## em

- 부모 요소의 font-size 를 기준으로 크기가 결정되는 상대 단위
- 만약 부모 요소에 font-size가 없다면, 그 상위 부모의 font-size를 상속 받음
- 장점
    - 부모 요소의 크기에 따라 자식 요소의 크기 유연하게 조절 가능
- 단점
    - 중첩 문제
    - em  단위를 사용하는 요소가 중첩되면 기준 크기가 계속 변경 → 계산이 복잡해지고 예측 어려움
    - rem으로 해결

---

## rem

- em의 단점을 극복하기 위해 등장
    - 상속의 복잡성 해결
    - 유지보수 용이성
    - 접근성 향
- 부모 요소가 아닌, 최상위 요소인 <html>의 font-size르르 기준으로 크기가 결정
- html의 기본 font-size는 대부분 16px

```html
<!DOCTYPE html>
<html lang="en">

<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
  <style>
    /* rem의 기준이 되는 최상위 요소(root)의 글자 크기(브라우저 기본 글자 크기)는 보통 16px입니다. */

    /* em의 기준이 될 부모 요소 */
    .parent-for-em {
      font-size: 20px;
      border: 2px solid blue;
      padding: 10px;
      margin-bottom: 20px;
    }

    /* em 단위 사용 */
    .em-unit {
      /* 부모(.parent-for-em)의 font-size인 20px을 기준으로 1.5배 크기를 가집니다.
      계산: 20px * 1.5 = 30px
    */
      font-size: 1.5em;
    }

    /* rem 단위 사용 */
    .rem-unit {
      /* 최상위 요소(html)의 font-size인 16px을 기준으로 1.5배 크기를 가집니다.
      계산: 16px * 1.5 = 24px
    */
      font-size: 1.5rem;
      border: 2px solid red;
      padding: 10px;
    }
  </style>
</head>

<body>

  <div class="parent-for-em">
    부모 요소 (font-size: 20px)
    <div class="em-unit">
      em 단위 자식 (font-size: 1.5em ==> 30px)
    </div>
  </div>

  <div class="rem-unit">
    rem 단위 요소 (font-size: 1.5rem ==> 24px)
  </div>

</body>

</html>
```

---

## CSS 상속

```html
<!DOCTYPE html>
<html lang="en">

<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
  <style>
    .parent {
      /* 상속 O */
      color: red;

      /* 상속 X */
      border: 1px solid black;
    }
  </style>
</head>

<body>
  <ul class="parent">
    <li class="child">Hello</li>
    <li class="child">Bye</li>
  </ul>
</body>

</html>
```

---

## CSS Box Mode

- 웹 페이지의 모든 HTML 요소를 감싸는 사각형 상자 모델
- 요소의 크기, 배치, 간격을 결정하는 규칙
- 원은 네모 박스를 깎은 것
- 내용(content), 안쪽 여백(padding), 테두리(border), 외부 간격(margin)으로 구성

---

### Margin

- 이 박스와 다른 요소와의 외부 간격

### Content

- 실제 내용이 위치하는 영역

### Border

- content와 padding을 감싸는 테두리

### Padding

- content와 border 사이의 내부 여백

```html
<!DOCTYPE html>
<html lang="en">

<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
  <style>
    .box1 {
      width: 200px;
      padding-left: 25px;
      padding-bottom: 25px;
      margin-left: 25px;
      margin-top: 50px;
      border-width: 3px;
      border-style: solid;
      border-color: black;
    }

    .box2 {
      width: 200px;
      padding: 25px 50px;
      margin: 25px auto;
      border: 1px dashed black;
    }
  </style>
</head>

<body>
  <div class="box1">box1</div>
  <div class="box2">box2</div>
</body>

</html>

```

---

## Box sizing 크기 계산법

### The standard CSS box model

1. 표준 상자 모델에서 width와 height 속성 값을 설정 → content box  크기 조정
2. CSS는 border box가 아닌 content box의 크기를 width 값으로 지

---

### The alternative CSS box model

- 대체 상자 모델에서 모든 width와 height는 실제 상자의 너비
- 실제 박스 크기를 정하기 위해 테두리와 패딩을 조정할 필요 없

```html
<!DOCTYPE html>
<html lang="en">

<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
  <style>
    .box {
      width: 100px;
      border: 2px solid black;
      padding: 10px;
      margin: 20px;
      background-color: yellow;
    }

    .content-box {
      box-sizing: content-box;
    }

    .border-box {
      box-sizing: border-box;
    }
  </style>
</head>

<body>
  <div class="box content-box">content-box</div>
  <div class="box border-box">border-box</div>
</body>

</html>
```
