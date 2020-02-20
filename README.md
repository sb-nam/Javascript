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

## 내장 객체 생성하기
** 참조 변수(인스턴스 이름) = new 생성 함수();
```
<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8">
<title>Insert title here</title>
</head>
<body>
	<script type="text/javascript">
		var tv = new Object();                      // 1번 방식
		tv.color = "white";
		tv.price = "300000";
		tv.info = function() {
			document.write("tv 색상: " + this.color, "<br>");
			document.write("tv 가격: " + this.price, "<br>");
		}

		var car = {                                //2번 
			color : "black",
			price : 5000000,
			info : function() {
				document.write("car 색상: " + this.color, "<br>");
				document.write("car 색상: " + this.price, "<br>");
			}
		};
		
		document.write("<h1>tv 객체 메서드 호출</h1>");
		tv.info();
		document.write("<h1>car 객체 메서드 호출</h1>");
		car.info();
	</script>
</body>
</html>
```
## 날짜

```
<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8">
<title>Insert title here</title>
</head>
<body>
	<script type="text/javascript">
		var today = new Date();
		var nowMonth = today.getMonth(), 
		nowDate = today.getDate(),
		nowDay = today.getDay();

		document.write("<h1>오늘 날짜 정보</h1>");
		document.write("현재 월: " + nowMonth, "<br>");
		document.write("현재 일: " + nowDate, "<br>");
		document.write("현재 요일: " + nowDay, "<br>");

		var worldcup = new Date(2002, 4, 31);
		var theMonth = worldcup.getMonth(), theDate = worldcup.getDate(), theDay = worldcup
				.getDay();

		document.write("<h1>월드컵 날짜 정보</h1>");
		document.write("2002월드컵 몇 월: " + theMonth, "<br>");
		document.write("2002월드컵 몇 일: " + theDate, "<br>");
		document.write("2002월드컵 몇 요일: " + theDay, "<br>");
	</script>
</body>
</html>
```

## 현재 부터 지정 날짜 남은 일수 구하기
```
<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8">
<title>Insert title here</title>
</head>
<body>
	<script type="text/javascript">
		var today = new Date();
		var nowYear = today.getFullYear();

		var theDate = new Date(nowYear, 4, 22);
		var diffDate = theDate.getTime() - today.getTime();
		var result = Math.ceil(diffDate / (60 * 1000 * 60 * 24));
		document.write("수료 D-day: " + result + "일 남았습니다.");
	</script>
</body>
</html>
```

## 배열

```
<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8">
<title>Insert title here</title>
</head>
<body>
<script type="text/javascript">
var arr = [30, "따르릉", true];

document.write("<h3>배열값 가져오기-1</h3>");
document.write(arr[0],"<br>");
document.write(arr[1],"<br>");
document.write(arr[2],"<br>");

document.write("<h3>배열값 가져오기-2</h3>");
for(var i=0; i<arr.length; i++) {
	document.write(arr[i],"<br>");
}

document.write("<h3>배열값 가져오기-3</h3>");
for(i in arr) {
	document.write(arr[i],"<br>");
}
</script>
</body>
</html>
```

## 배열2

```
<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8">
<title>Insert title here</title>
</head>
<body>
<script type="text/javascript">
var arr_1 = ["사당","교대","방배","강남"];
var arr_2 = ["신사", "압구정", "옥수"];

var result = arr_1.join("-"); // 배열 객체 연결
console.log(result);

result = arr_1.concat(arr_2); // 2개의 배열을 1개로 결합
console.log(result);

result = arr_1.slice(1,3);  // 인덱스 구간만큼 잘라서 가져옴
console.log(result);

arr_1.sort();               // 오름차순 정렬
console.log(arr_1);

arr_2.reverse();            // 데이터 선수 거꾸로 변경
console.log(arr_2);
</script>
</body>
</html>
```

## 배열3

```
<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8">
<title>Insert title here</title>
</head>
<body>
<script type="text/javascript">
var greenArr = ["교대","방배","강남"];
var yellowArr = ["미금","정자","수서"];

greenArr.splice(2,1,"서초","역삼"); // 2번 인덱스 부터 1개의 데이터 삭제, 그다음 "서초","역삼" 삽입
console.log(greenArr);

var data1 = yellowArr.pop(); // 배열 마지막 인덱스의 데이터를 data1에 저장
var data2 = yellowArr.shift(); // 배열 가장 앞쪽 인덱스의 데이터를 data2에 저장

yellowArr.push(data2);    // data2에 저장된 데이터를
console.log(yellowArr);   //  yellowArr 배열의 마지막 인덱스에 밀어 넣는다.

yellowArr.unshift(data1); // data1에 저장된 데이터를
console.log(yellowArr);   // yellowArr 배열의 가장 앞 인덱스에 밀어 넣는다.
</script>
</body>
</html>
```
## 배열을 이용한 알고리즘
```
<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8">
<title>Insert title here</title>
</head>
<body>
	<script type="text/javascript">
		var userEmail = prompt("당신의 이메일 주소는?", "");
		var	arrUrl = [ ".co.kr", ".com", ".net", ".or.kr", ".go.kr" ];

		var check1 = false;
		var check2 = false;

		if (userEmail.indexOf("@") > 0) {
			check1 = true;
		}

		for (var i = 0; i < arrUrl.length; i++) {
			if (userEmail.indexOf(arrUrl[i]) > 0) {
				check2 = true;
			}
		}

		if (check1 && check2) {
			document.write(userEmail);

		} else {
			alert("이메일 형식이 잘못 되었습니다.");
		}
	</script>
</body>
</html>
```
## 함수
```
기본형 - function name() {
	자바스크립트 코드;
}

참조 변수 = function () {
	자바스크립트 코드;
}
```
## 함수 예제
```
<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8">
<title>Insert title here</title>
</head>
<body>
	<script type="text/javascript">
		var addNum = 0;
		var subNum = 1000;

		var auto_1 = setInterval(function() {
			addNum++;
			console.log("addNum :" + addNum);
		}, 3000);

		var auto_2 = setInterval(function() {
			subNum--;
			console.log("subNum :" + subNum);
		}, 3000);
	</script>

	<button onclick="clearInterval(auto_1)">증가 정지</button>
	<button onclick="clearInterval(auto_2)">감소 정지</button>
</body>
</html>
```

## 함수 예제2
```
var count = 0;
myFnc();
function myFnc() {
    count++;
    document.write("hello" + count, "<br>");
}

myFnc();
var theFnc = function() {
	count++;
	document.write("bye" + count, "<br>");
}
theFnc();
```
