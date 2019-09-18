# 1. Kotlin 1.1 Cú pháp nhanh

- [1. Kotlin 1.1 Cú pháp nhanh](#1-kotlin-11-c%c3%ba-ph%c3%a1p-nhanh)
  - [1.1. File type](#11-file-type)
  - [1.2. HELLO WORLD](#12-hello-world)
  - [1.3. COMMENT](#13-comment)
  - [1.4. VARIABLE](#14-variable)
    - [1.4.1. số kiểu](#141-s%e1%bb%91-ki%e1%bb%83u)
    - [1.4.2. String](#142-string)
  - [1.5. Array - List](#15-array---list)
    - [1.5.1. Khởi tạo](#151-kh%e1%bb%9fi-t%e1%ba%a1o)
    - [1.5.2. Gán dữ liệu](#152-g%c3%a1n-d%e1%bb%af-li%e1%bb%87u)
    - [1.5.3. Phương thức](#153-ph%c6%b0%c6%a1ng-th%e1%bb%a9c)
    - [1.5.4. lambda expression](#154-lambda-expression)
    - [1.5.5. Đặc biệt](#155-%c4%90%e1%ba%b7c-bi%e1%bb%87t)
  - [1.6. OPERATOR](#16-operator)
  - [1.7. CONDITIONAL - if, when, try, break](#17-conditional---if-when-try-break)
  - [1.8. LOOP - Vòng lặp - for, while](#18-loop---v%c3%b2ng-l%e1%ba%b7p---for-while)
  - [1.9. FUNCTION - Hàm](#19-function---h%c3%a0m)
  - [1.10. CLASS - Lớp](#110-class---l%e1%bb%9bp)
    - [1.10.1. interface](#1101-interface)
    - [1.10.2. Lớp trừu tượng](#1102-l%e1%bb%9bp-tr%e1%bb%abu-t%c6%b0%e1%bb%a3ng)
    - [1.10.3. Override - Kế thừa](#1103-override---k%e1%ba%bf-th%e1%bb%aba)
    - [1.10.4. Call in Class](#1104-call-in-class)
    - [1.10.5. Generic - T type](#1105-generic---t-type)
    - [1.10.6. Enum](#1106-enum)
    - [1.10.7. Khác](#1107-kh%c3%a1c)
  - [1.11. PACKAGE](#111-package)
  - [1.12. Special](#112-special)
    - [1.12.1. Gọi đa phưong thức khởi tạo](#1121-g%e1%bb%8di-%c4%91a-ph%c6%b0ong-th%e1%bb%a9c-kh%e1%bb%9fi-t%e1%ba%a1o)
    - [Scope Functions (hàm phạm vi trong 1 biến): let, also, apply, with](#scope-functions-h%c3%a0m-ph%e1%ba%a1m-vi-trong-1-bi%e1%ba%bfn-let-also-apply-with)
    - [1.12.2. Coroutines, like thread](#1122-coroutines-like-thread)

## 1.1. File type

*.kt

## 1.2. HELLO WORLD

```js
pakage demo

fun main(args: Array<String>){
    println("Hello world!")
}
```

## 1.3. COMMENT

```js
// In line Comment
/* Mutilple comment */
```

## 1.4. VARIABLE

```js
var a : String  // = null
var age = 30
val PI : Int = 3.14    //constant
val bigInt = Int.MAX_VALUE
if (age is Int){}    // so sánh kiểu

public
private
protected //=private, visible in subclass
internal // visible inside the same module
```

### 1.4.1. số kiểu

```js
// Số nguyên
1 byte = 8 bit = 2^7
Byte (1byte) Short (2byte)
Int (4byte) Long (8byte)

// Số thực
Float (4byte) Double (8byte)

Boolean / Char
?Int, ?String, ?Boolean… // null variable
```

### 1.4.2. String

```js
// Khởi tạo
var name : String = "Nghia"

// Phương thức
name.length
name.get(2)    //get char 2nd
name[2]
name.equals("Nghia")
name.subSequence(2,8)    //get from 2 to 7
name.contains("a")
name.replace("a", "b")

// Nối chuỗi
"max int = " + bigInt
"A to Int =" + (A.toInt())
"my age = ${age + 2}"
"""..."""    //text xuống hàng
```

## 1.5. Array - List

### 1.5.1. Khởi tạo

```js
var myArr = arrayOf(1, 2.34, "nghia")
var myList = listOf("a","b","c")
var muList : MutableList<Int> = mutableListOf(1,2,3,4)
var map = mapOf("a" to 1, "b" to 2)
var arr2 :Array<Int> = arrayOf(1,2,3)
```

### 1.5.2. Gán dữ liệu

```js
map["key"] = value
map.put(3, "x") //add value
```

### 1.5.3. Phương thức

```js
myArr[2]
.add("d")
.first()
.last()
.take(10)
.clear()
.remove(3)
.removeAt(1)
.size
.contains("nghia")
.indexOf(2.34)
```

### 1.5.4. lambda expression

```js
array
.filter { it.startsWith("a") }
.filter { x -> x>0 } //lọc ra
.filter { it > 0 } //like line up
.sortedBy { it }
.map { it.toUpperCase() } //tạo lại list
.forEach { println(it) } //thực hiện all item trong list
```

### 1.5.5. Đặc biệt

```js
// Kiểm tra trong mảng "map"
for ((k, v) in map) {
    println("$k -> $v")
}

var sqArr = Array(5, {x -> x * x})    //array increase: x[2] = x[1] * x[1]
var oneTo10 = 1..10  //mảng từ 1 đến 10
"A".."Z"  //array from A to Z
10.downTo(1)  //array from 10 to 1
10 downTo 1 step 2
2.rangeTo(20)
oneTo10.step(3) //mảng nhảy 3 vị trí (1,4,7)
arr.reversed()  //mảng nghịch đảo
```

## 1.6. OPERATOR

```js
+ - * / %(lấy dư)
++ --
+= -= *= /= *=
< > <= >= == !=
&& || !
is !is(là kiểu) in !in(trong list)
a as String (chuyển kiểu)
```

## 1.7. CONDITIONAL - if, when, try, break

```js
// if
if () {} if else () {} else {}

// when
when (age) {
    0,1,2,3,4 -> print("baby")
    ‎in 5..13 -> print("tiểu học")
    ‎// có thể dùng !in, is, !is, điều kiện
    ‎else -> { ... }
} //Like Switch Case

val job = when {
    firstName ==  "Dan"       -> "programmers"
    lastName  ==  "Dihiansan" -> "designers"
    else                     -> "others"
}

// try
try {} catch() {}
break continue

// break
loop@ for... break@loop
```

## 1.8. LOOP - Vòng lặp - for, while

```js
for(i in items){}
for(index in items.indies) {
    //index=chỉ số, item = items[index]
}

while (index < items.size) {
    index++
}
```

## 1.9. FUNCTION - Hàm

```js
fun sum(a: Int, b: Int) : Int {
    return a+b
}

//Inline funtion
fun sum(a: Int, b: Int) = a+b
fun printSum(a: Int, b: Int) {
    println("sum of $a and $b is ${a + b}")
} //Call - Using: sum(1, 2) = 1+2 = 3

//List Argument
fun(vararg nums: Int)...

//Variable funtion
var multiply = {a:Int, b:Int -> a*b}    //Call - Using: multiply(2, 3) = 2*3 =6

operator fun...

// Extended funtion
fun nhan(num1: Int) : (Int) -> Int = {num2 -> num1 * num2}
val tinh = nhan(3) //Call - Using: tinh(4)= 3*4 = 12

// Hàm mở rộng của Int
fun Int.percent(percentage: Int)... //Call - Using: 10.percent(50)=10%=5
```

## 1.10. CLASS - Lớp

```js
class Person {
    init { 
        //khởi tạo 
    }
}

//Constructor with defaut name = ""
class Person (val name: String = "")

// 2 constructors
class Person (val name: String){
    constructor (name: String, parent: Person) : this(name) {
    ‎    parent.children.add(this)
    ‎}
}

//Using Class: Instrances of class, without "new"
var man = Person("nghia")
```

### 1.10.1. interface

```js
interface Foo {}

//lớp mở, chỉ cho kế thừa, like struct
open class Name {
    open fun...
    ‎open val...
}
```

### 1.10.2. Lớp trừu tượng

```js
abstract class...{
    override abstract fun...
}
```

### 1.10.3. Override - Kế thừa

```js
//man Kế thừa person
class Man(name:String) : Person(name), Foo...
_Override method
override fun...
override val...
```

### 1.10.4. Call in Class

```js
this.fun    // Call current
super.fun, super("a")  //Call parent
super<Foo>.  //Call with parent name
```

### 1.10.5. Generic - T type

```js
class Box<T>(t:T) { var value = t }

//Inner class
class Outer {
//...
    inner class Inner {
        //...
    }
}
Outer().Inner().   //call
```

### 1.10.6. Enum

```js
enum class Move {
    UP, DOWN, LEFT, RIGHT
}

Move.UP //Using
```

### 1.10.7. Khác

```js
//Lớp dữ liệu java, tạo sẵn getter, setter, toString, hashCode
data class... // ~ giống static class
sealed class...

// Kiểm tra biến khi tạo class
open class Person(var name: String, var age: Int) {
    init {
    ‎   //dùng regex, require để đưa ra yêu cầu biến đầu vào
    ‎  val regex=Regex(".*//d+.*")
    ‎  require(!name.matchs(regex)) {"phải đúng yêu cầu"}
    ‎  require(age>0) {"tuổi phải >0"}
    ‎}
}
```

## 1.11. PACKAGE

```js
pakage my.demo
import java.util.*
```

## 1.12. Special

### 1.12.1. Gọi đa phưong thức khởi tạo

```js
class Turtle {
    fun penDown()
    fun penUp()
    fun turn(degrees: Double)
    fun forward(pixels: Double)
}

//Using:
val myTurtle = Turtle()
with(myTurtle) {
     //draw a 100 pix square
    penDown()
    for(i in 1..4) {
        forward(100.0)
        turn(90.0)
    }
    penUp()
}
```

### Scope Functions (hàm phạm vi trong 1 biến): let, also, apply, with

- with: để gọi nhiều phương thức(method) cùng 1 đối tượng.
- let: để check null
  - Sử dụng một biến trong một phạm vi cụ thể trong đoạn code.
- apply: để Trả về Object (giống return function)
  - extension function cho tất cả các loại Object.
- also: để trả về Object gọi nó (return this)
- run: kết hợp with & let
- takeIf and takeUnless

```js
val number = Random.nextInt(100)
val evenOrNull = number.takeIf { it % 2 == 0 }  // Thỏa điều kiện
val oddOrNull = number.takeUnless { it % 2 == 0 }   // Không thỏa điều kiện
```

### 1.12.2. Coroutines, like thread

```js
fun main(args: Array<String>) {
   println("Start")
   // Start a coroutine
   ‎launch {
       // wait for 1 seconds
   ‎    delay(1000)
   ‎    println("Hello")
   ‎}
   // wait for 2 seconds
    Thread.sleep(2000)
    println("Stop")
}

runBlocking {
    delay(2000)
}
```
