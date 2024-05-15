# Markdown
> This is a description of how to write a document in markdown grammar.

<br>

### Align(정렬)
```
<center> CENTER </center>  
<div style="text-align: left"> LEFT </div>
<div style="text-align: right"> RIGHT </div>
```

<center> CENTER </center>  
<div style="text-align: left"> LEFT </div>
<div style="text-align: right"> RIGHT </div>

---
### Code block(코드블록)

<div style='background-color: red'>
```<b>Language</b><br>
<b>Code</b><br>
```
</div>
Declaring the language used at the start of the block code (````) enables grammar emphasis.<br>
(블럭 코드(```) 시작점에서 사용하는 언어를 선언하여 문법 강조가 가능)<br>
<i>cf. Language can be omitted. (언어는 생략 가능)</i>

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

---

### Table(표)

```
|제목|내용|설명|
|------|------|------|
|테스트1|테스트2|테스트3|
|테스트1|테스트2|테스트3|
|테스트1|테스트2|테스트3|
```

|제목|내용|설명|
|------|------|------|
|테스트1|테스트2|테스트3|
|테스트1|테스트2|테스트3|
|테스트1|테스트2|테스트3|

### Align(정렬)
```
|제목|내용|설명|
|:-----|-----:|:-----:|
|왼쪽정렬|오른쪽정렬|중앙정렬|
|왼쪽정렬|오른쪽정렬|중앙정렬|
|왼쪽정렬|오른쪽정렬|중앙정렬|
```

|제목|내용|설명|
|:-----|-----:|:-----:|
|왼쪽정렬|오른쪽정렬|중앙정렬|
|왼쪽정렬|오른쪽정렬|중앙정렬|
|왼쪽정렬|오른쪽정렬|중앙정렬|

#### Extends cell width(셀 확장)
```
|제목|내용|설명|
|:-----|:-----:|-----:|
||중앙에서확장||
|||오른쪽에서 확장|
|왼쪽에서확장||
```

|제목|내용|설명|
|:-----|:-----:|-----:|
||중앙에서확장||
|||오른쪽에서 확장|
|왼쪽에서확장||


### Text color(글자색)

```html
<span style="color:COLOR"> COLOR </span>
```

<b>COLOR</b> should be written in <b>English</b> or <b>RGB</b> or <b>Hex</b>.<br>
(색깔은 영어 또는 rgba 또는 hex로 작성해야 한다.)

[Color Wheel Picker](https://rgbacolorpicker.com/color-wheel-picker) : If you click the color you want, you can know the value of color in hex, rgb(a), hsl.<br>
(원하는 색을 클릭하면 hex, rgb(a), hsl 값을 알려주는 사이트)


<span style="color:red"> red </span><br>

<span style="color:rgb(255,0,0)"> red(rgb(255,0,0)) </span><br>
<span style="color:#ff0000"> red(#ff0000) </span><br>
<span style="color:#ffd33d"> yellow </span><br>
<span style="color:blue"> blue </span><br>
<span style="color:brown"> brown </span><br>
<span style="color:orange"> orange </span><br>
<span style="color:green"> green </span><br>
<span style="color:violet"> violet </span><br>
<span style="color:yellowgreen"> yellowgreen </span><br>
<span style="color:blueviolet"> blueviolet </span><br>
<span style="color:gray"> gray</span><br>
<span style="color:indigo"> indigo </span><br>

<br>





