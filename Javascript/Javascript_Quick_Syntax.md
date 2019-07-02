# 1. Javascript tóm tắt cú pháp

- [1. Javascript tóm tắt cú pháp](#1-Javascript-t%C3%B3m-t%E1%BA%AFt-c%C3%BA-ph%C3%A1p)
	- [1.1. FILE TYPE](#11-FILE-TYPE)
	- [1.2. HELLO WORLD](#12-HELLO-WORLD)
	- [1.3. COMMENT](#13-COMMENT)
	- [1.4. VARIABLE](#14-VARIABLE)
		- [1.4.1. _Declare Variable](#141-Declare-Variable)
		- [1.4.2. _Assign Variable](#142-Assign-Variable)
		- [1.4.3. _Constant/ final](#143-Constant-final)
		- [1.4.4. _Check Variable Type](#144-Check-Variable-Type)
	- [1.5. OBJECT](#15-OBJECT)
		- [1.5.1. _Create Object](#151-Create-Object)
		- [1.5.2. _Add new properties](#152-Add-new-properties)
		- [1.5.3. _Object Constructor - tạo cấu trúc Object - like Class](#153-Object-Constructor---t%E1%BA%A1o-c%E1%BA%A5u-tr%C3%BAc-Object---like-Class)
		- [1.5.4. _Add Reference, method - thêm thuộc tính, phương thức](#154-Add-Reference-method---th%C3%AAm-thu%E1%BB%99c-t%C3%ADnh-ph%C6%B0%C6%A1ng-th%E1%BB%A9c)
		- [1.5.5. _Declare Object](#155-Declare-Object)
		- [1.5.6. _Kế thừa](#156-K%E1%BA%BF-th%E1%BB%ABa)
		- [1.5.7. _Check Instance - kiểm tra Kiểu dữ liệu](#157-Check-Instance---ki%E1%BB%83m-tra-Ki%E1%BB%83u-d%E1%BB%AF-li%E1%BB%87u)
		- [1.5.8. _Pass by reference, thay đổi thuộc tính qua reference ra khỏi method](#158-Pass-by-reference-thay-%C4%91%E1%BB%95i-thu%E1%BB%99c-t%C3%ADnh-qua-reference-ra-kh%E1%BB%8Fi-method)
	- [1.6. ENUM](#16-ENUM)
	- [1.7. OPERATOR](#17-OPERATOR)
		- [1.7.1. _Bitwise Operators](#171-Bitwise-Operators)
	- [1.8. STRING](#18-STRING)
	- [1.9. ARRAY](#19-ARRAY)
		- [1.9.1. _Declare](#191-Declare)
		- [1.9.2. _Get Item + Functions](#192-Get-Item--Functions)
	- [1.10. DATE](#110-DATE)
		- [1.10.1. _Format Time](#1101-Format-Time)
		- [1.10.2. _Declare date](#1102-Declare-date)
		- [1.10.3. _Date Method](#1103-Date-Method)
	- [1.11. CONDITIONAL](#111-CONDITIONAL)
		- [1.11.1. _If](#1111-If)
		- [1.11.2. _Switch](#1112-Switch)
	- [1.12. LOOP](#112-LOOP)
		- [1.12.1. _For](#1121-For)
		- [1.12.2. _While](#1122-While)
		- [1.12.3. _Break](#1123-Break)
		- [1.12.4. _Continue](#1124-Continue)
	- [1.13. LABLE](#113-LABLE)
	- [1.14. METHOD/ FUNCTION](#114-METHOD-FUNCTION)
		- [1.14.1. _Define Method](#1141-Define-Method)
		- [1.14.2. _Call Method](#1142-Call-Method)
		- [1.14.3. _Parameter on Method](#1143-Parameter-on-Method)
		- [1.14.4. _Return method](#1144-Return-method)
		- [1.14.5. _Constructor Method](#1145-Constructor-Method)
	- [1.15. PACKAGE/ NAMESPACE](#115-PACKAGE-NAMESPACE)
	- [1.16. IMPORT](#116-IMPORT)
	- [1.17. EXCEPTION](#117-EXCEPTION)
	- [1.18. MATH - toán học](#118-MATH---to%C3%A1n-h%E1%BB%8Dc)
	- [1.19. REGEXP - Regular expression](#119-REGEXP---Regular-expression)
	- [1.20. DOM Document Object Model - ảnh hưởng html tag](#120-DOM-Document-Object-Model---%E1%BA%A3nh-h%C6%B0%E1%BB%9Fng-html-tag)
		- [1.20.1. _Lưu ý DOM](#1201-L%C6%B0u-%C3%BD-DOM)
	- [1.21. FORM VALIDATION - KT NHẬP LIỆU](#121-FORM-VALIDATION---KT-NH%E1%BA%ACP-LI%E1%BB%86U)
		- [1.21.1. _form tag](#1211-form-tag)
		- [1.21.2. _check on js](#1212-check-on-js)
	- [1.22. COOKIES](#122-COOKIES)
		- [1.22.1. _Storing/change Cookies](#1221-Storingchange-Cookies)
		- [1.22.2. _Read cookie](#1222-Read-cookie)
		- [1.22.3. _Delete cookie](#1223-Delete-cookie)
		- [1.22.4. _Some Functions](#1224-Some-Functions)
	- [1.23. PAGE REDIRECT - điều hướng trang](#123-PAGE-REDIRECT---%C4%91i%E1%BB%81u-h%C6%B0%E1%BB%9Bng-trang)
		- [1.23.1. _Refresh Page](#1231-Refresh-Page)
	- [1.24. DIALOG BOX](#124-DIALOG-BOX)
	- [1.25. VOID - Gọi 1 biểu thức, hàm và trả về undefine](#125-VOID---G%E1%BB%8Di-1-bi%E1%BB%83u-th%E1%BB%A9c-h%C3%A0m-v%C3%A0-tr%E1%BA%A3-v%E1%BB%81-undefine)
	- [1.26. AJAX - LẤY DỮ LIỆU KO CẦN LOAD PAGE](#126-AJAX---L%E1%BA%A4Y-D%E1%BB%AE-LI%E1%BB%86U-KO-C%E1%BA%A6N-LOAD-PAGE)
	- [1.27. Một số hàm cần thiết](#127-M%E1%BB%99t-s%E1%BB%91-h%C3%A0m-c%E1%BA%A7n-thi%E1%BA%BFt)

## 1.1. FILE TYPE

*.js *.html

## 1.2. HELLO WORLD

```html
<!-- Script tag đặt trong Head or Body tag --!>
<html>
<head>
    <script language="javascript" type="text/javascript">
    //enter script here
    alert("Hello World!");
    </script>
</head>
<body>
    <script>//or script here
    </script>
</body>
</html>

//Gọi file js vào trong html
<script src ='/js/myScript.js' />
```

## 1.3. COMMENT

```js
// Single Line comment
/*
* Multiline comment
*/
```

## 1.4. VARIABLE

Number
String
Boolean

### 1.4.1. _Declare Variable

```js
var name, age, right; //=undefined
var name = "nghia"; //String type
var age = 30.4; //Number type
var right = true; //Boolean type
```

### 1.4.2. _Assign Variable

```js
name = "nghia";
```

### 1.4.3. _Constant/ final

```js
const age = 30; //can not change value
let name; ... if (){ let name; } //like var, but 2nd name difrence 1st name, js Es6
```

### 1.4.4. _Check Variable Type

```js
typeof num == "number"
```

## 1.5. OBJECT

- Aggregation. Tính thu nạp.
- Abstraction (Tính trừu tượng). Ko có.
- Encapsulation (Tính bao đóng)
- Inheritance (Tính kế thừa)
- Polymophirsm (Tính đa hình)

### 1.5.1. _Create Object

```js
var batman = {
	name: "Nghia",
	sayHi: function() { 
		return "Hello " + this.name; 
	},
	address: {
		street: "71 Phú Định",
	}
};

// Using:
console.log(batman.sayHi());
console.log(batman.abc);
```

### 1.5.2. _Add new properties

```js
batman.abc = "Iabcde" ;
```

### 1.5.3. _Object Constructor - tạo cấu trúc Object - like Class

```js
function Person (name, street) {
	this.name = name;
	this.street = street;
	this.sayHi = function () {
		return "Hi " + this.name;
	}
}
```

### 1.5.4. _Add Reference, method - thêm thuộc tính, phương thức

```js
Person.prototype.sayGRR = function(){
    return "GRR" + this.name;
}
```

### 1.5.5. _Declare Object

```js
var batman = new Person("Batman", "12 GodHam");
console.log(batman.sayHi()); //_Using
```

### 1.5.6. _Kế thừa

```js
// Đối tượng User thừa kế tất cả các phương thức, thuộc tính của đối tượng Person
function User(name) { this.name = name; }; //Tạo cấu trúc cho đối tượng User
User.prototype = new Person();
```

### 1.5.7. _Check Instance - kiểm tra Kiểu dữ liệu

```js
console.log(batman instanceof Person);
```

### 1.5.8. _Pass by reference, thay đổi thuộc tính qua reference ra khỏi method

```js
function changeName (person) { person.name = "new name"; }
changeName(batman);
console.log(batman.name);
```

## 1.6. ENUM

```js
var sizes = {
	SMALL: 1 ,
	MEDIUM: 2 ,
	LARGE: 3 ,
};

sizes.SMALL //Call using
```

## 1.7. OPERATOR

```js
+ - * / %(modulus)
= += -= *= /= %=
++ --
!= > < >= <=

== //(So sánh cùng giá trị, "0"==0 -> true)
=== //(So sánh cùng loại+cùng giá trị, "0"===0 -> false, khuyên dùng)

&&(And) ||(or) !(not)

Condition ? True_value : false_value
```

### 1.7.1. _Bitwise Operators

```js
&(And) |(or) ^(XOR) ~(not) >>(right shift) <<(left shift) >>>(right shift with zero)
```

## 1.8. STRING

```js
var str = "nghia";
var str = new String("nghia"); //Object type
.length //độ dài
//Lấy vị trí
.indexOf("ng") //vị trí đầu của chuỗi ng
.indexOf("ng", startPos) //vị trí của chuỗi,bắt đầu từ vị trí
.lastIndexOf("ng") //vị trí cuối cùng của chuỗi
.search("ng") //vị trí của chuỗi, regular expression
//Cắt chuỗi
.slice(start, end)
.slice(- start, - end) //trừ ngược cuối chuỗi đếm lên
.substring(start, end)
.substr(start, length)
//Đổi chuỗi
.replace( "ab" , "cc" ); //thay ab thành c
.toUpperCase()
.toLowerCase()
.concat("str2", "str3") //nối nhiều chuỗi
//Lấy chuỗi
.charAt(4) // lấy chuỗi ở vị trí 4, đề nghị dùng
str[4] //lấy chuỗi vị trí 4
.charCodeAt(0) //số của chuỗi ở vị trí 0
.split( "," ) //tách chuỗi thành Mảng, cách ","
.match("regularString") //kt đúng với Regular expression
```

## 1.9. ARRAY

### 1.9.1. _Declare

```js
var fruits = [];
var fruits = new Array( "apple", "orange");
var fruits = [ "apple", "orange" ];
```

### 1.9.2. _Get Item + Functions

```js
fruits[2] //get item at index 2

.push( "new Item" ) //thêm item
.pop() //xoá phần tử cuối
.shift() //xoá phần tử đầu
.unshift("newItem") //xoá phần tử, thêm mới ở đầu
.splice(position_add, num_element_remove, newItem1, newItem2, ...) //Xoá 1 số item, tại vị trí, thêm 1 số item mới
.concat(array2, array3) //nối chuỗi
.length //chiêù dài chuỗi
.sort() //xắp mảng theo abc
.reverse() //đảo ngược mảng
```

## 1.10. DATE

### 1.10.1. _Format Time

- ISO Date: "2015-03-25" (The International Standard)
- Short Date: "03/25/2015"
- Long Date: "Mar 25 2015" or "25 Mar 2015"
- Full Date: "Wednesday March 25 2015"

### 1.10.2. _Declare date

```js
var d = new Date("2015-03-25");
var d = new Date("2015-03");
var d = new Date("2015" ;
var d = new Date("2015-03-25T12:00:00Z"); //YYYY-MM-DDTHH:MM:SSZ
var d = new Date("2015-03-25T12:00:00-06:30");
var d = new Date("03/25/2015");
var d = new Date("Mar 25 2015");
var d = new Date("25 Mar 2015");
var d = new Date("January 25 2015");
var d = new Date("Wed Mar 25 2015 09:56:24 GMT+0100 (W. Europe Standard Time)");
var d = new Date(milisecond);
```

### 1.10.3. _Date Method

```js
//UTC ((Universal Time Zone dates) add getUTCDate()...
getDate() //Get the day as a number (1-31)
getDay() //Get the weekday as a number (0-6)
getFullYear() //Get the four digit year (yyyy)
getHours() //Get the hour (0-23)
getMilliseconds() //Get the milliseconds (0-999)
getMinutes() //Get the minutes (0-59)
getMonth() //Get the month (0-11)
getSeconds() //Get the seconds (0-59)
getTime() //Get the time (milliseconds since January 1, 1970)
var msec = Date.parse( "March 21, 2012" ); //get minisecond between date and 1/1970
var msecs = Date.UTC(2008,9,6);
```

## 1.11. CONDITIONAL

### 1.11.1. _If

```js
if (num <= 1) {
	//Do somethings;
} else if (num <= 2) {
	//Do somethings;
} else {
	//Do somethings;
}
```

### 1.11.2. _Switch

```js
switch (num) {
	case 0: //do somethings
	break;
	case 0: //do somethings
	break;
	default: //do somethings
}
```

## 1.12. LOOP

### 1.12.1. _For

```js
for (var i=0; i<=10; i++) {
	console.log(i);
}
for (var i in enum1) {
	console.log(i);
}
```

### 1.12.2. _While

```js
while (num >= 1){
	console.log(num);
	num--;
}
do {
	console.log(num);
	num--;
} while (num>=1)
```

### 1.12.3. _Break

break; //break out of loop, exit loop

### 1.12.4. _Continue

continue; //continue at next loop condition

## 1.13. LABLE

```js
lableName : //define lable
...
lableName; //return lable before, do it again
```

## 1.14. METHOD/ FUNCTION

### 1.14.1. _Define Method

```js
function myFun() { ... }
```

### 1.14.2. _Call Method

```js
<input type="button" onclick="myFun()" value="Say Hello">
// or
myFun();
```

### 1.14.3. _Parameter on Method

```js
function sayHello (name, age) {
	document.write ("Hello " + name + age);
}
sayHello("nghia", 30); // call - using, log: Hello nghia30
```

### 1.14.4. _Return method

```js
function sayHello (name, age) {
	return "Hello " + name + age;
}

var hello = sayHello("nghia", 30); //call - using
```

### 1.14.5. _Constructor Method

```js
var sum = Function("a", "b", "return a+b");
var sum = function(a, b){ return a+b; };
document.write(sum(2,3)); //call, =2+3=5
```

## 1.15. PACKAGE/ NAMESPACE

## 1.16. IMPORT

## 1.17. EXCEPTION

```js
try{
  throw( "Divide by zero error." ); 
} catch(ex) {...} finally {...}
```

## 1.18. MATH - toán học

```js
//Properties
.E //Euler's constant and the base of natural logarithms, approximately 2.718.
.LN2 //Natural logarithm of 2, approximately 0.693.
.LN10 //Natural logarithm of 10, approximately 2.302.
.LOG2E //Base 2 logarithm of E, approximately 1.442.
.LOG10E //Base 10 logarithm of E, approximately 0.434.
.PI //Ratio of the circumference of a circle to its diameter, approximately 3.14159.
.SQRT1_2 //Square root of 1/2; equivalently, 1 over the square root of 2, approximately 0.707.
.SQRT2 //Square root of 2, approximately 1.414.
//_Method
abs() Returns the absolute value of a number.
acos() Returns the arccosine (in radians) of a number.
asin() Returns the arcsine (in radians) of a number.
atan() Returns the arctangent (in radians) of a number.
atan2() Returns the arctangent of the quotient of its arguments.
ceil() Returns the smallest integer greater than or equal to a number.
cos() Returns the cosine of a number.
exp() Returns EN, where N is the argument, and E is Euler's constant, the base of the natural logarithm.
floor() Returns the largest integer less than or equal to a number.
log() Returns the natural logarithm (base E) of a number.
max() Returns the largest of zero or more numbers.
min() Returns the smallest of zero or more numbers.
pow() Returns base to the exponent power, that is, base exponent.
random() Returns a pseudo-random number between 0 and 1.
round() Returns the value of a number rounded to the nearest integer.
sin() Returns the sine of a number.
sqrt() Returns the square root of a number.
tan() Returns the tangent of a number.
toSource() Returns the string "Math".
```

## 1.19. REGEXP - Regular expression

```js
var pattern = /pattern/modifiers; //ex: /[0-9]*/g
var pattern = new RegExp( "/[0-9]*/", modifiers);
//modifiers = i: case-insensitive, ko phân biệt hoa thường. m: so khớp toàn bộ chuỗi. g: so khớp luôn xuống dòng.

// Check văn bản đúng kiểu
/[0-9]*/.test("nghia")
pattern
.test("nghia) //Tests for a match in a string. Returns true or false
.exec("nghia") // Tests for a match in a string. Returns the first match
```

## 1.20. DOM Document Object Model - ảnh hưởng html tag

```js
var tag = document.getElementById("id_name");
var tag = document.getElementsByName("name");
var tagList = document.getElementsByTagName("H1"); //Change html Attributes.

// Change Html content.
tag.innerHTML = "Hello JavaScript" ;
//Change html Attributes.
tagList[0].setAttribute("class", "democlass");
//remove attributes.
tag.removeAttribute("class");

//change style of element
tag.style.backgroundColor = "red";
```

### 1.20.1. _Lưu ý DOM

```js
//Js trong tag Header, muốn tìm thấy tag html phải đặt trong sự kiện onload. Đợi page load xong.
window.onload = function(){
    //here
}
```

## 1.21. FORM VALIDATION - KT NHẬP LIỆU

### 1.21.1. _form tag

```html
<form action="/cgi-bin/test.cgi" name="myForm" onsubmit="return(validate());">...
    <input type="submit" value="Submit" />
</form>
```

### 1.21.2. _check on js

```js
//Check null
if( document.myForm.Name.value == "" ){
		alert( "Please provide your name!" );
		document.myForm.Name.focus() ;
		return false;
}

//Check Email
function validateEmail() {
	var emailID = document.myForm.EMail.value;
	atpos = emailID.indexOf("@");
	dotpos = emailID.lastIndexOf(".");
	if (atpos < 1 || ( dotpos - atpos < 2 ))
	{
		alert("Please enter correct email ID");
		document.myForm.EMail.focus() ;
		return false;
	}
	return( true );
}
```

## 1.22. COOKIES

Save data on the Browser, like: user's session, preference, purchases, commission...

### 1.22.1. _Storing/change Cookies

```js
document.cookie = "key1=value1;key2=value2;expires=date";
document.cookie = "username=John Doe; expires=Thu, 18 Dec 2013 12:00:00 UTC; path=/";
```

### 1.22.2. _Read cookie

```js
var x = document.cookie;
```

### 1.22.3. _Delete cookie

```js
// Don't set value, expires is pass date
document.cookie = "username=; expires=Thu, 01 Jan 1970 00:00:00 UTC; path=/;" ;
```

### 1.22.4. _Some Functions

```js
function setCookie(cname, cvalue, exdays) {
	var d = new Date();
	d.setTime(d.getTime() + (exdays* 24* 60* 60* 1000));
	var expires = "expires=" + d.toUTCString();
	document.cookie = cname +
	"=" + cvalue + ";" + expires + ";path=/" ;
}

function getCookie(cname) {
	var name = cname + "=" ;
	var decodedCookie = decodeURIComponent(document.cookie);
	var ca = decodedCookie.split( ';' );
	for ( var i = 0 ; i <ca.length; i++) {
		var c = ca[i];
		while (c.charAt( 0 ) == ' ' ) {
			c = c.substring( 1 );
		}
		if (c.indexOf(name) == 0 ) {
			return c.substring(name.length, c.length);
		}
	}
	return "";
}
```

## 1.23. PAGE REDIRECT - điều hướng trang

### 1.23.1. _Refresh Page

```js
<a href="javascript:location.reload(true)">Refresh Page</a>

//Tự load lại sau 5000ms=5s, đặt trong <body onload="JavaScript:...">
setTimeout("location.reload(true);", 5000);

//Chuyển đến 1 trang khác
window.location="http://www.google.com";
```

## 1.24. DIALOG BOX

```js
alert("dialog with Ok button");

//Confirm dialog, return boolean
var cf = confirm("ok or cancel");

//Get text Dialog
var name = prompt("Get Name", "Your name is here");
```

## 1.25. VOID - Gọi 1 biểu thức, hàm và trả về undefine

```js
//Gọi đường dẫn trong javascript. Trả về Indefine.
<a href="javascript:void(0)">Click me!</a>
javascript:void func()
void(func())
javascript:void(func())
```

## 1.26. AJAX - LẤY DỮ LIỆU KO CẦN LOAD PAGE

```js
function loadDoc() {
    var xhttp = new XMLHttpRequest();
    xhttp.onreadystatechange=function() {
        //kết nối thành công
        if(this.readyState == 4 && this.status == 200) {
            //lấy dữ liệu trả về
            document.getElementById("demo").innerHTML=this.responseText;
        }
    };
    //mở kết nối, lấy data từ server
    //Cấu hình GET
    xhttp.open("GET","description.php?data=true",true);
    xhttp.send();

    //Câú hình POST
    xhttp.setRequestHeader('Content-Type', 
        'application/x-www-form-urlencoded'); 
    xhttp.send('data=true'); //gởi request
}

//Using
<div id="demo">
    <h2>Let AJAX change this text</h2>
    <button type="button" onclick="loadDoc()">Change Content</button>
</div>
```

## 1.27. Một số hàm cần thiết

```js
document.write("nghia") //write on page.
console.log("nghia"); //ghi console.
window.print(); //print current page
undefined. NaN-not a number. Infinity- (ex: 2/0)
"20"+"20"=40
```

