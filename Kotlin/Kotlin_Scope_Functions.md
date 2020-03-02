# Scope Functions (hàm phạm vi trong 1 biến): let, also, apply, with

- [Scope Functions (hàm phạm vi trong 1 biến): let, also, apply, with](#scope-functions-h%c3%a0m-ph%e1%ba%a1m-vi-trong-1-bi%e1%ba%bfn-let-also-apply-with)
  - [Summary](#summary)
  - [Context object: this or it](#context-object-this-or-it)
  - [Return](#return)
  - [Ví dụ](#v%c3%ad-d%e1%bb%a5)
  - [Reference](#reference)

## Summary

- with:
  - Gọi nhiều phương thức.
  - “with this object, do the following.”
- let:
  - Sử dụng một biến trong một phạm vi cụ thể trong đoạn code.
  - (vd: check null)
- run:
  - kết hợp with & let

- apply:
  - Trả về Object (giống return function, return this)
  - “apply the following assignments to the object.”
  - (vd: extension function cho tất cả các loại Object)
- also:
  - Trả về Object (return it)
  - “and also do the following”

- takeIf and takeUnless

```js
val number = Random.nextInt(100)
val evenOrNull = number.takeIf { it % 2 == 0 }  // Thỏa điều kiện
val oddOrNull = number.takeUnless { it % 2 == 0 }   // Không thỏa điều kiện
```

## Context object: this or it

This: run, with, apply
It: let, also

## Return

1. let, run, with:
return the lambda result. trả về dòng cuối.
apply, also:
return the context object. trả về object.

## Ví dụ

```java
// ===== width =====
val numbers = mutableListOf("one", "two", "three")
with(numbers) {
  val firstItem = first() //numbers.first()
  val lastItem = last()   //numbers.last()
  println("First item: $firstItem, last item: $lastItem")
  "new value" // return
}

// ===== run vs let =====
val service = MultiportService("https://example.kotlinlang.org", 80)

// run
val result = service.run {
    port = 8080
    query(prepareRequest() + " to port $port")
}

// let:
val letResult = service.let {
    it.port = 8080
    it.query(it.prepareRequest() + " to port ${it.port}")
}


// ===== Apply =====
val adam = Person("Adam").apply {
    age = 32
    city = "London"
}

// ===== Also =====
numbers
    .also { println("The list elements before adding new one: $it") }
    .add("four")

```

---

## Reference

- <https://kotlinlang.org/docs/reference/scope-functions.html>
