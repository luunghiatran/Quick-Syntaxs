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
// Search all "HELLO WORD"
(?i)(^|$|\s|)\QHELLO WORD\E(?!([a-z0-9]+))  

// Select all tag html
<[^>]*>    

// Lấy "test1" hoặc "test2" cuối cùng
(?s:.*\s)\K(test1|test2)(?!.*(test1|test2))     
```

---

## Reference

- <https://www.vogella.com/tutorials/JavaRegularExpressions/article.html>
