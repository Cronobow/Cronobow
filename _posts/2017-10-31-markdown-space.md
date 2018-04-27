---
layout: post
title: "Sublime 中 Markdown 的換行問題"
date: 2017-10-31 13:33:14 +0800
comments: true
tags:
- markdown
- sublime
---
在 Sublime 中，我一向是把行末的空格，在存檔的同時，自動移除。

一方面維持內容的一致性，另一方面，根據我 seafood 的說法，在 github 比較不會出現無意義的 diff 提示。
<!-- more --> 
在 Sublime 中的設定方式也很簡單，只要在 preferences 中這樣設定即可

Preferences.sublime-settings -- User
``` json 
{
  "trim_trailing_white_space_on_save": true,
}
```

這一直都進行得很好，直到有一天，我膝蓋中了一箭。

### 移除空格的問題

改用 Octopress 寫文章後，就出現了 markdown 症候群，所有的內容都希望純粹由正確的 markdown 語法來解析，不希望有混用的情形發生。這時，我才發現一個問題：

> Markdown 的 `<br>` 換行，是採用 *行末兩個空格* 來表示

所以如果存檔時自動將空格移除，那所有的換行就都消失了

### Syntax Specific 設定

解決方法，就是在 Sublime 的設定檔中，指定 Markdown 文件的設定檔案，把這行排除。請先開啟你任何一個 markdown 檔案，在這個畫面中，選擇

*Preferences > Settings – More > Syntax Specific*

然後把裡面的內容改成

Markdown.sublime-settings
```
{
    // Which file extensions go with this file type?
    "extensions":
    [
        "md",
        "mdown",
        "mdwn",
        "mmd",
        "markdown"
    ],

    // Set to true to removing trailing white space on save
    "trim_trailing_white_space_on_save": false,
}

```

存檔之後，markdown 文件中的空白就會保留了。
