---
layout: post
title: "Code School – Try SQL 筆記 #1"
date: 2017-10-10 21:53:43 +0800
comments: true
tags: 
- sql
---
Code School 的 Try SQL 是資料庫課程的第一堂課，其實他也是個免費課程。只要註冊就能開始上。內容很簡單，就是資料庫與資料表的 CRUD 。作為入門的課程，應該可以在 1 – 1.5 小時就能看完並熟悉指令。

以下是第一堂課的課程筆記。
<!-- more --> 
### Section 1 簡介

1. 資料庫與資料表
1. 行與列的關係
1. ID: 每一筆資料應附帶的唯一識別碼（Unique identifier），通常被拿來做為 primary key。

### Section 2 取用資料

1. 使用 SELECT 資料 FROM 資料庫 的方式取用資料。
```sql
SELECT title
FROM movies;
```

1. 若 SELECT 單列的標題，則回傳該列的所有資料。
1. 連續指令中間用空格（或換行）分隔，結尾用分號。
1. 同一個指令中的不同參數，用逗號分隔。
```sql
SELECT title, genre, duration
FROM movies;
```

1. 使用 WHERE 過濾資料，字串要加上引號
```sql
SELECT title
FROM movies
WHERE title = 'Top Gun';
```

1. 即使找到資料，仍然會搜尋完整個資料庫，查看是否有其他符合的資料。


### Section 3 排序與過濾資料

1. 使用 ORDER BY 排序資料，DESC 或 ASC 可更改排序升降冪
```sql
SELECT title
FROM movies
ORDER BY duration DESC;
```

1. 使用算數符號設定搜尋區間
```sql
SELECT *
FROM movies
WHERE duration >= 100;
```

1. 使用 AND 或 OR 新增條件
```sql
SELECT title
FROM movies
WHERE duration > 100
AND genre = 'Comedy';
```
