# Bootstrap

과목: Web
학습일자: 2026년 2월 26일

# Bootstrap

- CSS 프론트엔드 프레임워크
- 모바일, 태블릿, 데스크탑 등 다양한 기기 환경에서 웹 페이지가 적절하게 표시될 수 있도록 반응형 웹 디자인을 지원하는 도구(기술)
- HTML에 반영하면 폰트 및 여백 변

---

## Bootstrap 기본 사용법

- 특정한 규칙이 있는 클래스 이름으로 스타일 및 레이아웃이 미리 작성되어 있음
- property : margin 또는 padding
- sides : 방향 (top, left, x, y)
- size : Spacing의 상대적 너비

---

# Reset CSS

- 모든 HTML 요소 스타일을 일관된 기준으로 재설정하는 간결하고 압축된 규칙 시트
- HTML Element, Table, List 등의 요소들에 일관성 있게 스타일을 적용 시키는 기본 단계

---

## Reset CSS 사용 배경

- 모든 브라우저는 각자의  ‘user agent stylesheet’를 가지고 있음
    - 웹사이트를 보다 읽기 편하게
- 문제는 이 설정이 브라우저마다 상이 → 모두 똑같은 스타일 상태로 만들고 스타일 개발 시작

---

## User-agent stylesheets가 존재하는 이유

- ‘CSS가 전혀 없는 상태에서도 HTML 문서의 정보를 올바르게 전달하기 위해서
- 문서 구조의 시각화
- 최소한의 가독성 보장

---

## Normalize CSS

- 웹 표준 기준으로 브라우저 중 하나가 불일치 한다면 차이가 있는 브라우저를 수정하는 방법

---

# Typography

- 제목, 본문 텍스트, 목록

---

### Display headings

- 기존 Heading보다 더 눈에 띄는 제목이 필요할 경우
    - 더 크고 약간 다른 스타일

```html
  <!-- display heading -->
  <h1 class="display-1">Display 1</h1>
  <h1 class="display-2">Display 2</h1>
  <h1 class="display-3">Display 3</h1>
  <h1 class="display-4">Display 4</h1>
  <h1 class="display-5">Display 5</h1>
  <h1 class="display-6">Display 6</h1>
```

### Inline text elements

- HTML inline 요소에 대한 스타일

```html
<p>You can use the mark tag to <mark>highlight</mark> text.</p>
<p><del>This line of text is meant to be treated as deleted text.</del></p>
<p><s>This line of text is meant to be treated as no longer accurate.</s></p>
<p><ins>This line of text is meant to be treated as an addition to the document.</ins></p>
<p><u>This line of text will render as underlined.</u></p>
<p><small>This line of text is meant to be treated as fine print.</small></p>
<p><strong>This line rendered as bold text.</strong></p>
<p><em>This line rendered as italicized text.</em></p>

```

### Lists

- HTML 요소에 대한 스타일

```html
<ul class="list-unstyled">
  <li>This is a list.</li>
  <li>It appears completely unstyled.</li>
  <li>Structurally, it’s still a list.</li>
  <li>However, this style only applies to immediate child elements.</li>
  <li>Nested lists:
    <ul>
      <li>are unaffected by this style</li>
      <li>will still show a bullet</li>
      <li>and have appropriate left margin</li>
    </ul>
  </li>
  <li>This may still come in handy in some situations.</li>
  </ul>
```

---

## Bootstrap Color System

- Bootstrap이 지정하고 제공하는 색상 시스템
- 일관성 있는 의미론적 관점의 색상을 적용할 수 있게 해 줌
    - blue 대신 primary
    - red 대신 danger

### Colors

- Text, Border, Background 및 다양한 요소에 사용하는 Bootstrap의 색상 키워드

```html
  <!-- text colors -->
  <p class="text-primary">.text-primary</p>
  <p class="text-primary-emphasis">.text-primary-emphasis</p>
  <p class="text-secondary">.text-secondary</p>
  <p class="text-secondary-emphasis">.text-secondary-emphasis</p>
  <p class="text-success">.text-success</p>
  <p class="text-success-emphasis">.text-success-emphasis</p>
  <p class="text-danger">.text-danger</p>
  <p class="text-danger-emphasis">.text-danger-emphasis</p>
  <p class="text-warning bg-dark">.text-warning</p>
  <p class="text-warning-emphasis">.text-warning-emphasis</p>
  <p class="text-info bg-dark">.text-info</p>
  <p class="text-info-emphasis">.text-info-emphasis</p>
  <p class="text-light bg-dark">.text-light</p>
  <p class="text-light-emphasis">.text-light-emphasis</p>
  <p class="text-dark bg-white">.text-dark</p>
  <p class="text-dark-emphasis">.text-dark-emphasis</p>

```

### Background colors

```html
    <!-- background colors -->
  <div class="p-3 mb-2 bg-primary text-white">.bg-primary</div>
  <div class="p-3 mb-2 bg-primary-subtle text-primary-emphasis">.bg-primary-subtle</div>
  <div class="p-3 mb-2 bg-secondary text-white">.bg-secondary</div>
  <div class="p-3 mb-2 bg-secondary-subtle text-secondary-emphasis">.bg-secondary-subtle</div>
  <div class="p-3 mb-2 bg-success text-white">.bg-success</div>
  <div class="p-3 mb-2 bg-success-subtle text-success-emphasis">.bg-success-subtle</div>
  <div class="p-3 mb-2 bg-danger text-white">.bg-danger</div>
  <div class="p-3 mb-2 bg-danger-subtle text-danger-emphasis">.bg-danger-subtle</div>
  <div class="p-3 mb-2 bg-warning text-dark">.bg-warning</div>
  <div class="p-3 mb-2 bg-warning-subtle text-warning-emphasis">.bg-warning-subtle</div>
  <div class="p-3 mb-2 bg-info text-dark">.bg-info</div>
```

---

## Bootstrap 만으로 박스 그려보기

```html
<!DOCTYPE html>
<html lang="en">

<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
  <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.8/dist/css/bootstrap.min.css" rel="stylesheet"
    integrity="sha384-sRIl4kxILFvY47J16cr9ZwB07vP4J8+LH7qKQnuqkuIAvNWLzeN8tE5YBujZqJLB" crossorigin="anonymous">
  <style>
    .box {
      width: 200px;
      height: 200px;
    }
  </style>
</head>

<body>
  <div class="box border border-dark border-2 bg-info"></div>

  <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.8/dist/js/bootstrap.bundle.min.js"
    integrity="sha384-FKyoEForCGlyvwx9Hj09JcYn3nv7wiPVlz7YYwJrWVcXK/BmnVDxM+D2scQbITxI"
    crossorigin="anonymous"></script>
</body>

</html>
```

---

# Component

- 재사용 가능한 독립적인 부품으로, 더 크고 복잡한 시스템을 구축하기 위해 사용되는 소프트웨어의 기본 단위

---

### Alerts

```html
  <div class="alert alert-primary" role="alert">
  A simple primary alert—check it out!
  </div>
  <div class="alert alert-secondary" role="alert">
    A simple secondary alert—check it out!
  </div>
  <div class="alert alert-success" role="alert">
    A simple success alert—check it out!
  </div>
  <div class="alert alert-danger" role="alert">
    A simple danger alert—check it out!
  </div>
```

---

### Badges

```html
<h1>Example heading <span class="badge text-bg-secondary">New</span></h1>
<h2>Example heading <span class="badge text-bg-secondary">New</span></h2>
<h3>Example heading <span class="badge text-bg-secondary">New</span></h3>
<h4>Example heading <span class="badge text-bg-secondary">New</span></h4>
<h5>Example heading <span class="badge text-bg-secondary">New</span></h5>
<h6>Example heading <span class="badge text-bg-secondary">New</span></h6>

```

---

### Cards

```html
  <div class="card" style="width: 18rem;">
  <img src="..." class="card-img-top" alt="...">
  <div class="card-body">
    <h5 class="card-title">Card title</h5>
    <p class="card-text">Some quick example text to build on the card title and make up the bulk of the card’s content.</p>
    <a href="#" class="btn btn-primary">Go somewhere</a>
  </div>
```

---

### Button

```html
<button type="button" class="btn btn-primary">Primary</button>
<button type="button" class="btn btn-secondary">Secondary</button>
<button type="button" class="btn btn-success">Success</button>
<button type="button" class="btn btn-danger">Danger</button>
<button type="button" class="btn btn-warning">Warning</button>
```

### Navbar

```html
<nav class="navbar navbar-expand-lg bg-body-tertiary">
  <div class="container-fluid">
    <a class="navbar-brand" href="#">Navbar</a>
    <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarSupportedContent" aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
      <span class="navbar-toggler-icon"></span>
    </button>
    <div class="collapse navbar-collapse" id="navbarSupportedContent">
      <ul class="navbar-nav me-auto mb-2 mb-lg-0">
        <li class="nav-item">
          <a class="nav-link active" aria-current="page" href="#">Home</a>
        </li>
        <li class="nav-item">
          <a class="nav-link" href="#">Link</a>
        </li>
        <li class="nav-item dropdown">
          <a class="nav-link dropdown-toggle" href="#" role="button" data-bs-toggle="dropdown" aria-expanded="false">
            Dropdown
          </a>
          <ul class="dropdown-menu">
            <li><a class="dropdown-item" href="#">Action</a></li>
            <li><a class="dropdown-item" href="#">Another action</a></li>
            <li><hr class="dropdown-divider"></li>
            <li><a class="dropdown-item" href="#">Something else here</a></li>
          </ul>
        </li>
        <li class="nav-item">
          <a class="nav-link disabled" aria-disabled="true">Disabled</a>
        </li>
      </ul>
      <form class="d-flex" role="search">
        <input class="form-control me-2" type="search" placeholder="Search" aria-label="Search"/>
        <button class="btn btn-outline-success" type="submit">Search</button>
      </form>
    </div>
  </div>
</nav>
```

---

### Carousel

- 이미지나 텍스트 슬라이드와 같은 요소를 순환하며 보여주는 슬라이드쇼 컴포턴트
- carousel id와 data-bs-target이 각각 일치하는지 확인

```html
<div id="carouselExample" class="carousel slide">
  <div class="carousel-inner">
    <div class="carousel-item active">
      <img src="..." class="d-block w-100" alt="...">
    </div>
    <div class="carousel-item">
      <img src="..." class="d-block w-100" alt="...">
    </div>
    <div class="carousel-item">
      <img src="..." class="d-block w-100" alt="...">
    </div>
  </div>
  <button class="carousel-control-prev" type="button" data-bs-target="#carouselExample" data-bs-slide="prev">
    <span class="carousel-control-prev-icon" aria-hidden="true"></span>
    <span class="visually-hidden">Previous</span>
  </button>
  <button class="carousel-control-next" type="button" data-bs-target="#carouselExample" data-bs-slide="next">
    <span class="carousel-control-next-icon" aria-hidden="true"></span>
    <span class="visually-hidden">Next</span>
  </button>
</div>
```

---

### Modal

- 기존 화면의 상호작용을 일시적으로 차단하고 그 안에 레이어를 띄워, 사용자의 즉각적인 확인을 요구하는 대화 상자
- 주의사항
    1. modal과 modal 버튼 코드가 반드시 함께 다닐 필요는 없다
    2. modal 코드가 다른 중첩된 요소들 안에 위치할 경우 modal이 활성화 되었을 때 검은 배경 뒤로 깔려버릴 위험이 있다.
    3. modal 코드는 주로 body 태그가 닫히는 곳 바로 직전에 모아두는 것이 일반적

```html
<!-- Button trigger modal -->
<button type="button" class="btn btn-primary" data-bs-toggle="modal" data-bs-target="#exampleModal">
  Launch demo modal
</button>

<!-- Modal -->
<div class="modal fade" id="exampleModal" tabindex="-1" aria-labelledby="exampleModalLabel" aria-hidden="true">
  <div class="modal-dialog">
    <div class="modal-content">
      <div class="modal-header">
        <h1 class="modal-title fs-5" id="exampleModalLabel">Modal title</h1>
        <button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Close"></button>
      </div>
      <div class="modal-body">
        ...
      </div>
      <div class="modal-footer">
        <button type="button" class="btn btn-secondary" data-bs-dismiss="modal">Close</button>
        <button type="button" class="btn btn-primary">Save changes</button>
      </div>
    </div>
  </div>
</div>
```

---

## 컴포넌트의 특징 및 장점

- 사용성
    - 한번 잘 만들어 둔 컴포넌트는 여러 페이지에서 반복해서 사용할 수 있음
- 독립성
    - 각 컴포넌트는 자체적으로 작동하는 데 필요한 모든 코드를 가지고 있음
    - 따라서 다른 컴포턴트에 미치는 영향 최소화
- 유지보수 용이성
    - 특정 기능을 수정해야 할 때, 전체 코드를 뒤질 필요 없이 해당 컴포넌트만 찾아 수정하면 되므로, 관리가 매우 편리

---

# Semantic Web

- 웹 데이터를 의미론적으로 구조화된 형태로 표현하는 방식
- 요소의 목적과 역할에 집중하는 방식

---

## Semantic in HTML

- 외형보다는 요소 자체의 의미에 집중하는 것

---

## HTML Semantic Element

- 기본적인 모양과 기능 이외의 의미를 가지는 HTML 요소
- 검색엔진 및 개발자가 웹 페이지의 콘텐츠를 이해하기 쉽게 해준다
- Semantic 요소가 브라우저에 보여질 때는 div 요소와 똑같이 나오게 된

### header

- 소개 및 탐색에 도움을 주는 콘텐츠

```html
  <header>
    <h1>Header</h1>
  </header>
```

### nav

- 현재 페이지 내, 또는 다른 페이지로의 링크를 보여주는 구획

```html
  <nav>
    <ul>
      <li><a href="#">Home</a></li>
      <li><a href="#">About Us</a></li>
      <li><a href="#">Contact</a></li>
    </ul>
  </nav>
```

### main

- 문서의 주요 콘텐츠

```html
  <main>
    <article>
      <h2>Article Title</h2>
      <p>Article content goes here...</p>
    </article>
    <aside>
      <h3>Aside</h3>
      <ol>
        <li><a href="#">Lorem, ipsum.</a></li>
        <li><a href="#">Lorem, ipsum.</a></li>
        <li><a href="#">Lorem, ipsum.</a></li>
      </ol>
    </aside>
  </main>

```

### article

- 독립적으로 구분해 배포하거나 될 수 있는 구성의 콘텐츠 구획

```html
    <article>
      <h2>Article Title</h2>
      <p>Article content goes here...</p>
    </article>
```

### section

- 문서의 독립적인 구획
- 더 적합한 요소가 없을 때 사용

### aside

- 문서의 주요 내용과 간접적으로만 연관된 부분

### footer

- 가장 가까운 조상 구획(main, article 등)의 작성자, 저작권 정보, 관련 문서

```html
  <footer>
    <p>&copy; All rights reserved.</p>
  </footer>
```

---

## CSS 방법론

- CSS가 효율적이고 유지 보수가 용이하게 작성하기 위한 일련의 가이드라

---

## OOCSS (Object Oriented CSS)

- 객체 지향적 접근법을 적용하여 CSS를 구성하는 방법론

### 1. 구조와 스킨을 분리

- 구조와 스킨을 분리함으로써 가능성을 높임
- 구조와 색상을 나타내는 선택자가 분리
- 다른 색의 버튼을 추가할 때 다른 선언만 추가

```html
    /* 기본 버튼 구조 */
    .btn {
      display: inline-block;
      border-radius: 4px;
      padding: 8px 16px;
      font-size: 1rem;
      font-weight: 400;
      color: #212529;
      text-align: center;
      text-decoration: none;
      cursor: pointer;
    }

    /* 파란 배경 버튼 */
    .btn-blue {
      background-color: #007bff;
      color: #fff;
    }

    /* 빨간 배경 버튼 */
    .btn-red {
      background-color: #cb2323;
      color: #fff;
    }
```

### 2. 컨테이너와 콘텐츠 분리

- 객체에 직접 적용하는 대신 객체를 둘러싸는 컨테이너에 스타일을 적용
- 스타일을 정의할 때 위치에 의존적인 스타일 사용 X
- 콘텐츠를 다른 컨테이너로 이동시키거나 재배치할 때 스타일이 꺠지는 것을 방

```html
/* 기본 Card 구조 */
    .card {
      border: 1px solid #ccc;
      border-radius: 4px;
      padding: 16px;
      width: 50%;
    }

    /* Card 제목 */
    .card-title {
      font-size: 20px;
      font-weight: bold;
      margin-bottom: 8px;
    }

    /* Card 설명 */
    .card-description {
      font-size: 16px;
      margin-bottom: 16px;
    }
```

---

# Bootstrap을 사용하는 이유

- 가장 많이 사용되는 CSS 프레임워크
- 사전에 디자인된 다양한 컴포넌트 및 기능
    - 빠른 개발과 유지보수
- 손쉬운 반응형 웹 디자인 구현
- 커스터마이징이 용이
- 크로스 브라우징 지원
    - 모든 주요 브라우저에서 작동하도록 설계되어 있음

---
