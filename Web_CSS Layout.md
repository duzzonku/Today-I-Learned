# CSS Layout

과목: Web
학습일자: 2026년 2월 25일

# Display 속성 (박스의 화면 배치 방식)

## 박스 타입

- 박스 타입에 따라 페이지에서의 배치 흐름 및 다른 박스와 관련하여 박스가 동작하는 방식이 달라짐
1. Block 타입
2. Inline 타입

---

## block 타입

- 하나의 독립된 덩어리처럼 동작하는 요소
- 항상 새로운 행으로 나뉨 (한 줄 전체를 차지, 너비 100%)
- width, height, margin, padding 속성을 모두 사용 가능
- padding, margin, border로 인해 다른 요소를 상자로부터 밀어냄
- width 속성을 지정하지 않으면 박스는 inline 방향으로 사용 가능한 공간을 모두 차지
- ex) h1~6, p, div, ul, li

---

### div

- 다른 HTML 요소들을 그룹화하여 레이아웃을 구성하거나 스타일링을 적용할 수 있음
- 헤더, 푸터, 사이드바 등 웹 페이지의 다양한 섹션을 구조화하는 데 가장 많이 쓰이는 요소

---

## inline 타입

- 문장 안의 단어처럼 흐름에 따라 자연스럽게 배치되는 요소
- 줄바꿈 X
- 텍스트의 일부에만 다른 스타일 적용 가능
- width, height 속성 사용 X
- 수직 방향 ( 상하)
    - padding, margin, border 가 적용
    - 다른 요소 밀어내기 X
- 수평 방향 ( 좌우)
    - padding, margin, border 가 적용
    - 다른 요소 밀어내기 O
- ex) a, img, span, strong

```html
Box vs Inline

<!DOCTYPE html>
<html lang="en">

<head>
  <meta charset="UTF-8">
  <title>Block vs. Inline 예시</title>
  <style>
    /* 모든 div 요소에 적용 (Block 타입) */
    div {
      background-color: lightblue;
      border: 2px solid blue;
      padding: 15px;
      margin: 10px;
    }

    /* 모든 span 요소에 적용 (Inline 타입) */
    span {
      background-color: lightcoral;
      border: 2px solid red;
      padding: 10px;
      margin: 30px;
      /* 상하 마진은 다른 요소를 밀어내지 못함 */
    }

    /* width 속성 비교를 위한 div */
    .custom-width {
      width: 300px;
      /* block 타입은 width 지정 가능 */
    }
  </style>
</head>

<body>

  <h2>Block 타입 예시 (div)</h2>
  <div>
    첫 번째 div 블록입니다. width를 지정하지 않으면, <strong>한 줄 전체 너비</strong>를 차지합니다.
  </div>
  <div class="custom-width">
    두 번째 div 블록입니다. <strong>width를 300px로 지정</strong>했습니다. 블록 요소는 너비 지정이 가능합니다.
  </div>
  <div>
    세 번째 div 블록입니다. block 요소들은 <strong>자동으로 줄바꿈</strong>이 됩니다.
  </div>

  <hr>

  <h2>Inline 타입 예시 (span)</h2>
  <p>
    문장 속에서
    <span>첫 번째 span</span>
    처럼 흐름에 따라 자연스럽게 배치됩니다.
    <span>두 번째 span</span>
    처럼 줄바꿈 없이 이어지며, <strong>자신의 내용만큼만 공간을 차지</strong>합니다.
    span에 적용된 상하 여백(margin)은 다른 줄에 영향을 주지 못하는 것을 확인해 보세요.
  </p>

</body>

</html>

```

---

### span

- 자체적으로 시각적 변화 X
    - 스타일을 적용하기 전까지
- 텍스트 일부 조작
- 블록 요소처럼 줄 바꿈을 일으키지 않으므로, 문서 구조에 큰 변화 X

---

# Normal Flow

- 일반적인 흐름 또는 레이아웃을 변경하지 않은 경우 웹 페이지 요소가 배치되는 방식
- block 요소는 한 줄 전체 공간 차지
- Inline 요소는 콘텐츠만큼의 공간만 차지하여 줄 바꿈 X

```html
<!DOCTYPE html>
<html lang="en">

<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
  <style>
    a,
    span,
    img {
      border: 3px solid red;
    }

    h1,
    p,
    div {
      border: 1px solid blue;
    }
  </style>
</head>

<body>
  <h1>Normal flow</h1>
  <p>Lorem, ipsum dolor sit amet consect explicabo</p>
  <div>
    <p>block 요소는 기본적으로 부모 요소의 너비 100%를 차지하며, 자식 콘텐츠의 최대 높이를 취한다.</p>
    <p>block 요소의 총 너비와 총 높이는 content + padding + border width/height다.</p>
  </div>
  <p>block 요소는 서로 margins로 구분된다.</p>
  <p>inline 요소는 <span>이 것처럼</span> 자체 콘텐츠의 너비와 높이만 차지한다.
    그리고 inline 요소는 <a href="#">width나 height 속성을 지정 할 수 없다.</a>
  </p>
  <p>
    물론 이미지도 <img src="#"> 인라인 요소다.
    단, 이미지는 다른 inline 요소와 달리 width나 height로 크기를 조정할 수 있다.
  </p>
  <p>
    만약 inline 요소의 크기를 제어하려면 block 요소로 변경하거나 inline-block 요소로 설정해주어야 한다.
  </p>
</body>

</html>

```

---

# 기타 display 속성

## inline-block 타입

- inline과 block의 특징을 모두 가진 특별한 display 속성 값
    - 줄 바꿈 없이, 크기 지정 가능
- width, height 속성 사용 가능
- padding, margin, border로 인해 다른 요소가 상자에서 밀려남

```html
<!DOCTYPE html>
<html lang="en">

<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
  <style>
    span {
      margin: 20px;
      padding: 20px;
      width: 80px;
      height: 50px;
      background-color: lightblue;
      border: 2px solid blue;
      display: inline-block;
    }

    ul>li {
      background-color: crimson;
      padding: 10px 20px;
      display: inline-block;
    }

    .container {
      text-align: center;
    }

    .box {
      width: 100px;
      height: 100px;
      background-color: #4CAF50;
      margin: 10px;
      display: inline-block;
    }
  </style>
</head>

<body>
  <!-- 1. 이제 다른 요소를 밀어낼 수 있는 span -->
  <p>Lorem ipsum dolor sit amet <span>consectetur</span> adipisicing elit.</p>

  <!-- 2. 리스트 요소를 가로로 정렬 -->
  <ul>
    <li><a href="#">link</a></li>
    <li><a href="#">link</a></li>
    <li><a href="#">link</a></li>
  </ul>

  <!-- 3. div 요소를 가로로 정렬 -->
  <div class="container">
    <div class="box"></div>
    <div class="box"></div>
    <div class="box"></div>
  </div>
</body>

</html>
```

---

## none 타입

- 요소를 화면에 표시하지 않고, 공간조차 부여되지 않음

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
      height: 100px;
      background-color: red;
      border: 2px solid black;
    }

    .none {
      display: none;
    }
  </style>
</head>

<body>
  <div class="box"></div>
  <div class="box none"></div>
  <div class="box"></div>
</body>

</html>
```

---

# CSS Position

## CSS Layout

- 각 요소의 위치와 크기를 조정하여 웹 페이지의 디자인을 결정하는 것
- 요소들을 상하좌우로 정렬하고, 간격을 맞추고, 전체적인 페이지의 뼈대를 구성
- 핵심 속성 : display(block, inline, flex, grid, .. )

---

## CSS Position

- 요소를  Normal Flow에서 제거하여 다른 위치로 배치하는 것
- 다른 요소 위에 올리기, 화면의 특정 위치에 고정시키기 등
- 핵심 속성 : position(static, relative, absolute, fixed, sticky, .. )

---

### Position 이동 방향

- 4가지 방향 속성 (상, 하, 좌, 우)을 이용해 요소의 위치를 조절할 수 있음
- 겹치는 요소의 쌓이는 순서를 조절할 수 있음

---

# Position 유형

## 1. Position : static

- 요소를 Normal Flow에 따라 배치
- top, right, bottom, left 속성이 적용되지 않음

```html
<!DOCTYPE html>
<html>

<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
  <style>
    * {
      box-sizing: border-box;
    }

    body {
      height: 1500px;
    }

    .container {
      /* position: relative; */
      height: 300px;
      width: 300px;
      border: 1px solid black;
    }

    .box {
      height: 100px;
      width: 100px;
      border: 1px solid black;
    }

    .static {
      position: static;
      background-color: lightcoral;
    }

    .absolute {
      /* position: absolute; */
      background-color: lightgreen;
      top: 100px;
      left: 100px;
    }

    .relative {
      /* position: relative; */
      background-color: lightblue;
      top: 100px;
      left: 100px;
    }

    .fixed {
      /* position: fixed; */
      background-color: gray;
      top: 0;
      right: 0;
    }
  </style>
</head>

<body>
  <div class="container">
    <div class="box static">Static</div>
    <div class="box absolute">Absolute</div>
    <div class="box relative">Relative</div>
    <div class="box fixed">Fixed</div>
  </div>
</body>

</html>

```

---

## 2. Position : relatvie

- 요소를 Normal Flow에 따라 배치
- 자신의 원래 위치(static)을 기준으로 이동
- top, right, bottom, left 속성으로 위치를 조정
- 다른 요소의 레이아웃에 영향을 주지 않음

```html
<!DOCTYPE html>
<html>

<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
  <style>
    * {
      box-sizing: border-box;
    }

    body {
      height: 1500px;
    }

    .container {
      /* position: relative; */
      height: 300px;
      width: 300px;
      border: 1px solid black;
    }

    .box {
      height: 100px;
      width: 100px;
      border: 1px solid black;
    }

    .static {
      position: static;
      background-color: lightcoral;
    }

    .absolute {
      /* position: absolute; */
      background-color: lightgreen;
      top: 100px;
      left: 100px;
    }

    .relative {
      position: relative;
      background-color: lightblue;
      top: 100px;
      left: 100px;
    }

    .fixed {
      /* position: fixed; */
      background-color: gray;
      top: 0;
      right: 0;
    }
  </style>
</head>

<body>
  <div class="container">
    <div class="box static">Static</div>
    <div class="box absolute">Absolute</div>
    <div class="box relative">Relative</div>
    <div class="box fixed">Fixed</div>
  </div>
</body>

</html>
```

---

## 3. Position : absolute

- 요소를 Normal Flow에서 제거
- 가장 가까운 relative 부모 요소를 기준으로 이동
    - 만족하는 부모 요소가 없으면 body 태그를 기준으로 함
- top, right, bottom, left 속성으로 위치를 조정
- 문서에서 요소를 차지하는 공간이 없어짐

```html
<!DOCTYPE html>
<html>

<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
  <style>
    * {
      box-sizing: border-box;
    }

    body {
      height: 1500px;
    }

    .container {
      position: relative;
      height: 300px;
      width: 300px;
      border: 1px solid black;
    }

    .box {
      height: 100px;
      width: 100px;
      border: 1px solid black;
    }

    .static {
      position: static;
      background-color: lightcoral;
    }

    .absolute {
      position: absolute;
      background-color: lightgreen;
      top: 100px;
      left: 100px;
    }

    .relative {
      position: relative;
      background-color: lightblue;
      top: 100px;
      left: 100px;
    }

    .fixed {
      /* position: fixed; */
      background-color: gray;
      top: 0;
      right: 0;
    }
  </style>
</head>

<body>
  <div class="container">
    <div class="box static">Static</div>
    <div class="box absolute">Absolute</div>
    <div class="box relative">Relative</div>
    <div class="box fixed">Fixed</div>
  </div>
</body>

</html>
```

---

## 4. Position : fixed

- 요소를 Normal Flow에서 제거
- 현재 화면영역을 기준으로 이동
- 스크롤해도 항상 같은 위치에 유지됨
- top, right, bottom, left 속성으로 위치를 조정
- 문서에서 요소가 차지하는 공간이 없어짐

```html
<!DOCTYPE html>
<html>

<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
  <style>
    * {
      box-sizing: border-box;
    }

    body {
      height: 1500px;
    }

    .container {
      position: relative;
      height: 300px;
      width: 300px;
      border: 1px solid black;
    }

    .box {
      height: 100px;
      width: 100px;
      border: 1px solid black;
    }

    .static {
      position: static;
      background-color: lightcoral;
    }

    .absolute {
      position: absolute;
      background-color: lightgreen;
      top: 100px;
      left: 100px;
    }

    .relative {
      position: relative;
      background-color: lightblue;
      top: 100px;
      left: 100px;
    }

    .fixed {
      position: fixed;
      background-color: gray;
      top: 0;
      right: 0;
    }
  </style>
</head>

<body>
  <div class="container">
    <div class="box static">Static</div>
    <div class="box absolute">Absolute</div>
    <div class="box relative">Relative</div>
    <div class="box fixed">Fixed</div>
  </div>
</body>

</html>
```

---

## 5. Position : sticky

- relative와 fixed의 특성을 결합한 속성
- 스크롤 위치가 임계점에 도달하기 전에는 relative처럼 동작
- 스크롤 위치가 임계점에 도달하면 fixed처럼 화면 고정
- 다음 sticky 요소가 나오면 이전 sticky 요소의 자리를 대체
    - 이전 요소와 다음 요소의 위치가 겹치기 때문

```html
<!DOCTYPE html>
<html lang="en">

<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
  <style>
    body {
      height: 1500px;
    }

    .sticky {
      position: sticky;
      top: 0;
      background-color: lightblue;
      padding: 20px;
      border: 2px solid black;
    }
  </style>
</head>

<body>
  <h1>Sticky positioning</h1>
  <div>
    <div class="sticky">첫 번째 Sticky</div>
    <div>
      <p>내용1</p>
      <p>내용2</p>
      <p>내용3</p>
    </div>
    <div class="sticky">두 번째 Sticky</div>
    <div>
      <p>내용4</p>
      <p>내용5</p>
      <p>내용6</p>
    </div>
    <div class="sticky">세 번째 Sticky</div>
    <div>
      <p>내용7</p>
      <p>내용8</p>
      <p>내용9</p>
    </div>
  </div>
</body>

</html>
```

---

## Position absolute 활용

```html
<!DOCTYPE html>
<html lang="en">

<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
  <style>
    .card {
      position: relative;
      width: 300px;
      height: 200px;
      border: 1px solid black;
    }

    .card-content {
      padding: 10px;
    }

    .badge {
      position: absolute;
      top: 0;
      right: 0;
      background-color: red;
      color: white;
      padding: 5px 10px;
    }
  </style>
</head>

<body>
  <div class="card">
    <div class="card-content">
      <h3>Card Title</h3>
      <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit.</p>
      <span class="badge">New</span>
    </div>
  </div>
</body>

</html>
```

---

# z-index

- 요소의 쌓임 순서를 정의하는 속성
- 정수 값을 사용해 Z축 순서를 지정
- 값이 클수록 요소가 위에 쌓이게 됨
- static이 아닌 요소에만 적용
- 기본 값은 auto로 부모 요소의 z-index 값에 영향을 받음
- 같은 부모 내에서만 z-index 값을 비교하고, 값이 같으면 HTML 문서 순서대로 쌓임
- 부모의 z-index가 낮으면 자식의 z-index가 아무리 높아도 부모보다 위로 올라갈 수 없음

```html
<!DOCTYPE html>
<html lang="en">

<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
  <style>
    .container {
      position: relative;
    }

    .box {
      position: absolute;
      width: 100px;
      height: 100px;
    }

    .red {
      background-color: red;
      top: 50px;
      left: 50px;
      z-index: 3;
    }

    .green {
      background-color: green;
      top: 100px;
      left: 100px;
      z-index: 2;
    }

    .blue {
      background-color: blue;
      top: 150px;
      left: 150px;
      z-index: 1;
    }
  </style>
</head>

<body>
  <div class="container">
    <div class="box red">z-index: 3</div>
    <div class="box green">z-index: 2</div>
    <div class="box blue">z-index: 1</div>
  </div>
</body>

</html>
```

---

# CSS Flexbox

- 요소를 행과 열 형태로 배치하는 1차원 레이아웃 방식
- 공간 배열 & 정렬

### 1. Outer display 타입

- block 타입
- inline 타입

### 2. Inner display 타입

- 박스 내부의 요소들이 어떻게 배치될지를 결정
- CSS Flexbox (속성 : flex)

---

# Flexbox 구성 요소

## main axis (주 축)

- flex item들이 배치되는 기본 축
- main start에서 시작하여 main end 방향으로 배치 (기본 값)

## cross axis (교차 축)

- main axis에 수직인 축
- cross start에서 시작하여 cross end 방향으로 배치 (기본 값)

## flex container

- display : flex; 혹은 display : inline-flex; 가 설정된 부모 요소
- 이 컨테이너의 1차 자식 요소들이 Flex item이 됨
- flexbox 속성 값들을 사용하여 자식 요소 Flex Item들을 배치하는 주체

## flex item

- Flex Container 내부에 레이아웃 되는 항목
- 자유로운 순서 변경 및 정렬 가능

---

# Flexbox 속성

## 1. Flex Container 지정

- display 속성을 flex로 설정하면, Flex Container로 지정됨
- flex item은 기본적으로 행으로 나열
- flex item은 주 축의 시작 선에서 시작
- flex item은 교차 축의 크기를 채우기 위해 늘어남

```html
    .container {
      height: 500px;
      border: 1px solid black;
      display: fle
```

---

## 2. flex-direction

- flex item이 나열되는 방향을 지정
- row (기본 값) : 아이템이 가로 방향으로, 왼쪽에서 오른쪽으로 배치
- column : 아이템을 세로 방향으로, 위에서 아래로 배치
- ‘-reverse’로 지정하면 flex item 배치의 시작 선과 끝 선이 서로 바뀜

```html
    .container {
      flex-direction: row;
      /* flex-direction: column;
      /* flex-direction: row-reverse; */
      /* flex-direction: column-reverse; */
   }
```

---

## 3. flex-wrap

- flex item 목록이 flex container의 한 행에 들어가지 않을 경우, 다른 행에 배치할지 여부 결정
- nowrap(기본 값) : 줄 바꿈을 하지 않음
- wrap : 여러 줄에 걸쳐 배치될 수 있게 설정 ( 위에서 아래로 쌓임)
- wrap-reverse : 여러 줄에 걸쳐 배치되나, 줄이 쌓이는 방향이 반대(역순)로 설정

```html
    .container {
      /* flex-wrap: nowrap; */
      /* flex-wrap: wrap; */
      /* flex-wrap: wrap-reverse; */
   }
```

---

## 4. justify-content

- 주 축을 따라 flex item들을 정렬하고 간격을 조정
- flex-start(기본값) : 주 축의 시작점으로 정렬
- center : 주 축의 중앙으로 정렬
- flex-end : 주 축의 끝점으로 정렬

```html
    .container {
      /* justify-content: flex-start; */
      /* justify-content: center; */
      /* justify-content: flex-end; */
   }
```

---

## 5. allign-content

- 컨테이너에 여러 줄의 flex item이 있을 때, 그 줄들 사이의 공간을 어떻게 분배할지 지정
    - flex-wrap이 wrap 또는 wrap-reverse로 설정된 여러 행에만 적용됨
    - flex 아이템이 두 줄 이상일 때만 의미가 있
- stretch(기본값) : 여러 줄을 교차 축에 맞게 늘려 빈 공간을 채움
- center : 여러 줄을 교차 축의 중앙에 맞게 정렬
- flex-start : 여러 줄을 교차 축의 시작점에 맞게 정렬
- flex-end : 여러 줄을 교차 축의 끝점에 맞춰 정렬

```html
    .container {
	    flex-wrap : wrap;
	    
      /* align-content: flex-start; */
      /* align-content: center; */
      /* align-content: flex-end; */
   }
```

---

## 6. align-items

- 컨테이너 안에 있는 flex item들의 교차 축 정렬 방법을 지정
- stretch(기본값) : 아이템을 교차 축 높이를 꽉 채우도록 늘어남
- center : 아이템을 교차 축의 중앙에 맞게 정렬
- flex-start : 아이템을 교차 축의 시작점(가로 방향일 경우 위쪽)에 맞게 정렬
- flex-end : 아이템을 교차 축의 끝점(가로 방향일 경우 아래쪽)에 맞춰 정렬

```html
    .container {
		    align-item : center
	    /* align-items: flex-start; */
      /* align-items: center; */
      /* align-items: flex-end; */
   }
```

---

## 7. align-self

- 컨테이너 안에 있는 flex item 들을 교차 축을 따라 개별적으로 정렬
- auto(기본값) : 부모 컨테이너의 align-item 속성 값을 상속
- stretch : 해당 아이템만 교차 축 방향으로 늘어나 컨테이너를 꽉 채우도록 정렬
- center : 해당 아이템만 교차 축의 중앙에 정렬
- flex-start : 해당 아이템만 교차 축의 시작점에 정렬
- flex-end : 해당 아이템만 교차 축의 끝점에 정렬

```html
    .item1 {
      align-self: center;
    }

    .item2 {
      align-self: flex-end;
    }
```

---

## 목적에 따른 속성 분류

### 배치

- flex-direction
- flex-wrap

### 공간 분배

- justify-content
- align-content

### 정렬

- align-items
- align-self

---

### justify - 주 축

### align - 교차 축

---

## 8. flex-grow

- 남는 행 여백을 비율에 따라 각 flex item에 분배
- flex item이 컨테이너 내에서 확장하는 비율을 지정

```html
<!DOCTYPE html>
<html lang="en">

<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
  <style>
    .container {
      display: flex;
      width: 100%;
    }

    .item {
      height: 100px;
      color: white;
      font-size: 3rem;
    }

    .item-1 {
      background-color: red;
      flex-grow: 1;
    }

    .item-2 {
      background-color: green;
      flex-grow: 2;
    }

    .item-3 {
      background-color: blue;
      flex-grow: 3;
    }
  </style>
</head>

<body>
  <div class="container">
    <div class="item item-1">1</div>
    <div class="item item-2">2</div>
    <div class="item item-3">3</div>
  </div>
</body>

</html>
```

---

## 9. flex-basis

- flex item의 초기 크기 값을 지정
- flex-basis와 width 값을 동시에 적용한 경우 flex-basis가 우선

```html
<!DOCTYPE html>
<html lang="en">

<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
  <style>
    .container {
      display: flex;
      width: 100%;
    }

    .item {
      height: 100px;
      color: white;
      font-size: 3rem;
    }

    .item-1 {
      background-color: red;
      flex-basis: 300px;
    }

    .item-2 {
      background-color: green;
      flex-basis: 600px;
    }

    .item-3 {
      background-color: blue;
      flex-basis: 300px;
    }
  </style>
</head>

<body>
  <div class="container">
    <div class="item item-1">1</div>
    <div class="item item-2">2</div>
    <div class="item item-3">3</div>
  </div>
</body>

</html>
```

---

## 반응형 레이아웃

- 다양한 디바이스와 하면 크기에 자동으로 적응하여 콘텐츠를 최적으로 표시하는 웹 레이아웃 방식
- flex-wrap을 사용해 반응형 레이아웃 작성

```html
<!DOCTYPE html>
<html lang="en">

<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
  <style>
    .card {
      width: 80%;
      border: 1px solid black;
      /* 1 */
      display: flex;
      /* 2 */
      flex-wrap: wrap;
    }

    img {
      width: 100%;
    }

    .thumbnail {
      /* 3 */
      flex-basis: 700px;
      /* 4 */
      flex-grow: 1;
    }

    .content {
      /* 3 */
      flex-basis: 700px;
      /* 4 */
      flex-grow: 1;
    }
  </style>
</head>

<body>
  <div class="card">
    <img class="thumbnail" src="images/sample.jpg" alt="sample">
    <div class="content">
      <h2>Heading</h2>
      <p>Lorem, ipsum dolor sit amet consectetur adipisicing elit. Perspiciatis minus sed expedita ut nihil tempora
        neque autem odio eos, repudiandae blanditiis, molestiae consequatur. Adipisci illo dolor repellat alias
        maiores.
        Aut?</p>
    </div>
  </div>
</body>

</html>
```

---

# 마진 상쇄

- 두 block 타입 요소의 margin top과 bottom이 만나 더 큰 margin으로 결합되는 현상
- 복잡한 레이아웃에서 요소 간 간격을 일관되게 유지할 수 있다 (일관성)
- 요소  간의 간격을 더 예측 가능하고 관리하기 쉽게 만들 수 있다 (단순성)

```html
<!DOCTYPE html>
<html lang="ko">

<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Flexbox 레이아웃 예시</title>
  <style>
    body {
      display: flex;
      /* 자식 요소들을 세로로 배치 */
      flex-direction: column;
      /* 최소 높이를 뷰포트 높이로 설정하여 전체 화면 차지 */
      min-height: 100vh;
      margin: 0;
      font-family: Arial, sans-serif;
    }

    .box {
      background-color: #f0f0f0;
      border: 1px solid #000;
      padding: 20px;
      margin: 5px;
    }

    header {
      /* 헤더가 축소되지 않도록 설정 */
      flex-shrink: 0;
      display: flex;
      /* 로고와 네비게이션을 양쪽으로 정렬 */
      justify-content: space-between;
      /* 세로 방향 중앙 정렬 */
      align-items: center;
      padding: 10px 20px;
    }

    header h1 {
      margin: 0;
    }

    nav ul {
      list-style-type: none;
      padding: 0;
      margin: 0;
      /* 네비게이션 항목을 가로로 배열 */
      display: flex;
    }

    nav ul li {
      margin-left: 20px;
    }

    nav ul li a {
      text-decoration: none;
      color: #333;
    }

    main {
      /* 남은 공간을 모두 차지하도록 설정 */
      flex-grow: 1;
      display: flex;
      /* 사이드바와 콘텐츠 사이에 공간 분배 */
      justify-content: space-between;
    }

    .sidebar {
      width: 200px;
      display: flex;
      /* 내부 요소를 세로로 배치 */
      flex-direction: column;
      /* 내용을 위쪽에서 시작 */
      justify-content: flex-start;
      /* 가로 방향 중앙 정렬 */
      align-items: center;
    }

    .content {
      flex-grow: 1;
      display: flex;
      /* 가로 & 세로 방향 중앙 정렬 */
      justify-content: center;
      align-items: center;
    }

    footer {
      /* 푸터가 축소되지 않도록 설정 */
      flex-shrink: 0;
      display: flex;
      /* 가로 & 세로 방향 중앙 정렬 */
      justify-content: center;
      align-items: center;
    }
  </style>
</head>

<body>
  <header class="box">
    <h1>웹사이트 제목</h1>
    <nav>
      <ul>
        <li><a href="#home">홈</a></li>
        <li><a href="#about">소개</a></li>
        <li><a href="#services">서비스</a></li>
        <li><a href="#contact">연락처</a></li>
      </ul>
    </nav>
  </header>
  <main>
    <aside class="sidebar box">
      <h2>사이드바</h2>
      <ul>
        <li>메뉴 1</li>
        <li>메뉴 2</li>
        <li>메뉴 3</li>
      </ul>
    </aside>
    <section class="content box">
      <h2>메인 콘텐츠</h2>
    </section>
  </main>
  <footer class="box">
    <p>푸터 - 저작권 정보 등</p>
  </footer>
</body>

</html>
```

---

# 박스 타입 별 수평 정렬

## Block 요소의 수평 중앙 정렬

- margin : auto 사용
- 블록의 너비를 지정하고 좌우 마진을 auto로 설정

## Inline 요소의 수평 중앙 정렬

- text-align 사용
- 부모 요소에 적용

## Inline-block 요소의 수평 중앙 정렬

- text-align 사용
- 부모 요소에 적용
