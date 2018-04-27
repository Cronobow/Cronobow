---
layout: post
title: "git-flow-completion on zsh"
date: 2017-09-03 09:27:32 +0800
comments: true
tags: 
- git
---
最近公司決定正式導入 git flow 的開發流程。所以我也安裝了 git flow 和 git-flow-completion。

不過繞了一大圈才把 git-flow-completion 解決，紀錄一下。
<!-- more  -->
首先我是使用 zsh，以及 oh-my-zsh。用 brew 裝 git flow 是沒啥問題，但是 git-flow-completion 就怪怪的了。

一開始我是自己去 clone 一份 git-flow-completion 到 oh-my-zsh 的 custom plugin 裡面。後來發現 oh-my-zsh 其實已經包進去了。不過這不是重點，重點是 git-flow-completion 怎麼樣都沒辦法正常運作。

後來偉大的 google 大神幫我找到了一個解法，就在 oh-my-zsh 的 一個 issues 裡面:

```zsh
brew uninstall git
brew install git --without-completions
```

總之就是裝一份沒有 autocompletions 的 git 就可以了。

紀錄一下免得下次又找不到。
