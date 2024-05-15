# Markdown
> This is a description of how to write a document in markdown grammar.  
> (마크다운 문법으로 문서를 작성하는 방법에 대한 설명입니다.)  
> It also includes HTML grammar available on GitHub.  
> (또한 GitHub에서 사용할 수 있는 HTML 문법도 포함되어 있습니다.)

<br>

### Align(정렬)
> GitHub has only left alignment. (깃허브에는 왼쪽정렬만 있습니다.)  
> HTML grammar has center, left and right properties that can be used for sorting.  
> (HTML 문법에는 정렬에 사용할 수 있는 중앙, 왼쪽 및 오른쪽 속성이 있습니다.)

```html
<center> CENTER </center>  
<div style="text-align: left"> LEFT </div>
<div style="text-align: right"> RIGHT </div>
```
<details>
<summary>Results(실행 결과)</summary>

<center> CENTER </center>  
<div style="text-align: left"> LEFT </div>
<div style="text-align: right"> RIGHT </div>
</details>


---
### Code block(코드블록)

#### Markdown grammar
> Declaring the language can emphasis the grammar.(언어를 선언하여 문법 강조 가능)  
> Language can be omitted(언어는 생략 가능)

```md
```Language(언어)
CODE```
```

<details>
<summary>Results(실행 결과)</summary>

```
CODE
```
</details>

#### Available Languages(사용 가능한 언어)

|Language |	Markdown |	Language | Markdown|
|:---:|:---:|:---:|:---:|
|Bash |	bash |	JSON |	json|
|C# |	cs |	Java |	java |
|C++	| cpp	| JavaScript |	javascript|
|CSS | css |	PHP |	php|
|Diff |	diff |	Perl |	perl|
|HTML, XML |	html |	Python |	python|
|HTTP |	http |	Ruby |	ruby|
|Ini |	ini |	SQL |	sql|

<br>

#### HTML grammar
```HTML
<pre>
  <code>CODE</code>
</pre>
```
<details>
<summary>Results(실행 결과)</summary>

<pre>
  <code>CODE</code>
</pre>
</details>

---
### Comment(주석)
```md
contents1
<!-- Comment -->
contents2
```
<details>
<summary>Results(실행 결과)</summary>

contents1
<!-- Comment -->
contents2
</details>

---
### Details(접기/ 펼치기)
```HTML
<details>
<summary>Folding/Unfolding</summary>

<!-- summary 아래 한칸 공백 두어야함 -->
CONTENTS
</details>
```

<details>
<summary>Folding/Unfolding</summary>

CONTENTS
</details>

---
### Heading(글머리)

#### Markdown grammar

```md
# Head1(h1)
## Head2(h2)
### Head3(h3)
#### Head4(h4)
##### Head5(h5)
###### Head6(h6)
```
<details>
<summary>Results(실행 결과)</summary>

# Head1(h1)
## Head2(h2)
### Head3(h3)
#### Head4(h4)
##### Head5(h5)
###### Head6(h6)
</details>

#### HTML grammar

```html
<h1>Head1(h1)</h1>
<h2>Head2(h2)</h2>
<h3>Head3(h3)</h3>
<h4>Head4(h4)</h4>
<h5>Head5(h5)</h5>
<h6>Head(h6)</h6>
```
<details>
<summary>Results(실행 결과)</summary>

<h1>Head1(h1)</h1>
<h2>Head2(h2)</h2>
<h3>Head3(h3)</h3>
<h4>Head4(h4)</h4>
<h5>Head5(h5)</h5>
<h6>Head(h6)</h6>
</details>

---

### Newline(줄바꿈)
> In Markdown, you can't change a line with just one enter.  
> (마크다운에서는 엔터 한번만으로는 줄을 변경할 수 없습니다.)

```md
1st ROW
2nd ROW
```
<details>
<summary>Results(실행 결과)</summary>

  1st ROW
  2nd ROW
</details>

<br>

#### Markdown grammar
> There are two ways to change a line.


 1. Input 2 spaces at the end of the sentence.
(문장 마지막에 공백 2개로 줄바꿈)

```md
1st ROW  <!-- 1st ROW__ (문장 마지막에 공백 2개 입력-->
2nd ROW
```
  <details>
  <summary>Results(실행 결과)</summary>
  
    1st ROW  
    2nd ROW
  </details>

2. Input Enter twice.
(Enter키 2번으로 줄바꿈)

```md
1st ROW

2nd ROW
```
  <details>
  <summary>Results(실행 결과)</summary>
  
    1st ROW
    
    2nd ROW
  </details>

#### HTML grammar
```html
1st ROW<br>2nd ROW
```
<details>
<summary>Results(실행 결과)</summary>

1st ROW<br>2nd ROW
</details>

---
### Table(표)
#### Markdown grammar

```
|제목|내용|설명|
|------|------|------|
|테스트1|테스트2|테스트3|
|테스트1|테스트2|테스트3|
|테스트1|테스트2|테스트3|
```

<details>
<summary>Results(실행 결과)</summary>
  
|제목|내용|설명|
|------|------|------|
|테스트1|테스트2|테스트3|
|테스트1|테스트2|테스트3|
|테스트1|테스트2|테스트3|
</details>


##### Align(정렬)
```
|제목|내용|설명|
|:-----|-----:|:-----:|
|왼쪽정렬|오른쪽정렬|중앙정렬|
|왼쪽정렬|오른쪽정렬|중앙정렬|
|왼쪽정렬|오른쪽정렬|중앙정렬|
```
<details>
<summary>Results(실행 결과)</summary>

|제목|내용|설명|
|:-----|-----:|:-----:|
|왼쪽정렬|오른쪽정렬|중앙정렬|
|왼쪽정렬|오른쪽정렬|중앙정렬|
|왼쪽정렬|오른쪽정렬|중앙정렬|
</details>


##### Extends cell width(셀 확장)
```
|제목|내용|설명|
|:-----|:-----:|-----:|
||중앙에서확장||
|||오른쪽에서 확장|
|왼쪽에서확장||
```
<details>
<summary>Results(실행 결과)</summary>
  
|제목|내용|설명|
|:-----|:-----:|-----:|
||중앙에서확장||
|||오른쪽에서 확장|
|왼쪽에서확장||
</details>

<br>

#### HTML grammar
```html
<table>
  <tr>
    <th>title</th>
    <th>contents</th>
    <th>description</th>
  </tr>
  <tr>
    <td>test1</td>
    <td>test2</td>
    <td>test3</td>
  </tr>
  <tr>
    <td>test1</td>
    <td>test2</td>
    <td>test3</td>
  </tr>
</table>
```
<details>
<summary>Results(실행 결과)</summary>

<table>
  <tr>
    <th>title</th>
    <th>contents</th>
    <th>description</th>
  </tr>
  <tr>
    <td>test1</td>
    <td>test2</td>
    <td>test3</td>
  </tr>
  <tr>
    <td>test1</td>
    <td>test2</td>
    <td>test3</td>
  </tr>
</table>
</details>

##### Border(테두리)

```css
border: size, border-style, color;
```

##### border-color(테두리색)
> The value of `border-color` attribute should be given in 'English' or 'RGB' or 'Hex'.  
(`border-color` 속성의 값은 영어 또는 rgb 또는 hex로 주어져야 합니다.)
```css
border-color: COLOR;
```
##### Border-style(테두리 스타일)  
> `solid`, `double`, `dotted`, `dashed`, `groove`, `ridge`, `inset`, `outset`, `none`, `hidden`
```css
border-style: solid;
```
##### Border collapse(테두리 중복 제거)
> If you give border properties to both the table and the cell, the border appears doubled.  
> (테이블과 셀 모두에 테두리 속성을 부여하면 테두리가 이중으로 나타납니다.)  
> Border redundancy can removed using `border-collapse`.  
> (`Border-collaps` 속성을 사용하여 border 이중화를 제거할 수 있습니다.)  
```css
border-collapse: collapse;
```

##### Background-color(셀 배경색)
> The Value of `background-color` attribute should be given in 'English' or 'RGB' or 'Hex'.  
> (`background-color` 속성의 값은 영어, rgb 혹은 hex 값으로 줄 수 있습니다.) 
```css
background-color: COLOR;
```

##### Border-radius(테두리 모서리 곡률)
> Use when you want to create a table with rounded edges of the border.   
> (테두리의 모서리가 둥근 테이블을 만들고 싶을 때 사용합니다.)
```css
border-radius: size(px);
```

---

### Text color(글자색)
> The value of 'color' attribute should be given in 'English' or 'RGB' or 'Hex'.
(`color` 속성의 값은 영어 또는 rgb 또는 hex로 주어져야 합니다.)
```html
<span style="color:COLOR"> COLOR </span>
```

[Color Wheel Picker](https://rgbacolorpicker.com/color-wheel-picker) : If you click the color you want, you can know the value of color in hex, rgb(a), hsl.<br>
(원하는 색을 클릭하면 hex, rgb(a), hsl 값을 알려주는 사이트)


<span style="color:red"> red </span>&nbsp
<span style="color:rgb(255,0,0)"> red(rgb(255,0,0)) </span>&nbsp
<span style="color:#ff0000"> red(#ff0000) </span>&nbsp
<span style="color:#ffd33d"> yellow </span>&nbsp
<span style="color:blue"> blue </span>&nbsp
<span style="color:brown"> brown </span>&nbsp
<span style="color:orange"> orange </span>&nbsp
<span style="color:green"> green </span>&nbsp
<span style="color:violet"> violet </span>&nbsp
<span style="color:yellowgreen"> yellowgreen </span>&nbsp
<span style="color:blueviolet"> blueviolet </span>&nbsp
<span style="color:gray"> gray</span>&nbsp
<span style="color:indigo"> indigo </span>&nbsp

<br>





