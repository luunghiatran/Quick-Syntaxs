# PHP Code Syntax

- [PHP Code Syntax](#php-code-syntax)
	- [FILE TYPE](#file-type)
	- [HELLO WORLD](#hello-world)
	- [COMMENT](#comment)
	- [Metadata](#metadata)
	- [VARIABLE](#variable)
		- [Declare Variable](#declare-variable)
		- [Assign Variable](#assign-variable)
		- [Variable Types](#variable-types)
		- [Using Variable](#using-variable)
		- [Constant/ final](#constant-final)
		- [Generic Variable - kiểu chung T](#generic-variable---kiểu-chung-t)
	- [STRING](#string)
	- [ENUM](#enum)
		- [Declare](#declare)
		- [Using](#using)
	- [OPERATOR](#operator)
		- [Arithmetic (Số học)](#arithmetic-số-học)
		- [Combined assignment (kết hợp +=)](#combined-assignment-kết-hợp-)
		- [Comparison (So sánh)](#comparison-so-sánh)
		- [Logical](#logical)
		- [Bitwise (tính bit)](#bitwise-tính-bit)
		- [Operator precedence (độ ưu tiên)](#operator-precedence-độ-ưu-tiên)
	- [STRING](#string-1)
		- [Character reference (CHAR)](#character-reference-char)
		- [String compare](#string-compare)
		- [Escape characters (special char)](#escape-characters-special-char)
	- [Numberic ARRAY](#numberic-array)
		- [Declare](#declare-1)
		- [Assign](#assign)
		- [Get Item](#get-item)
		- [Add Item](#add-item)
		- [Remove Item](#remove-item)
	- [Associative Arrays (like enum)](#associative-arrays-like-enum)
		- [Declare](#declare-2)
		- [Assign](#assign-1)
		- [Get value](#get-value)
	- [Mixed arrays (multi type)](#mixed-arrays-multi-type)
	- [Multi-dimensional arrays](#multi-dimensional-arrays)
		- [Declare](#declare-3)
		- [Assign](#assign-2)
		- [Get value](#get-value-1)
	- [Hash table (mảng trong mảng)](#hash-table-mảng-trong-mảng)
	- [CONDITIONAL](#conditional)
		- [If](#if)
		- [Switch](#switch)
		- [Alternative syntax (short if)](#alternative-syntax-short-if)
		- [Mixed modes (php + HTML + if)](#mixed-modes-php--html--if)
	- [LOOP](#loop)
		- [For](#for)
		- [While](#while)
		- [Break](#break)
		- [Continue](#continue)
		- [Loop in array](#loop-in-array)
	- [LABLE - Go to](#lable---go-to)
	- [METHOD/ FUNTION](#method-funtion)
		- [Define Method](#define-method)
		- [Call Method](#call-method)
		- [Parameter in Method](#parameter-in-method)
		- [Default parameters](#default-parameters)
		- [Variable parameter list](#variable-parameter-list)
		- [Return method](#return-method)
		- [Scope and lifetime (Global vs Local)](#scope-and-lifetime-global-vs-local)
		- [Anonymous functions](#anonymous-functions)
		- [Override - Overloading](#override---overloading)
		- [Passing Argument](#passing-argument)
		- [Static](#static)
		- [Public/ Private/ Protected](#public-private-protected)
	- [CLASS](#class)
		- [Constructor - Destructor](#constructor---destructor)
		- [This](#this)
		- [Overriding](#overriding)
		- [Call Parent/ Super](#call-parent-super)
		- [Struct](#struct)
		- [Sealed](#sealed)
		- [Interface](#interface)
		- [Abstract](#abstract)
		- [Inherit](#inherit)
		- [Object comparison](#object-comparison)
	- [PACKAGE/ NAMESPACE](#package-namespace)
	- [IMPORT](#import)
	- [EXCEPTION](#exception)
		- [Try Catch](#try-catch)
	- [IMPRESSION](#impression)


## FILE TYPE
## HELLO WORLD

```php
<?php ... ?>
<? ... ?>
<script language="php">...</script>
	Outputting text (Xuất text)
	echo "Hello World";
	print "Hello World"
<?= "Hello World" ?>
<? echo "Hello World" ?>
```

## COMMENT

```php
// single-line comment
# single-line comment
/* multi-line comment */
```

## Metadata
## VARIABLE
### Declare Variable

```php
$myVar;
$myVar = 10;
$myVar = 1; // int type
$myVar = 1.5; // float type
$myInt = 1234; // decimal number$myInt = 0b10; // binary number (2 decimal)$myInt = 0123; // octal number (83 decimal)$myInt = 0x1A; // hexadecimal number (26 decimal)
$myFloat = 1.234; $myFloat = 3e2; // 3*10^2 = 300
$myBool = true; // bool type
$myNull = null; // variable is set to null
```

### Assign Variable
### Variable Types
### Using Variable
### Constant/ final
### Generic Variable - kiểu chung T

## STRING
## ENUM
### Declare
### Using

## OPERATOR

### Arithmetic (Số học)

```php
$x = 4 + 2; // 6 // addition
$x = 4 - 2; // 2 // subtraction
$x = 4 * 2; // 8 // multiplication
$x = 4 / 2; // 2 // division
$x = 4 % 2; // 0 // modulus (division remainder)
```

###  Combined assignment (kết hợp +=)

```php
$x = 0;
$x += 5; // $x = $x+5;
$x -= 5; // $x = $x-5;
$x *= 5; // $x = $x*5;
$x /= 5; // $x = $x/5;
$x %= 5; // $x = $x%5;
Increment and decrement (Tăng, giảm ++)
$x++; // $x += 1;
$x−−; // $x -= 1;
$x = 5; $y = $x++; // $x=6, $y=5$x = 5; $y = ++$x; // $x=6, $y=6
```

### Comparison (So sánh)

```php
$x = (2 == 3); // false // equal to
$x = (2 != 3); // true // not equal to
$x = (2 <> 3); // true // not equal to (alternative)
$x = (2 === 3); // false // identical
$x = (2 !== 3); // true // not identical
$x = (2 > 3); // false // greater than
$x = (2 < 3); // true // less than
$x = (2 >= 3); // false // greater than or equal to
$x = (2 <= 3); // true // less than or equal to
$x = (1 == "1"); // true (same value)$x = (1 === "1"); // false (different types)
```

### Logical 

```php
$x = (true && false); // false // logical and
$x = (true || false); // true // logical or
$x = !(true); // false // logical not
```

### Bitwise (tính bit)

```php
$x = 5 & 4; // 101 & 100 = 100 (4) // and$x = 5 | 4; // 101 | 100 = 101 (5) // or$x = 5 ^ 4; // 101 ^ 100 = 001 (1) // xor (exclusive or)$x = 4 << 1; // 100 << 1 =1000 (8) // left shift$x = 4 >> 1; // 100 >> 1 = 10 (2) // right shift$x = ~4; // ~00000100 = 11111011 (-5) // invert
```

### Operator precedence (độ ưu tiên)

```php
++ −− 
~ − (unary)
!
/ % 
+ − (binary) 
<< >> 
< <= > >= <> 
== != === !== 
&
^
|
&&
||
= op=
and
16 xor
17 or
```

## STRING

```php
$a = 'Hello';
$b = $a . ' World'; // Hello World
$a .= ' World'; // Hello World

echo "Hello $a"; // "Hello World"
echo 'Hello $a'; // "Hello $a"

// Heredoc (Enter string)
$s = <<<LABEL
Heredoc (with parsing) (văn bản html)
LABEL;

// Nowdoc
$s = <<<'LABEL'
Nowdoc (without parsing)
LABEL;
```

### Character reference (CHAR)

```php
$s = 'Hello';
$s[0] = 'J';
echo $s; // "Jello"
$s[strlen($s)-1] = 'y';echo $s; // "Jelly"
```

### String compare

```php
$a = 'test';
$b = 'test';
$c = ($a == $b); // true
```

### Escape characters (special char)

```php
\n newline 
\f form feed
\t horizontal tab 
\$ dollar sign
\v vertical tab 
\' single quote
\e escape 
\" double quote
\r carriage return 
\\ backslash
```

## Numberic ARRAY

### Declare

```php
$a = array(1,2,3);
$a = [1,2,3];
$a[] = 5; // $a[4]
```

### Assign

```php
$a[0] = 1;
$a[1] = 2;
$a[2] = 3;
```

### Get Item

```php
echo "$a[0] $a[1] $a[2] $a[3]"; // "1 2 3 4"
```

### Add Item

```php
$a[3] = 4; //Add new Element
```

### Remove Item

```php
unset($array[2]);
```

## Associative Arrays (like enum)

### Declare

```php
$b = array('one' => 'a', 'two' => 'b', 'three' => 'c'); // key => value
$c = array(0 => 0, 1 => 1, 2 => 2); // khai báo số
$e = array(5 => 5, 6); // tự liên tiếp số 
```

### Assign

```php
$b['one'] = 'a';$b['two'] = 'b';$b['three'] = 'c';
```

### Get value

```php
echo $b['one'] . $b['two'] . $b['three']; // "abc"
```

## Mixed arrays (multi type)

```php
$d = array(0 => 1, 'foo' => 'bar');
```

## Multi-dimensional arrays

### Declare

```php
$a = array(array('00', '01'), array('10', '11'));
$c[][][][] = "0000"; // four dimensions
```

### Assign

```php
$a[0][0] = '00';$a[0][1] = '01';$a[1][0] = '10';$a[1][1] = '11';
```

### Get value

```php
echo $a[0][0] . $a[0][1] . $a[1][0] . $a[1][1];
```

## Hash table (mảng trong mảng)

```php
$b = array('one' => array('00', '01'));
echo $b['one'][0] . $b['one'][1]; // "0001"
```

## CONDITIONAL

### If

```php
if ($x == 1) {
	echo "x is 1";
}
elseif ($x == 2) {
	echo "x is 2";
}
else {
	echo "x is something else";
}
```

### Switch

```php
switch ($x) {
	case 1: 
		echo "x is 1"; 
		break;
	case 2: 
		echo "x is 2"; 
		break;
	default: echo "x is something else";
}
```

### Alternative syntax (short if)

```php
if ($x == 1): 
	echo "x is 1";
elseif ($x == 2): 
	echo "x is 2";
else: 
	echo "x is something else";
endif;

switch ($x):
case 1: 
	echo "x is 1"; 
	break;
case 2: 
	echo "x is 2"; 
	break;
default: 
	echo "x is something else";
endswitch;

$y = ($x == 1) ? 1 : 2; // Ternary operator expression
($x == 1) ? $y = 1 : $y = 2; // Ternary operator statement
```

### Mixed modes (php + HTML + if)

```php
<?php if ($x == 1) { ?>
	This will show 
		if $x is 1
			.<?php } 
		else { 
			?>Otherwise this will show.
<?php } ?>

<?php if ($x == 1): ?>
	This will show 
		if $x is 1
			.<?php 
		else: ?>
			Otherwise this will show.
<?php endif; ?>
```

## LOOP

### For

```php
for ($i = 0; $i < 10; $i++) { 
	echo $i; 
} // 0-9

for (;$i < 10;) { 
	echo $i++; 
}

// 2 variable change
for ($i = 0, $x = 9; $i < 10; $i++, $x--) {
	echo $x; // 9-0
}
```

### While

```php
$i = 0;
while ($i < 10) { 
	echo $i++; 
} // 0-9

// Do-while loop
$i = 0;
do { 
	echo $i++; 
} while ($i < 10); // 0-9
```

### Break

```php
$i = 0;
while ($i++ < 10) {
	for (;;) { 
		break 2; // end for and while
	} 
}
```

### Continue

```php
$i = 0;
while ($i++ < 10) {
	for (;;) { 
		continue 2; // start next while iteration
	} 
}
```

### Loop in array

```php
$a = array(1,2,3);
for($i = 0; $i < sizeof($a); $i++) {
	echo $a[$i]; // "123"
}

// Foreach loop
$a = array (1,2,3);
foreach ($a as $v) {
	echo $v; // "123"
}

// Mixed arrays
$a = array ('one' => 1, 'two' => 2, 'three' => 3);
foreach ($a as $k => $v) {
	echo "$k => $v <br>";
}

// Alternative syntax (phương thức thay thế)
while ($i < 10): 
	echo $i++; 
endwhile;

for ($i = 0; $i < 10; $i++): 
	echo $i; 
endfor;

foreach ($a as $v): 
	echo $v; 
endforeach;
```

## LABLE - Go to

```php
goto myLabel; // jump to labelmyLabel: // label declaration

loop: while (!$finished) {
	// ...if ($try_again) goto loop; // restart loop
}
```

## METHOD/ FUNTION

### Define Method

```php
function myFunc() {
	echo "Hello World";
}
```

### Call Method

```php
myFunc(); // "Hello World"

bar(); // error (not found function)
if (true) { function bar() {} }
bar(); // ok
```

### Parameter in Method

```php
function myFunc($x,$y){
	echo $x . $y;
}
myFunc('Hello', ' World'); // "Hello World"
```

### Default parameters

```php
function myFunc($x, $y = " Earth") {
	echo $x . $y;
}
myFunc("Hello"); // "Hello Earth"
```

### Variable parameter list

```php
function myFunc() {
	$x = func_get_arg(0); // get specified argument$y = func_get_arg(1);$z = func_get_arg(2);echo $x . $y . $z;
}
myFunc('Fee', 'Fi', 'Fo'); // "FeeFiFo"

function myFunc() {
	$num = func_num_args(); // count list argument$args = func_get_args(); for ($i = 0; $i < $num; $i++)echo $args[$i] . ' ';
}
myFunc('Fee', 'Fi', 'Fo'); // "Fee Fi Fo"
```

### Return method

```php
function myFunc() {
	return; // exit function
}

function myFunc() {
	return 'Hello'; // exit function and return value
}
echo myFunc(); // "Hello"
```

### Scope and lifetime (Global vs Local)

```php
$x = 'Hello'; // global $x
function myFunc() {
	global $x; // use global $x in this function
	$x .= ' World'; // change global $x
}
myFunc();
echo $x; // "Hello World"

function myFunc() {
	$GLOBALS['x'] .= ' World'; // change global $x
}
```

### Anonymous functions

```php
$say = function($name){
	echo "Hello " . $name;
};
$say("World"); // "Hello World"

$x = 1;
$y = 2;
$callback = function($z) use ($x, $y){
	return $x + $y + $z;
};
echo $callback(3); // "6"
```

### Override - Overloading

```php
// Prints a variable number of parameters
function myprint(){
	$a = func_get_args();
	foreach ($a as $v) { 
		echo $v; 
		}
}
myprint(1,2,3); // "123"
```

### Passing Argument
### Static
### Public/ Private/ Protected

## CLASS

### Constructor - Destructor

```php
class MyRectangle {
	public $x, $y; 
	public $a = 5, $b = 10; // Initial property values

	// constructor
	function __construct(){
		$this->x = 5;
		$this->y = 10;
		echo "Constructed";
	}

	// constructor 2
	function __construct($x, $y){
		$this->x = $x;
		$this->y = $y;
	}

	function newArea($a, $b){
		return $a * $b;
	}
	
	function getArea(){
		return $this->newArea($this->x, $this->y);
	}
}

$r = new MyRectangle(); // "Constructed"
$r = new MyRectangle; // "Constructed"
$r = new MYRECTANGLE; // "Constructed OK, not case sensitivity"

$r = new MyRectangle(5,10); // constructor 2
unset($r); // "Destructed" // remove all references to the object

// Accessing object members
$r->getArea(10, 2); // 20$r->x = 5; $r->y = 10;
```

### This
### Overriding
### Call Parent/ Super
### Struct
### Sealed
### Interface
### Abstract
### Inherit

### Object comparison

```php
class Flag {
	public $flag = true;
}
$a = new Flag();
$b = new Flag();
$c = ($a == $b); // true (same values)$d = ($a === $b); // false (different instances)
```

## PACKAGE/ NAMESPACE
## IMPORT
## EXCEPTION
### Try Catch

## IMPRESSION
