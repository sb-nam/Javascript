# JSP

## 데이터 타입
```
var 변수명; 또는 var 변수명 = 값;
데이터 타입: 문자형 String, 숫자형 Number, 논리형 Boolean, Null & Undefined 가 있다.


<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8">
<title>Insert title here</title>
</head>
<body>
	<script type="text/javascript" src="../JSP/b.js">
		var t1 = "학교종이"
		var t2 = "땡땡땡"
		var t3 = "8282"
		var t4 = "어서모이자"
		var result;
		
		result = t1+t2+t3+t4;
		document.write(result);
	</script>
</body>
</html>

var a = true;
var b = false;
var c = 10 > 5;
var d = Boolean(null);

document.write(a, "<br>");
document.write(b, "<br>");
document.write(c, "<br>");
document.write(d, "<br>");

var num = 100;
var str = "자바스크립트";

document.write(typeof num, "<br>");
document.write(typeof str);
```
## 비교 연산자
```
var a = 10, b = "10";
a == 10; //true
b == 10; //true

var a = 10, b = "10";
a === 10; //true
b === 10; //false

===이 붙을때는 데이터 타입 까지 비교한다.
!==은 부정의 의미
```

## 3항 연산자

```
<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8">
<title>Insert title here</title>
</head>
<body>
<script type="text/javascript">
var name = prompt("당신의 이름은?", "");
var height = prompt("당신의 키는?", "0");
var weight = prompt("당신의 몸무게는?", "0");

var normal_W = (height - 100) * 0.9;
var result = weight >=normal_W -5 && weight <= normal_W +5;
result = result ? "적정 체중 입니다.":"적정 체중이 아닙니다.";
document.write(name+ " 님은 " + result);
</script>
</body>
</html>
```

## 짝수열 색 넣고 table 만들기
```
<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8">
<title>Insert title here</title>
<style>
table {
    border: 1px solid black;
	border-collapse: collapse;
}

tr, td {
    border: 1px solid black;
}

tr:nth-child(2n) {
    background-color: yellow;
}
</style>
</head>
<body>
<script type="text/javascript">
var hang = prompt("행 입력", "0");
var yull = prompt("열 입력", "0");

document.write("<table>");
for(var i=1; i<=hang; i++) {
	
	document.write("<tr>");
	for(var j=1; j<=yull; j++) {
		
		document.write("<td>");
		document.write(i+"행"+j+"열");
		document.write("</td>");
	}
	
	document.write("</tr>");
}
document.write("</table>");
</script>
</body>
</html>
```
## table로 묶어서 항목 만들기
```
<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8">
<title>Insert title here</title>
<style>
table {
	border-collapse: collapse;
}
tr,td,th {
    border: 1px solid black;
}
</style>
</head>
<body>
	<table>
		<tr>
			<th>번호</th>
			<th>내용</th>
			<th>비고</th>
		</tr>
		<script type="text/javascript">
		var control = prompt("자료건수 입력", "0");

		for (var i = 1; i <= control; i++) {
			document.write("<tr>");
			document.write("<td>" + i + "</td>");
			document.write("<td>" + i + "번째 입력 내용" + "</td>");
			document.write("<td></td>");
			document.write("</tr>");
		}
	</script>
	</table>
</body>
</html>
```
