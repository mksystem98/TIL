>  [!NOTE] 
>
> 참고 강의 및 링크 출처
> [HTML - Web 개발 학습하기 | MDN](https://developer.mozilla.org/ko/docs/Learn/HTML) 
> [The Web Developer Bootcamp: Learn HTML, CSS, Node, and More! | Udemy](https://www.udemy.com/course/the-web-developer-bootcamp-2021-korea/?couponCode=GENAISALE24)

## HTML이란 ?
HTML(HyperText Markup Language)은 웹의 기본 구성 요소 중 하나이며, 웹 페이지의 내용과 구조를 담당하는 마크업 언어이다.
CSS는 외관(스타일), JavaScript는 동작(기능)을, HTML은 웹 페이지의 내용과 구조를 담당한다.

![capture 100](https://github.com/mksystem98/TIL/assets/147119824/f35c48da-65ad-4565-9673-471c8678a9bd)
[The Fundamental Elements of Web Development: HTML, CSS, and JavaScript](https://www.linkedin.com/pulse/fundamental-elements-web-development-html-css-anass-essadikine-byn7e)

<br>
HTML은 elements(요소)로 구성되어 있으며, 이 요소들을 태그를 통해 웹 문서에 표현된다. 각 요소는 시작 태그로 시작해서 종료 태그로 끝나며, 이 사이에 콘텐츠(텍스트, 이미지 등)를 포함한다. 일부 요소는 종료 태그 없이 단일 태그로만 사용되기도 한다.
이러한 요소들을 통해 문서의 제목, 단락, 링크, 이미지 등 웹 페이지의 다양한 부분을 정의하는 데 사용된다. 

## HTML Element(요소)의 구조
![image](https://github.com/mksystem98/TIL/assets/147119824/a6f5f949-a469-479e-b868-6979ca3651a0)
[HTML 시작하기 | MDN](https://developer.mozilla.org/ko/docs/Learn/HTML/Introduction_to_HTML/Getting_started)

- **여는 태그(Opening tag)와 닫는 태그(Closing tag)** :
	- `<p>` `</p>` 처럼 열고 닫는 꺽쇠 괄호가 사용되고, 닫는 태그의 경우는 요소의 이름 앞에`/`를 붙여준다.
- **내용(Content)**: 요소의 내용이며, 텍스트, 이미지 등을 작성할 수 있다.
- **요소(Element)**: 여는 태그, 닫는 태그, 내용을 통들어 요소라고 한다.

>  [!TIP] 
>
> 태그는 대소문자 구분을 하지 않는다.


## 블록 레벨 요소와 인라인 요소

HTML에서 요소는 블록 레벨 요소와, 인라인 요소 2가지로 구분된다. 

- **블록 레벨 요소**
	- 새로운 줄(블록)에서 시작하며, 가능한 많은 너비를 차지한다.
	- 주로 문서의 구조를 구성하는 데 사용되며, 단락(`<p>`), 제목(`<h1>`), 리스트(`<ul>, <ol>`), `<div>` 등이 있다.
	- 블록 레벨 요소는 내부에 다른 블록 레벨 요소나 인라인 요소를 포함할 수 있다.

- **인라인 요소**
	- 새로운 줄에서 시작하지 않고, 필요한 만큼의 너비만을 차지한다. 주로 텍스트 내에서 스타일링이나 구조를 추가할 때 사용된다.
	- 예로는 링크(`<a>`), 강조(`<em>`), 이미지(`<img>`), `<span>` 등이 있다.
	- 인라인 요소는 다른 인라인 요소를 포함할 수 있지만, 보통 블록 레벨 요소를 포함하지는 않는다. 

```html
<em>안녕</em>
<em>하세요</em>
<em>여러분</em>

<p>Hello</p>
<p>HTML</p>
<p>World !</p>
```

![capture 101](https://github.com/mksystem98/TIL/assets/147119824/9ed798f1-8ddd-42a1-92b3-1b808aeb1732)



<br>

## 제목 요소

`<h1> - <h6>` 요소를 통해 6단계의 제목을 나타낼 수 있다. 
`<h1>` 이 가장 큰 제목이며, `<h1`>은 한 페이지 당 하나만 존재해야 하고 항상 최상위 제목이 되도록 한다. 
여러 `<h1>`을 여러 번 사용할 수 있지만, 문서 구조의 명확성이나, 검색 엔진 최적화의 고려를 위해 한 번만 사용하는 것이 권장된다.

```html
<h1>h1 제목입니다.</h1>
<h2>h2 제목입니다.</h2>
<h3>h3 제목입니다.</h3>
<h4>h4 제목입니다.</h4>
<h5>h5 제목입니다.</h5>
<h6>h6 제목입니다.</h6>
```

<h1>h1 제목입니다.</h1>
<h2>h2 제목입니다.</h2>
<h3>h3 제목입니다.</h3>
<h4>h4 제목입니다.</h4>
<h5>h5 제목입니다.</h5>
<h6>h6 제목입니다.</h6>


<br>
## HTML 상용구 (SKELETON)

HTML 상용구는 만드는 모든 HTML 파일의 기본 구조를 형성하는 코드의 집합이다. 
간단한 프로젝트나 학습 목적의 페이지에서는 상용구 없이도 작동이 되지만 페이지의 기능성, 호환성, 접근성을 보장하고 사용자와 검색 엔진에서의 최적화를 제공하기 위해 HTML상용구를 사용하는 것이 권장된다.

>  [!TIP] 
> Visual Studio Code에서 ' ! + tab ' 을 통해 간단하게 HTML 상용구를 생성할 수 있다.

```html
<!DOCTYPE html>
<html>
    <head>
        <meta charset="UTF-8" />
        <title>This is title</title>
    </head>
    <body>
    
    </body>
</html>
```

- `<!DOCTYPE html>` : 문서가 HTML5 표준을 따르고 있음을 브라우저에게 알린다. 이를 생략했을 때 차이가 없는 것처럼 보일 수 있지만, 복잡한 레이아웃이나 최신 CSS/JavaScript 기능을 사용하는 웹 페이지를 개발할 때는, `<! DOCTYPE html>` 선언을 꼭 포함해주어서 브라우저가 문서를 표준 모드로 정확히 해석하고 렌더링할 수 있도록 해주어야 한다.
- `<html>` : HTML 문서의 루트 요소로, 문서의 다른 요소는 이 태그 내부에 위치해야 한다.
	- `<meta charset="UTF-8">` : 문서의 문자 인코딩을 UTF-8로 설정한다.
	- `<title>` : 브라우저 탭에 표시될 문서의 제목을 정의한다.
- `<head>` : 문서의 메타데이터, 제목, 스타일 시트 링크, 스크립트 등을 포함하는 섹션이다.
	- ![[Pasted image 20240328214038.png|300]]
- `<body>` : 실제 페이지 콘텐츠를 포함하는 부분이다. 텍스트, 이미지, 폼 등이 이 섹션에 위치하게 된다. 

>  [!IMPORTANT] 
>
> 표준 HTML 문서 구조는 하나의 `<html>` 요소 내에  `<head>` 섹션 하나와 `<body>` 섹션 한 쌍으로 이루어져야 한다.



## 목록 요소

HTML의 목록을 만드는 데는 순서 있는 목록(Ordered Lists)와 순서 없는 목록(Unordered Lists) 두 가지 유형이 사용된다.

1. 순서 있는 목록 (Ordered Lists)
- `<ol>` 태그를 사용한다.
- 각 목록 항목은 `<li>` 로 감싸며, 각 항목은 순서를 가지고 자동으로 번호가 매겨진다.
```html
<ol>
  <li>1번째 항목입니다.</li>
  <li>2번째 항목입니다.</li>
  <li>3번째 항목입니다.</li>
</ol>
```
<ol>
  <li>첫 번째 항목입니다.</li>
  <li>두 번째 항목입니다.</li>
  <li>세 번째 항목입니다.</li>
</ol>


<br>




2. 순서 없는 목록 (Unordered Lists)
- `<ul>` 태그를 사용한다.
- 각 목록 항목은 `<li>`로 감싸며, 각 항목 앞에 점이 붙는다.
```html
<ul>
  <li>Apple</li>
  <li>Banana</li>
  <li>Grape</li>
</ul>
```
<ul>
  <li>Apple</li>
  <li>Banana</li>
  <li>Grape</li>
</ul>


## 앵커 태그 - 하이퍼링크

앵커 태그 `<a>` 는 문서에 사용자가 클릭할 수 있는 하이퍼링크를 만들어, 다른 페이지나 파일, 위치 등으로 이동할 수 있는 기능을 제공한다.

```html
<!--기본 구조-->
<a href="URL주소">사용자에게 표시되는 텍스트</a>

<!--다른 페이지로 이동-->
<a href="https://www.google.com">Go to Google</a>

<!--페이지 내 이동-->
<a href="#HTML 기초">Go to HTML 기초</a>
```

<a href="https://www.google.com">Go to Google</a>
<a href="#HTML 기초">Go to HTML 기초</a>


## 이미지 요소

HTML 문서에 이미지를 삽입할 수 있다. 열고 닫는 태그 없이 `<img>` 만을 사용한다. 이미지 소스, 대체 텍스트, 크기 등을 지정할 수 있다.

```html
<!--기본 구조-->
<img src="image_url.jpg" alt="대체 텍스트" width="500" height = "600>

<img src="https://github.githubassets.com/assets/GitHub-Mark-ea2971cee799.png" alt="This is Github Image" width="400" height="400">
```

<img src="https://github.githubassets.com/assets/GitHub-Mark-ea2971cee799.png" alt="This is Github Image" width="300" height="300">



## 주석

소스 코드 내에 메모나 설명을 추가하는 데 사용된다. 주석된 부분은 웹 페이지에 표시되지 않는다.

```html
<!-- 주석의 사용 예 입니다. -->

<!--
여러 줄 주석을 사용할 수 있습니다.
여러 줄에 걸쳐 설명을 추가해 보세요.
-->
```



# HTML 시멘틱


## HTML5 란?

HTML5는 HTML의 최신 버전이다. 단순히 문서의 버전이라기보다는 웹의 기능과 가능성을 확장하는 표준의 집합을 의미한다. HTML5는 다운로드하거나 설치할 필요 없다. 그저 웹 브라우저들이 이러한 HTML5 문서를 해석하고 사용자에게 표시할 뿐이다.

HTML5의 주요 특징으로는 새로운 요소(`<section>, <nav>, <header>, <footer>등)` 의 추가, 웹 애플리케이션 지원, 웹 접근성 향상 등이 있다.


## hr, br, sup, sub

**`<hr>`** 태그는 'horizontal rule'의 약자로, 수평선을 의미한다. 종료 태그가 필요하지 않다. 문서의 구조나 내용의 흐름을 구분짓는 데 사용하고, CSS를 통해 스타일링이 가능하다.
```html
<p> 안녕하세요. </p>
<hr>
<p> 수직 선 입니다. </p>
```
<p> 안녕하세요. </p>
<hr>
<p> 수직 선 입니다. </p>

<br>

**`<br>`** 태그는 줄 바꿈을 나타내는 데 사용된다. 텍스트 내에서 새로운 줄을 시작할 때 사용되며, 종료 태그가 필요하지 않다.
```html
<p> 안녕하세요. </p>
<br>
<p> 줄 바꿈 입니다. </p>
```
<p> 안녕하세요. </p>
<br>

<p> 줄 바꿈 입니다. </p>

<br>



**`<sup>`** 태그는 윗첨자를 표현하는 데 사용된다. 

```html
<p>공식 E=mc<sup>2</sup> 입니다.</p>
```
<p>공식 E=mc<sup>2</sup> 입니다.</p>

<br>

**`<sub>`** 태그는 아랫첨자를 표현하는 데 사용된다.
```html
<p>물의 화학식 H<sub>2</sub>O 입니다.</p>
```
<p>물의 화학식 H<sub>2</sub>O 입니다.</p>

<br>


## 엔티티 코드(entity code)

엔티티 코드는 HTML에서 특정 문자를 나타내기 위해 사용되는 문자열이다. 예를 들어 `<`와 `>` 같은 경우 HTML내에서 태그로 사용되는 문자이기 때문에, 혼동될 우려가 있어 엔티티 코드를 꼭 사용해야 할 때가 있다.

엔티티 코드는 일반적으로 `&`로 시작하여 `;`로 끝나는 형식을 가진다. 표현 방법으로는 두 가지가 있는데, 엔티티 이름(`&copy;`)과 엔티티 넘버(`&#169;`)로 나뉘는데, 가독성이나 기억하기 쉬운지를 고려했을 때 엔티티 이름을 더 많이 사용된다.

```html
<p>&copy; All rights reserved.</p>
<p>Your Product&reg; is registered.</p>
```
<p>&copy; All rights reserved.</p>
<p>Your Product&reg; is registered.</p>

엔티티 코드는 'copyright entity code'처럼 검색을 하거나, 엔티티 코드들을 모아놓은 사이트들을 통해 찾아낼 수 있다.
[Entity Code 사이트](https://entitycode.com/)

<br>


## 시맨틱 마크업 (Semantic Markup)

시맨틱 마크업은 마크업에 의미를 부여해주는 것이다. 다른 추가되는 기능은 없지만, 협업을 하거나 코드 유지보수를 하는 등 코드를 읽을 때 가독성이 높아지는 효과가 있다.

- `<header>` - 페이지나 섹션의 머리말 영역을 나타냄
- `<footer>` - 페이지나 섹션의 바닥글 영역을 나타냄
- `<nav>` - 네비게이션 링크의 그룹을 나타냄
- `<article>` - 독립적으로 배포하거나 재사용할 수 있는 콘텐츠를 나타냄
- `<section>` - 문서의 일반적인 섹션을 나타냄
- `<main>` - 페이지의 주요 콘텐츠 영역을 나타냄

시맨틱 마크없이 없던 시절, `<div>` 만으로 웹 페이지의 콘텐츠를 그룹화 했었다.
시맨틱 마크업이 나오면서 페이지 내의 콘텐츠가 가지는 구체적 의미를 명확하게 정의하면서 페이지의 구조를 잘 이해할 수 있게 되었다.

<br>


## VSCode Emmet

 VSCode 에 내장되어 있는 도구로 HTML을 쉽게 작성할 수 있도록 도와준다. 축약된 구문을 통해 HTML 요소들을 빠르게 생성할 수 있다.
```html
<!-- 하위 요소 생성: ">" -->
nav>ul>li
	<nav>
        <ul>
            <li></li>
        </ul>
    </nav>

<!-- 동급 요소 생성: "+" -->
div+p+bq
    <div></div>
    <p></p>
    <blockquote></blockquote>

<!-- 반복 태그 생성: "*" -->
ul>li*5
	<ul>
        <li></li>
        <li></li>
        <li></li>
        <li></li>
        <li></li>
    </ul>

<!-- 넘버링: "$" -->
ul>li*3>a$
	<ul>
        <li></li>
        <li></li>
        <li></li>
    </ul>>a$
```



<br>

<br>

# HTML Form & Table


## HTML Table

HTML에서 행과 열의 형태로 데이터를 정렬하여 사용한다. 테이블을 만들기 위해 사용되는 주요 태그들은 다음과 같다.

- `<tale>` : 테이블을 생성하기 위한 컨테이너. 테이블 관련 요소는 이 태그 안에 포함된다.
- `<tr>` (Table Row): 테이블의 한 행. 행 안에는 하나 이상의 테이블 데이터(`<td>`) 테이블 헤더(`<th>`)셀이 들어갈 수 있다.
- `<th>` (Table Header): 테이블의 열 또는 행의 제목을 나타내는 셀
- `<td>` (Table Data): 테이블의 실제 데이터를 담고 있는 셀
- `<thead>` : 테이블의 헤더(머리말) 부분을 그룹화한다. 
- `<tbody>` : 테이블의 본문 내용을 그룹화한다.
- `<tfoot>` : 테이블의 바닥글(꼬리말) 부분을 그룹화한다.

```html
<table>        <!-- 테이블 생성 -->
    <thead>    <!-- 헤더 부분 그룹화 -->
        <tr>   <!-- 테이블의 한 행-->
            <th>번호</th>    <!-- 테이블의 첫 번째 열 제목 -->
            <th>이름</th>    <!-- 테이블의 두 번째 열 제목 -->
            <th>나이</th>    <!-- 테이블의 세 번째 열 제목 -->
        </tr>
    </thead>
    <tbody> <!-- 테이블의 본문 그룹화 -->
        <tr>
            <td>1</td>   <!-- 첫번째 행데이터 입력 -->
            <td>홍길동</td>
            <td>30</td>
        </tr>
        <tr>
            <td>2</td>  <!-- 두번째 행 데이터 입력 -->
            <td>김철수</td>
            <td>25</td>
        </tr>
    </tbody>
    <tfoot>  <!-- 테이블의 바닥글 그룹화 -->
        <tr>
            <td>평균 나이</td>
            <td>27.5</td>
            <td></td>
        </tr>
    </tfoot>
</table>
```
<table>        <!-- 테이블 생성 -->
    <thead>    <!-- 헤더 부분 그룹화 -->
        <tr>   <!-- 테이블의 한 행-->
            <th>번호</th>    <!-- 테이블의 첫 번째 열 제목 -->
            <th>이름</th>    <!-- 테이블의 두 번째 열 제목 -->
            <th>나이</th>    <!-- 테이블의 세 번째 열 제목 -->
        </tr>
    </thead>
    <tbody> <!-- 테이블의 본문 그룹화 -->
        <tr>
            <td>1</td>   <!-- 첫번째 행데이터 입력 -->
            <td>홍길동</td>
            <td>30</td>
        </tr>
        <tr>
            <td>2</td>  <!-- 두번째 행 데이터 입력 -->
            <td>김철수</td>
            <td>25</td>
        </tr>
    </tbody>
    <tfoot>  <!-- 테이블의 바닥글 그룹화 -->
        <tr>
            <td>평균 나이</td>
            <td>27.5</td>
            <td></td>
        </tr>
    </tfoot>
</table>

<br>

### rowspan 과 colspan

rowspan과 colspan 는 테이블 셀이 여러 행이나 열에 걸쳐 확장될 수 있도록 한다.
colspan은 셀이 차지하는 열의 수를 지정하여 하나의 셀이 여러 열에 확장되도록 한다.
rowspan은 셀이 차지하는 행의 수를 지정하여 하나의 셀이 여러 행에 걸쳐 확장되도록 한다.

```html
<table border="1">
  <tr>
    <th>시간</th>
    <th>세미나실</th>
    <th>대강당</th>
  </tr>
  <tr>
    <td>09:00 - 10:00</td>
    <td colspan="2">개회사</td>
  </tr>
  <tr>
    <td>10:00 - 11:00</td>
    <td>기술 세미나</td>
    <td rowspan="2">워크숍</td>
  </tr>
  <tr>
    <td>11:00 - 12:00</td>
    <td>제품 발표</td>
  </tr>
</table>
```


<table border="1">
  <tr>
    <th>시간</th>
    <th>세미나실</th>
    <th>대강당</th>
  </tr>
  <tr>
    <td>09:00 - 10:00</td>
    <td colspan="2">개회사</td>
  </tr>
  <tr>
    <td>10:00 - 11:00</td>
    <td>기술 세미나</td>
    <td rowspan="2">워크숍</td>
  </tr>
  <tr>
    <td>11:00 - 12:00</td>
    <td>제품 발표</td>
  </tr>
</table>
<br>



## HTML Form

HTML에서 사용자로부터 데이터를 수집하기 위한 방법으로 `<form>`이 쓰인다. 폼을 통해 텍스트 입력, 체크박스, 옵션, 버튼 등 다양한 방법의 데이터를 입력할 수 있다.


**`<form>`**: 사용자 입력을 수집하기 위해 사용된다. action 속성을 이용해 폼 데이터가 전송될 서버가 URL을 지정하여 전송한다.
```html
<form action="데이터가 전송될 URL"></form>
```

<br>

**`<input>`**: 가장 일반적인 입력 필드를 생성한다. 다양한 type을 지정하여 텍스트, 패스워드, 체크박스, 라디오 버튼 등 다양한 속성을 가질 수 있다.

```html
<!-- 텍스트 입력 -->
<input type="text">

<!-- 비밀번호 입력 -->
<input type="password">
```
![textpassword](https://github.com/mksystem98/TIL/assets/147119824/b32ef734-8919-429a-83f5-44f9c8a1be36)

<br>

```html
<!-- 체크박스 -->
<input type="checkbox"> <!--checked 속성을 넣으면 체크된 상태로 표현됨.-->
```
![checkbox](https://github.com/mksystem98/TIL/assets/147119824/914edb71-7789-4750-8504-856f6bbb9d0f)

<br>

```html
<!-- 라디오 버튼 -->
<!-- 같은 name을 부여해서 서로를 연결해주어야 한다.  -->
<label for="S">s: </label>
<input type="radio" name="size" id="S" value="s"/>
<label for="M">m:</label>
<input type="radio" name="size" id="M" value="m"/>
<label for="L">l:</label>
<input type="radio" name="size" id="L" value="l"/>
```

![Apr-02-2024 10-31-56](https://github.com/mksystem98/TIL/assets/147119824/d8ff1ad5-4df2-4166-8a05-457f756c455a)

<br>

```html
<!-- 슬라이드 컨트롤 -->
<label for="volume">음량</label>
<input type="range" id="volme" min="0" max="100" />
```
![volume](https://github.com/mksystem98/TIL/assets/147119824/1b41162e-05dd-4af6-9846-515d19ea70e9)

<br>


```html
<!-- 여러 줄의 텍스트를 입력받는 폼 컨트롤 -->
<!-- cols, rows 속성을 통해 입력받는 텍스트 창의 크기 조절 가능 -->
<label for="request">메모를 남겨주세요.</label>
<textarea id="request" cols="20" rows="5"></textarea>
```
![image](https://github.com/mksystem98/TIL/assets/147119824/65a6ba2b-0b22-4630-961a-b4317dcff5f8)



<br>

**`<label>`**: 폼 요소에 레이블을 붙이는 데 사용된다. id값을 동일하게 설정해주어 두 요소를 연결해주면, 레이블을 클릭했을 때 연결된 폼 요소를 활성화시킬 수 있다.

```html
<label for="username">사용자 이름:</label>
<input type="text" id="username" name="user_name">
```

![Apr-01-2024 22-48-02](https://github.com/mksystem98/TIL/assets/147119824/7eab9f8a-5f10-4894-ae0f-53f9d3332d7f)

<br>

**`<button>`**: 클릭할 수 있는 버튼을 생성하는 요소이다. type값을 할당하여 여러 속성을 부여할 수 있다.

```html
<!-- 폼 제출 버튼 -->
<button type="submit">제출</button>

<!-- 폼을 제출하지 않는 평범한 버튼 -->
<button type="button">그냥 버튼</button>

<!-- 자바스크립트 함수 실행 버튼 -->
<button type="button" onclick="alert('Hello, World!')">클릭</button>
```

<br>

**`name`**: 폼 요소에 이름을 지정하는 데 사용된다. 폼이 제출될 때, name 속성을 통해 입력 필드의 데이터를 식별하는데, `name="q"` 의 속성이라면, 서버에서는 "q" 키를 사용하여 필드의 데이터를 처리한다. 

```html
<form action="http://www.google.com/search">
    <input type="text" name="q"/>
    <input type="submit" value="Google 검색" />
</form>
```

![Apr-02-2024 10-22-08](https://github.com/mksystem98/TIL/assets/147119824/6dc1a0a5-825e-4417-9c4c-0e177c5df6fd)

<br>

**`<select>`**:  드롭다운 메뉴를 생성하여 여러 옵션 중에서 하나를 선택할 수 있도록 한다. `<option>` 태그를 자식으로 가지며, 각 `<option>` 태그는 목록에서 하나의 항목을 나타낸다. 
![select](https://github.com/mksystem98/TIL/assets/147119824/eaac039d-17c8-4086-a1a7-1cb8c59cb333)