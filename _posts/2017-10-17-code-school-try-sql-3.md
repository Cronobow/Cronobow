---
layout: post
title: "Code School – Try SQL 筆記 #3"
date: 2017-10-17 12:20:01 +0800
comments: true
tags: 
- sql
---
Code School – Try SQL 的最後一堂課。是講資料庫和資料表的操作。包含建立刪除資料庫與資料表。也是相當基礎的內容。
<!-- more --> 

### Section 1 資料庫與資料表操作

1. 使用 CREATE DATABASE 建立資料庫。
```sql
CREATE DATABASE Theaters;
```

1. 使用 DROP DATABASE 刪除資料庫。
```sql
DROP DATABASE Theaters;
```

1. 使用 CREATE TABLE建立資料表，欄位用逗點隔開，欄位名稱和資料型態用空格隔開。
```sql
CREATE TABLE movies (
    id int,
    title varchar(50), --括號內的數字是字元的最大長度
    genre varchar(15),
    duration int
);
```

1. 使用 DROP TABLE 移除資料表。
```sql
DROP TABLE movies;
```

### Section 2 資料表操作

1. 使用 ALTER TABLE 操作資料表。
1. 使用 ADD COLUMN 新增欄位，並指定欄位名稱與資料型態。
```sql
ALTER TABLE movies
ADD COLUMN ratings int;
```

1. 使用 DROP COLUMN 移除欄位。
```sql
ALTER TABLE movies
DROP COLUMN ratings;
```
