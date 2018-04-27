---
layout: post
title: "Sublime Text 3 : 側邊欄與當前檔案同步"
date: 2017-10-13 16:44:57 +0800
comments: true
tags:
- sublime
---
Sublime 有個非常方便的功能，就是使用 cmd + p，可以在只用幾個檔名關鍵字，瞬間找到並開啟所需的檔案。

另一個方便的功能，就是側邊欄的目錄與檔案列表，可以再不開啟 Finder 的情況下，快速了解現在的檔案結構，當然也可以直接從側邊欄開啟需要的檔案。
<!-- more --> 
但是上面這兩個功能，其實並沒有很好結合。當我使用 cmd + p 快速開啟檔案，或是在頁籤中切換不同檔案時，側邊欄並不會同步更新，還會停留在最後一次使用的畫面。

### SyncedSideBar

想解決這個問題，可以安裝一個非常方便的小外掛，[SyncedSideBar](https://github.com/TheSpyder/SyncedSideBar)。

裝完之後，側邊欄就會同步開啟現在正在編輯的檔案的所在目錄，並且高亮這個檔案。非常方便

另外看到一個討論，在關閉側邊欄時，這個外掛可能觸發強制開啟側邊欄的行為（我沒遇到），如果遇到的人可以參考[這篇文章](http://julianhigman.com/blog/2013/07/23/sublime-text-3-keyboard-shortcut-to-reveal-file-in-sidebar/)的解決方法。
