# Responsive Web

과목: Web
학습일자: 2026년 2월 27일

# 반응형 웹과 UX/UI

## 반응형 웹 디자인

- 디바이스 종류나 화면 크기에 상관없이 어디서든 일관된 레이아웃 및 사용자 경험을 제공하는 디자인 기술
- 모니터, 태블릿, 스마트폰 등 화면 크기에 따라 요소의 배치를 변경하여 일관된 사용자 경험 제공
- 다양한 화면 크기에 맞춰 UI를 유연하게 변경함으로써, 어떤 환경에서도 사용자에게 최적의 UX 제공

---

## UX (User Experience)

- 사용자가 서비스를 이용하며 느끼는 만족감이자 경험
- 제품이나 서비스를 사용하는 사람들이 느끼는 전체적인 경험과 만족도를 개선하고 최적화하기 위한 디자인과 개발 분야
- ex) 감각적 경험(브랜드 인식), 기능적 경험(사용성), 편의적 경험(흐름)

---

### UX 설계

- 사용자의 숨겨진 니즈와 행동 패턴을 데이터를 통해 깊이 이해하고, 이를 바탕으로 제품의 구조와 사용 흐름을 논리적으로 구체화 하는 과정

---

## UI (User Interface)

- 사용자와 서비스가 만나는 화면 디자인과 배치
- 서비스와 사용자 간의 상호작용을 가능하게 하는 디자인 요소들을 개발하고 구현하는 분야
- ex) 물리적 UI (리모콘), 복합적 UI (ATM 기기), 디지털 UI (Software)

---

### UI 설계

- 단순히 ‘보기 좋은’ 디자인을 넘어, 정보의 위계를 잡아 사용자가 무엇을 먼저 봐야 할지 유도하고, 일관성을 통해 학습 비용을 줄이는 것

---

# Bootstrap Grid System

- 웹 페이지의 레이아웃을 조정하는 데 사용되는 12개의 칼럼으로 구성된 시스템
- 반응형 디자인을 지원해 웹 페이지를 모바일, 태블릿, 데스크탑 등 다양한 기기에서 적절하게 표시할 수 있도록 도와줌

---

## Grid system 구조와 문법

### Container

- Column들을 담고 있는 공간

### Column

- 실제 컨텐츠를 포함하는 부분

### Gutter

- 컬럼과 컬럼 사이의 여백 영역 (상하좌우)

---

# 반응형 레이아웃 구현

## 12칸 분배

- 첫 번째 줄

```html
<div class="container">
    <div class="row">
      <div class="col">
        <div class="box">col</div>
      </div>
      <div class="col">
        <div class="box">col</div>
      </div>
      <div class="col">
        <div class="box">col</div>
      </div>
    </div>
  </div>
      
```

- 2번째 줄

```html
<div class="container">
    <div class="row">
      <div class="col-4">
        <div class="box">col-4</div>
      </div>
      <div class="col-4">
        <div class="box">col-4</div>
      </div>
      <div class="col-4">
        <div class="box">col-4</div>
      </div>
    </div>
  </div>
      
```

- 3번째 줄

```html
<div class="container">
    <div class="row">
      <div class="col-2">
        <div class="box">col-2</div>
      </div>
      <div class="col-8">
        <div class="box">col-8</div>
      </div>
      <div class="col-2">
        <div class="box">col-2</div>
      </div>
    </div>
  </div>
      
```

---

### 반응형 레이아웃 구현 - 중첩

- 하나의 Columns 안에 또 따른 Row

```html
<div class="container">
   <div class="row">
     <div class="col-4 box">
	     <div>col-4</div>
	   </div>
       <div class="col-8 box">
				 <div class='row'>
			     <div class="col-6">
		         <div class="box">col-6</div>
			     </div>
			     <div class="col-6">
		         <div class="box">col-6</div>
			     </div>
			     <div class="col-6">
		         <div class="box">col-6</div>
			     </div>
			     <div class="col-6">
		         <div class="box">col-6</div>
			     </div>
			   </div>
      </div>
    </div>
  </div>
      
```

---

### 반응형 레이아웃 구현 - 상쇄(offset)

- Offset으로 Column 생략

```html
<div class="container">
   <div class="row">
     <div class="col-4">
	     <div class='box'>col-4</div>
	   </div>
	   <div class="col-4 offset_4">
	     <div class='box'>col-4 offset-4</div>
	   </div>
	 </div>
	 <div class="row">
     <div class="col-3 offset-3">
	     <div class='box'>col-4</div>
	   </div>
	   <div class="col-3 offset_3">
	     <div class='box'>col-3 offset-3</div>
	   </div>
	 </div>
	 <div class="row">
     <div class="col-6 offset-3">
	     <div class='box'>col-6 offset-3</div>
      </div>
    </div>
  </div>
      
```

---

# Gutters

- Grid system 에서 Columns 사이의 여백 영역
    - x축은 padding 으로 여백 생성
    - y축은 margin 으로 여백 생성

```html
<div class="container">
    <div class="row gx-0">
      <div class="col-6">
        <div class="box">col</div>
      </div>
      <div class="col-6">
        <div class="box">col</div>
      </div>
    </div>
  </div>
```

---

- 간격 조정
    - gy-5
    - row 사이 여백 증가

```html
<div class="container">
    <div class="row gy-5">
      <div class="col-6">
        <div class="box">col</div>
      </div>
      <div class="col-6">
        <div class="box">col</div>
      </div>
      <div class="col-6">
        <div class="box">col</div>
      </div>
      <div class="col-6">
        <div class="box">col</div>
      </div>
    </div>
  </div>
```

---

- 간격 조정
    - g-5

```html
<div class="container">
    <div class="row g-5">
      <div class="col-6">
        <div class="box">col</div>
      </div>
      <div class="col-6">
        <div class="box">col</div>
      </div>
      <div class="col-6">
        <div class="box">col</div>
      </div>
      <div class="col-6">
        <div class="box">col</div>
      </div>
    </div>
  </div>
```

---

# Grid system for responsive web

- Bootstrap grid system에서는 12개의 column과 6개의 breakpoints를 사용하여 반응형 웹 디자인 구현

---

## Breakpoints

- 웹 페이지를 다양한 화면 크기에서 적절하게 배치하기 위한 분기점
    - 화면 너비에 따라 6개의 분기점 제공 (xs, sm, md, lg, xl, xxl)
- 각 breakpoints 마다 설정된 최대 너비 값 ‘이상으로’ 화면이 커지면 grid system 동작이 변경

---

## Breakpoints 활용

```html
<div class="container">
    <div class="row">
      <div class="col-12 col-sm-6 col-md-2 col-lg-3 col-xl-4">
        <div class="box">col</div>
      </div>
			<div class="row">
      <div class="col-12 col-sm-6 col-md-2 col-lg-3 col-xl-4">
        <div class="box">col</div>
      </div>
      <div class="row">
      <div class="col-12 col-sm-6 col-md-2 col-lg-3 col-xl-4">
        <div class="box">col</div>
      </div>
      <div class="row">
      <div class="col-12 col-sm-6 col-md-2 col-lg-3 col-xl-4">
        <div class="box">col</div>
      </div>
    </div>
  </div>
```

---

- 화면 사이즈가 변함에 따라 columns의 배치를 바꿔보자
    - offset도 함꼐 활

```html
<div class="container">
    <div class="row g-4">
      <div class="col-12 col-sm-4 col-md-6">
        <div class="box">col</div>
      </div>
			<div class="col-12 col-sm-4 col-md-6">
        <div class="box">col</div>
      </div>
      <div class="col-12 col-sm-4 col-md-6">
        <div class="box">col</div>
      </div>
      <div class="col-12 col-sm-4 col-md-6 offset-sm-4 offset-md-0">
        <div class="box">col</div>
      </div>
    </div>
  </div>
```

---

## Bootstrap Grid system 정리

- Grid System은 화면 크기에 따라 12개의 칸을 각 요소에 나누어 주는 것

---

# CSS Layout 종합 정리

## 무엇을? 언제 사용?

- 최적의 기술을 선택하고 효과적으로 활용하기 위해서는 다양한 실제 개발 경험 필수

### Position

- 벽에 붙인 스티커
- 흐름을 무시하고 원하는 좌표에 배치할 때

### Flexbox

- 방 안의 가구
- Grid로 나눈 구역 내부를 정렬할 때

### Bootstrap Grid system

- 건물의 뼈대
- 웹 페이지의 전체적인 구조를 잡을
