# Regular Expression Rule

## Rule

```
(?i) : All Case
| : Or
^
$
\s
?!([a-z0-9]+) : Not word
```

## Example

```
// Search all "NGHIA 1"
(?i)(^|$|\s|)\QNGHIA 1\E(?!([a-z0-9]+))  

// Select all tag html "<dfa> </dfa>"
<[^>]*>    

// Lấy "NGHIA 1" hoặc "NGHIA 2" cuối cùng
(?s:.*\s)\K(NGHIA 1|NGHIA 2)(?!.*(NGHIA 1|NGHIA 2))     
```

---

## Reference

- <https://www.vogella.com/tutorials/JavaRegularExpressions/article.html>
