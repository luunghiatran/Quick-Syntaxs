# Regular Expression Rule

## Rule

```
(?i)    : All Case
|       : Or
^       : Bắt đầu 1 dòng
[^t]    : Tất cả từ, trừ "t" 
$
\s
?!([a-z0-9]+) : Not word
\Q Text \E: Match word (java: Pattern.quote(" Text "))
```

## Example

```
// Search all "NGHIA 1"
(?i)(^|$|\s|)\QNGHIA 1\E(?!([a-z0-9]+))  

// Select all tag html "<dfa> </dfa>"
<[^>]*>    

// Lấy "NGHIA 1" hoặc "NGHIA 2" cuối cùng
(?s:.*\s)\K(NGHIA 1|NGHIA 2)(?!.*(NGHIA 1|NGHIA 2)) 

// Ngoại trừ "NullReferenceException" hoặc "updateSurface"
^(?!NullReferenceException|updateSurface).*$
```

---

## Reference

- <https://www.vogella.com/tutorials/JavaRegularExpressions/article.html>
- <https://www.rexegg.com/regex-quickstart.html>
