```dataview
Table author as Author, ("![|100](" + cover + ")") as Cover, total as "Pages", category as genre, rating
From "Books"
Where contains(status, "to read")
```

