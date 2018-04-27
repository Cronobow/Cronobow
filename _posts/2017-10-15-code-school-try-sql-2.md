---
layout: post
title: "Code School – Try SQL 筆記 #2"
date: 2017-10-15 20:05:45 +0800
comments: true
tags: 
- sql
---
這是 Code School – Try SQL 的第二堂課，主要是如何新增，修改，和移除資料。課程內容很單純，就是三種不同的指令，另外搭配 [第一堂課]({% post_url 2017-10-10-code-school-try-sql-1 %}) 的 WHERE 來過濾所需的資料。

<!-- more --> 
### Section 1 新增資料

1. 使用 INSERT INTO 新增資料，VALUES 輸入對應的值
```sql
INSERT INTO movies (id, title, genre, duration)
VALUES (5, 'Good Story', 'Comedy', 83);
```

1. 如果每個欄位都要輸入，欄位名稱可以省略
```sql
INSERT INTO movies
VALUES (5, 'Good Story', 'Comedy', 83);
```

1. Primary Key 就算不輸入（一般是id），也會自動產生接下來的數字
1. 未輸入資料的欄位，初始值是 null

### Section 2 更新資料

1. 使用 UPDATE 更新資料，SET 指定要改變的欄位名稱與值，並使用 WHERE 指定要修改的資料
```sql
/* 把 id3 的 genre 改成 Horror，duration 改為 93 */
UPDATE movies
SET genre = 'Horror' ,duration = 93
WHERE id = 3;
```

1. 搭配 WHERE 可批次修改多筆資料
```sql
/* 把所有 genre 為 Horrer 的資料改成 Horror */
UPDATE movies
SET genre = 'Horrer'
WHERE genre = 'Horror';
```

### Section 3 移除資料

1. 使用 DELETE FROM 移除資料
```sql
DELETE FROM movies WHERE id = 5;
```

1. 如果沒有使用 WHERE 指定資料，會刪除資料表中的所有欄位
```sql
DELETE FROM movies;
```

1. WHERE 的各式指定區間和連續技也能使用
```sql
DELETE FROM movies WHERE duration < 100;
```
