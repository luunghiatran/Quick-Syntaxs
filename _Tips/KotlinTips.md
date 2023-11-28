# Kotlin Tips


## fake data:

```kotlin
fun fakeArticles (count: Int): List { 
    return (0 until count).map {
        ArticleEntity(
            sourceName = "Source #$it", title = "Title #$it",
            content="Content",
            author = "Author",
            publishedAt = Instant.DISTANT_PAST, url = "https://link.to.article/$it",
            id
            it.toString()
        )
    }
}

// Or
List(count) { index -> ... }
```

## Type safety for primitives
