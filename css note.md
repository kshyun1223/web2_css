# 생활코딩 WEB2 - CSS 수업 필기노트
### CSS의 등장 배경

- 정보를 나타내는 HTML과 디자인을 나타내는 도구를 분리하여 별도로 관리할 필요성
- 개별적으로 관리하는 것이 불가능한, 극도로 많은 수의 태그들을 일괄적으로 관리할 필요성

### 주석

- `<!--내용-->`: 대상이 되는 부분이 브라우저에 출력되지 않게 하는 태그

### CSS 기본 개념

- 선택자(selector): CSS 효과를 적용할 대상
    - 여러 선택자를 한 번에 지정할 수 있으며 쉼표( , )로 구분한다.
- 효과(delaration; 선언): 대상 선택자에게 지정할 CSS 효과
    - {속성 : 값}의 형태를 가진다
- 구분자( ; ): 하나의 선택자에 여러 효과를 적용 시 효과와 효과를 구분
- `<style>` 태그
    
```html
<style>
    선택자 {
        속성:값
    }
</style>
```
    
  - `<head>`  영역에 배치되어 문서 전체의 해당 대상에 일괄적으로 CSS 효과를 적용시키는 태그
- style 속성
    
```html
    `<태그 style="속성:값"> 내용</태그>`
```
    
  - 개별 HTML 태그에 CSS 효과를 적용시키는 속성
  - 값에는 반드시 CSS 효과가 위치해야 한다

### 텍스트 디자인

```html
<style>
    선택자 {
        color:색상;
        text-decoration:none;
    }
</style>
```

- color 속성: 텍스트에 색상을 적용
- text-decoration 속성: 텍스트에 서식을 적용
    - none 값: 텍스트에 적용되어 있는 모든 서식을 해제
- 위의 상황에서 특정 요소에만 예외적으로 밑줄을 적용하려면 `<style>` 속성을 사용
    
```html
<태그 style="text-decoration:underline;">내용</태그>
```
    
  - underline 값: 텍스트에 밑줄을 적용

### 텍스트 정렬

```html
<style>
    선택자 {
        font-size:값px;
        text-align:center;
    }
</style>
```

- font-size 속성: 텍스트의 크기를 조정
- text-align 속성: 텍스트를 정렬
    - center 값: 가운데 정렬

### 선택자

- 우선순위: 아이디(ID) - 클래스(Class) - 태그(Tag)
- 태그와 구분하기 위해 아이디는 앞에 샵(#)을 붙이고, 클래스는 앞에 온점( . )을 붙인다
- 같은 종류의 선택자가 여러 개인 경우에는 뒤에 오는 것이 우선한다
- 클래스/아이디 선택자를 사용하기 위해서는 우선 대상이 되는 태그들에 속성을 지정해야 한다
- 아이디 선택자는 여러번 써도 동작은 하지만, 가급적 한 페이지에서 한 번만 사용할 것이 권장된다
  > The id of an element is unique within a page, so the id selector is used to select one unique element! ([w3schools - CSS Selectors](https://www.w3schools.com/css/css_selectors.asp))

### 박스모델

```html
<style>
    선택자 {
        border-width:두께px;
        border-color:색상;
        border-style:종류;
        padding:값px;
        margin:값;
        display:종류;
        width:값px;
    }
</style>
```

- 테두리
    - border-width 속성: 테두리의 두께
    - border-color 속성: 테두리의 색상
    - border-style 속성: 테두리의 종류
        - solid 값: 실선
    - 앞에 border- 가 붙은 속성들은 ‘border’로 축약해서 사용할 수 있다.
        - 이 경우 여러 값을 한 번에 지정할 수 있으며, 각각의 값들은 공백(  )으로 구분한다.
        - 예시: `border:5px solid red`
- 범위: 태그의 성격에 따라 기본값이 정해져 있음
    - 블록 레벨 엘리먼트(block level element): 화면 전체 영역
        - 출력 화면에서 줄바꿈이 됨 (한 줄 전체를 차지함)
        - `display:block`으로 임의 지정
    - 인라인 엘리먼트(inline element): 콘텐츠 크기만큼의 영역
        - 출력 화면에서 다른 개체들과 같은 줄에 위치함
        - `display:inline`으로 임의 지정
- 여백
    - padding: 텍스트와 테두리 사이의 간격
        - 기본적으로 붙어있으며, 값을 지정하여 떨어뜨릴 수 있다
    - margin: 테두리와 다른 테두리 사이의 간격
        - 기본적으로 떨어져있으며, 값을 0으로 지정하여 붙일 수 있다
- 크기
    - height 속성: 높이
    - width 속성: 너비
- 개발자도구
    - 웹브라우저에서 CSS 개체를 우클릭 하고 ‘검사’ 항목을 선택하면 해당 요소의 박스모델 확인 가능

### 박스모델 활용

- 가로선
    
    ```html
    <style>
        h1 {
            font-size:크기px;
            text-align:위치;
            border-bottom:두께 종류 색상;
            margin:Opx;
            padding:값px;
        }
    </style>
    ```
    
    - 제목(`<h1>`)에 아래쪽 테두리(border-bottom)를 설정하여 구현
    - 간격 조절을 위해 margin 값을 0으로 만들고 적절한 padding 값 설정
- 세로선
    
    ```html
    <style>
        ol {
            border-right:두께 종류 색상;
            width:값px;
            margin:Opx;
            padding:값px;
        }
    </style>
    ```
    
    - 목록(`<ol>`)에 오른쪽 테두리(border-right)를 설정하여 구현
    - `<ol>`의  기본 범위는 화면 전체이기 때문에 테두리를 보이게 하려면 너비를 설정해야 함
    - 간격 조절을 위해 margin 값을 0으로 만들고 적절한 padding 값 설정
- `<body>` 태그
    
    ```html
    <style>
        body {
            margin:0px
        }
    </style>
    ```
    
    - 가로선 양 끝에 여백이 있는 것은 `<body>`태그에 margin 값이 있기 때문이다
    - margin 값을 0으로 설정하면 가로선이 화면 끝까지 닿는다

### 그리드

목록과 본문을 나란히 위치하게 하는 방법

```html
<head>
    <style>
        #ID값 {
            display: grid;
            grid-template-columns: 150px 1fr；
        }
    </style>
</head>
<body>
    <div id="값">
        <div>칼럼1</div>
        <div>칼럼2</div>
    </div>
</body>
```

- 각각의 개체에 `<div>` 태그를 지정 (division; 분할)
    - `<span>` 태그도 동일한 기능을 하며 인라인 엘리먼트임
    - `<div>`는 블록 레벨 엘리먼트
- 두 태그의 부모 태그인 `<div>` 태그를 추가
- 부모 태그에 ID 속성을 부여
- `{display: grid}` 속성을 추가하는 것만으로는 아무 일도 일어나지 않는다
- 그 뒤에 다시 `{grid-template-columns}` 속성을 추가하면 그리드 기능이 구현됨
    - column은 페이지의 세로단이라는 뜻
    - 예시1: 150px과 1fr 값을 지정하면 첫 번째 칼럼은 150px을 고정적으로 차지하고 두 번째 칼럼은 가변적으로 크기가 바뀐다
    - 예시2: 2fr과 1fr 값을 지정하면 첫 번째 칼럼은 1/3만큼, 두 번째 칼럼은 2/3만큼의 비율로 가변적으로 크기가 바뀐다
    - 예시3: 어느 한 칼럼, 혹은 두 칼럼 모두의 텍스트가 증감하면 미리 설정한 비율에 따라 가변적으로 크기가 바뀐다

### Can I use

- [https://caniuse.com/](https://caniuse.com/)
- 현용 웹 브라우저들이 HTML, CSS, JavaScript 등의 기술들을 얼마나 지원하는지에 대한 통계를 제공하는 사이트

### 그리드 활용

```html
<head>
    <style>
        #grid ol {
            속성 : 값
        }                
        #grid {
            속성 : 값
        }
    <style>
</head>
<body>
    <div id="grid">
        <ol>목록</ol>
        <div>
            <h2>제목</h2>
            <p>문단</p>
        </div>
    </div>
</body>
```

- 제목 `<h2>`과 문단 `<p>`를 부모 태그 `<div>`로 묶고, 그것을 다시 목록 `<ol>`과 묶는다
- 가장 상위의 부모 태그에 ID 속성을 부여
- 목록이 첫 번째 칼럼이고, 제목과 문단을 묶은 것이 두 번째 칼럼이다
- 선택자 지정 시 특정 ID가 부여된 태그의 자식 태그만으로 범위를 한정할 수 있다
    - 예시: `#grid ol`의 경우 grid라는 ID가 부여된 태그의 자식 태그인 `<ol>`만을 선택하는 것

### 미디어쿼리

반응형 웹을 순수 CSS만으로 구현하는 기술

> 반응형 웹(responsive web): 화면 크기에 따라 웹 페이지의 각 요소들이 최적화된 모양으로 바뀌는 개념

- 화면의 크기에 따라서 대상 개체가 출력되지 않게 하는 방법
    
    ```html
    <head>
        <style>
            @media(min-width: 800px) {
            div {display: none}
            }
        </style>
    </head>
    <body>
        <div>
            대상
        </div>
    </body>
    ```
    
    - `min-width: 800px` 의 경우 화면 크기가 800픽셀보다 작다는 조건
    - `display: none` 은 대상을 출력하지 않는다는 의미
    

### 미디어쿼리 활용

```html
<head>
    <style>
        @media(min-width: 800px) {
        #grid {display: block}
        #grid ol {border-right: none}
        h1 {border-bottom: none}
        }
    </style>
</head>
```

- `min-width: 800px` 은 화면 크기가 800픽셀보다 작다는 조건
- `#grid {display: block}`은 grid라는 ID가 부여된 태그를 블록 레벨 엘리먼트로 지정
- `#grid ol {border-right: none}`은 grid라는 ID가 부여된 태그의 하위에 있는 `<ol>` 태그의 오른쪽 태두리를 출력하지 않는다는 의미
- `h1 {border-bottom: none}`은 `<h1>` 태그의 아래쪽 테두리를 출력하지 않는다는 의미

### CSS 코드의 재사용

```html
<head>
    <title>WEB1 - HTML</title>
    <meta charset="utf-8">
    <link rel="stylesheet" href="style.css" />
</head>
```

- CSS 파일을 생성하고 HTML 파일에 입력했던 `<style>` 태그의 모든 내용을 옮긴다
- 원래 `<style>` 태그가 있던 자리에 `<link rel="stylesheet" href="파일명.css" />` 라고 입력하면 기존과 동일한 효과가 구현됨
- CSS 파일 하나만을 수정하면 해당 파일이 연결되어 있던 모든 웹페이지에 적용되기 때문에 개발자는 대규모 웹사이트를 관리하기가 용이해진다
- 캐싱을 통해 CSS 파일을 저장해뒀다가 필요할 경우 새로 내려받지 않고 재사용 하기 때문에 트래픽이 줄어드는 효과도 있음
