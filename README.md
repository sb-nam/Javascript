# JSP

## 이클립스에서 jsp
```
Help - Install New Software 선택
Work with에 http://oss.opensagres.fr/tern.repository/1.2.0/ url 넣기
Tern-Embed Node.js, Tern IDE, Tern Tooling 3개 박스 체크
Install
이클립스 재시작 후 프로젝트 오른쪽 클릭, Configure-Convert to Tern Project 선택
JavaScript-Tern-Modules 에서 Browser, CKEditor, jQuery 체크
```
## 데이터 타입
```
var 변수명; 또는 var 변수명 = 값;
데이터 타입: 문자형 String, 숫자형 Number, 논리형 Boolean, Null & Undefined 가 있다.

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

function myFnc(name,area) {
	document.write("안녕하세요. " + name +" 입니다.","<br>");
	document.write("사는 곳은 " + area + " 입니다.","<br><br>");
}

myFnc("홍당무","서울");
myFnc("닭찌찌","수원");
```
## 함수 이용하여 버튼클릭시 배경색 바꾸기
```
var color = [ "white", "yellow", "aqua", "purple" ];

	var i = 0;
	function changeColor() {
		i++;
		if (i >= color.length) {
			i = 0;
		}

	var bodyTag = document.getElementById("theBody");
	bodyTag.style.backgroundColor = color[i];
	}
	// document.getElementById("theBody").style.backgroundColor = color[i]; 이렇게도 대체 가능!
</script>

</head>
<body id="theBody">
<button onclick="changeColor()">배경색 바꾸기</button>
```

## 함수 이용하여 로그인 로직 짜보기
```
var rightId ="korea";
var rightPw ="1234";

function login(id,pw) {
	if(id == rightId) {
		if(pw == rightPw) {
			document.write(id + " 님 방문을 환영 합니다." );
		} else {
			document.write(" 잘못된 비밀번호 입니다. " );
		}
	} else {
		document.write("존재하지 않는 아이디 입니다." );
	}
} 

var userId = prompt("아이디를 입력하세요." , "");
var userPw = prompt("비밀번호를 입력하세요." , "");

login(userId,userPw);
```
## 매개변수 없이 함수에 전달된 값 가져오기
```
function sum() {
	var sum = arguments[0]+arguments[1]+arguments[2];
	document.write("sum");
}
sum(10,20,30);
```

## 데이터를 반환하고 강제 종료하는 return 문
```
function 함수명() {
	스크립트 코드1;    //2
	return 데이터(값);  //3
}
var 변수 = 함수명();   //1  함수 호출
```

## 함수 return 예제
```
function testAvg(arrData) {
	var sum=0;
	for(var i=0; i<arrData.length; i++) {
		sum += Number(prompt(arrData[i] + " 점수는?","0"));
	}
	
	var avg = sum / arrData.length;
	return avg;
}

var arrSubject = ["국어","수학"];
var result = testAvg(arrSubject);

document.write("평균 점수는 " + result + " 입니다.");
```

## 함수 이용하여 사진 갤러리 만들기
```
<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8">
<title>Insert title here</title>
<script type="text/javascript">
	var num = 1;
	function gallery(direct) {
		if (direct) {
			if (num == 8) {
				return;
			}
			num++;
		} else {
			if (num == 1) {
				return;
			}
			num--;
		}

		var imgTag = document.getElementById("photo");
		imgTag.setAttribute("src", "../images/pic_" + num + ".jpg");
	}
</script>
</head>
<body>
	<div id="galleryZone">
		<p>
			<img alt="" src="../images/pic_1.jpg" id="photo">
		</p>
		<p>
			<button onclick="gallery(0)">이전</button>
			<button onclick="gallery(1)">다음</button>
		</p>
	</div>
</body>
</html>
```
## 재귀함수
```
		var num = 0;
		function testFnc() {
			num++;
			document.write(num, "<br>");
			if (num == 10) {
				return;
			}
			testFnc();
		}

		testFnc();
```

## 객체 생성자 함수
```
function 함수명(매개변수1,매개변수2,....매개변수n) { //객체 생성자 함수
    this.속성명 = 새 값;
    this.함수명 = function() {
    	자바스크립트 코드;
    }
}

var 참조 변수(인스턴스 네임) = new 함수명();

var 참조 변수 = {
		속성 : 새 값, 함수명 : function () {     // 객체 생성
			
		}
}
```

## 객체 생성자 함수 예제
```

	<script type="text/javascript">
		function CheckWeight(name, height, weight) {
			this.userName = name;
			this.userHeight = height;
			this.userWeight = weight;
			this.minWeight;
			this.maxWeight;

			this.getInfo = function() {
				var str = "";
				str += "이름: " + this.userName + ", ";
				str += "키: " + this.userHeight + ", ";
				str += "몸무게: " + this.userWeight + "<br>";
				return str;
			}

			this.getResult = function() {
				this.minWeight = (this.userHeight - 100) * 0.9 - 5;
				this.maxWeight = (this.userHeight - 100) * 0.9 + 5;

				if (this.userWeight >= this.minWeight
						&& this.userWeight <= this.maxWeight) {
					return "정상 몸무게 입니다.";
				} else if (this.userWeight < this.minWeight) {
					return "정상 몸무게 보다 미달 입니다.";
				} else {
					return "정상 몸무게 보다 초과 입니다.";
				}
			}
		}

		var jang = new CheckWeight("장보리", 168, 62);
		var park = new CheckWeight("박달재", 176, 75);
	
		console.log(jang);
		console.log(park);
		
		document.write(jang.getInfo());
		document.write(jang.getResult());
```

## 문서를 동적으로 만드는 방법
```
<body>
	<ul>
		<li>first</li>
		<li>second</li>
		<li>third</li>
	</ul>
	<button onclick="setColor()">click</button>
	<script type="text/javascript">
		function setColor() {
			var li = document.querySelectorAll("li");
			for (var i = 0; i < li.length; i++) {
				li[i].style.color = "green";
				li[i].style.backgroundColor = "orange";
			}
		}
	</script>
</body>
```

## style 객체와 속성
```
<style type="text/css">
div {
	width: 600px;
	height: 400px;
	border: 1px solid;
}
</style>
</head>
<body>
	<div id="box">색상 바꾸기</div>
	<button onClick="setColor()">click</button>
	<script>
		function setColor() {
			var box = document.getElementById("box");
			box.style.color="white";
			box.style.backgroundColor="orange";
		}
	</script>
</body>
```

## 속성 조작
```
<style type="text/css">
#box {
	width: 100px;
	height: 100px;
	border: 3px solid black;
}
.box {
    background: orange;
}
</style>
</head>
<body>
	<div id="box" onClick="changeColor()">HelloBox</div>
	<button onClick="changeColor()">click</button>
	<script>
		function changeColor() {
			var box = document.getElementById("box");
			box.setAttribute("class","box"); // class="box"; 랑 같다.
			
		}
	</script>
</body>
```

## 인라인 이벤트

```
<body>
<a href="http://www.google.com" onclick="alert('구글로 이동')">구글</a>
</body>
```

## 이벤트 핸들러

```
<body>
	<button id="btn">click</button>
	<script>
		var btn=document.getElementById("btn");
		btn.onclick=function() {
			alert("event 1");
		}
		btn.onclick=function() {
			alert("event 2");   // 이벤트 핸들러는 내용 변경이기 때문에 event 2만 동작한다.
		}
	</script>
</body>

```

## 이벤트 리스너

```
<body>
	<button id="btn">click</button>
	<script>
		var btn=document.getElementById("btn");
		btn.addEventListener("click",function() {
			alert("event 1");
		});
		btn.addEventListener("click",function() {     // 이벤트 리스너는 두 이벤트가 순차적으로 실행된다.
			alert("event 2");
		});
	</script>
</body>
```

## 이벤트 리스너

```
<style type="text/css">
#box {
	width: 100px;
	height: 100px;
	border: 3px solid black;
}

#box.hover { // id가 box 이면서 class가 hover인것
	background: orange;
	color: white;
}
</style>
</head>
<body>
	<button id="box">
		<p>마우스를 올려주세요</p>
	</button>
	<script>
		var box = document.getElementById("box");
		box.addEventListener("mouseover", function() {
			box.setAttribute("class", "hover");   // class="hover";
		});
		box.addEventListener("mouseout", function() {
			box.removeAttribute("class");
		});
	</script>
</body>
```


