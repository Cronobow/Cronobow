---
layout: post
title: "安裝 Ruby on Rails 環境重點筆記"
date: 2017-10-20 18:48:04 +0800
comments: true
tags:
- ruby
- rails
- sublime
---
這次趁著 macOS 升級的同時，大整理一次電腦中的程式，順便重新把 ruby on rail 的環境安裝，做一個整理筆記。
<!-- more --> 
### 安裝 Command Line Tools

1. 在 Terminal 中輸入指令：  
   `xcode-select --install` 

2. 檢查是否安裝成功  
   `xcode-select -p`  
   顯示：  
   `/Applications/Xcode.app/Contents/Developer`  即是成功安装！

3. 未安裝Xcode是出現：  
   `/Library/Developer/CommandLineTools`

### 安裝 Homebrew

1. 到 [Homebrew 網站](https://brew.sh/index_zh-tw.html) 取得最新安裝指令。

2. 出現 `Installation successful!` 即是安裝完成

### 使用 Homebrew 安裝必要程式

1. 安裝 git  `brew install git` 或  
   沒有 auto-completions 的 git  
   `brew install git --without-completions` (git flow 和 zsh 的相容性)

2. 安裝 git-flow `brew install git-flow-avh`

3. 安裝 ImageMagick  `brew install imagemagick` (選用)

4. 安裝 PostgresSQL  `brew install postgresql`  
   結束後執行 `brew services start postgresql` (開機自動啟動)

### 安裝 ruby 版本控制系統 rbenv

1. 執行 `brew install rbenv`

2. 在 Home 目錄下 新增檔案  
   `nano .bash_profile`  ( bash 用)

3. 在使用的 shell 中加上兩行
```bash
export PATH="$HOME/.rbenv/bin:$PATH"
eval "$(rbenv init -)"
```

4. 重新啟動 terminal

### 安裝 Ruby 在 rbenv 內

1. `rbenv install 2.4.0`

2. 指定預設版本 `rbenv global 2.4.0`

3. 查看 ruby 版本 `which ruby`  
輸出結果應包含 `.rbenv/shims/ruby`

4. 更新 gem 到最新版 `gem update`  
更新完需執行 `rbenv rehash`

### 安裝 Rails
1. `gem install rails` 預設安裝最新版

2. `gem install rails -v 5.1.2` 可指定版本

### 優化與調整

* 在終端機使用 subl 開啟檔案
```bash
sudo ln -s "/Applications/Sublime Text.app/Contents/SharedSupport/bin/subl" /usr/local/bin/subl
```

* 改變 shell 為 zsh，輸入
  `chsh -s /bin/zsh`

### 使用 on_my_zsh
* 安裝 on_my_zsh
```bash
cd ~/
git clone git://github.com/robbyrussell/oh-my-zsh.git ~/.oh-my-zsh
cp ~/.zshrc ~/.zshrc.orig
cp ~/.oh-my-zsh/templates/zshrc.zsh-template ~/.zshrc
subl .zshrc
```

* 安裝 zsh 高亮外掛
```bash
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting
```

* 修改 .zshrc

    + 新增兩行，載入 rbenv
```bash
export PATH="$HOME/.rbenv/bin:$PATH"
eval "$(rbenv init -)"
```

    + 修改 theme
```bash
#ZSH_THEME="robbyrussell"
ZSH_THEME="agnoster"
```
  
    * 修改 plugin
```bash
#plugins=(git)
plugins=(git git-flow zsh-syntax-highlighting)
```

    * 新增 SourceTree 快速鍵
```bash
# SourceTree
alias stree='/Applications/SourceTree.app/Contents/Resources/stree'
```

1. 替換 agnoster 的 theme source code
    1. 打開 `subl ~/.oh-my-zsh/themes/agnoster.zsh-theme `
用 [這裡](https://gist.githubusercontent.com/agnoster/3712874/raw/c3107c06c04fb42b0ca27b0a81b15854819969c6/agnoster.zsh-theme ) 的內容替換掉
    1. 安裝 powerline 特殊字型：[vim-powerline patched fonts](https://gist.github.com/qrush/1595572)
    1. 在 itrem2 中選擇佈景主題和字型
        * Preference -> Profiles -> Colors -> Load Presets，載入 Solarized Dark
        * Preference -> Profiles -> Text 換成 Menlo 16 字體

### 修改 git alias

```
git config --global alias.co checkout
git config --global alias.ci commit
git config --global alias.st status
git config --global alias.br branch
```

### Sublime 設定檔
Preferences.sublime-settings -- User

``` json
{
  "binary_file_patterns":
  [
    "*.jpg",
    "*.jpeg",
    "*.png",
    "*.gif",
    "*.ttf",
    "*.tga",
    "*.dds",
    "*.ico",
    "*.eot",
    "*.pdf",
    "*.swf",
    "*.jar",
    "*.zip"
  ],
  "default_line_ending": "unix",
  "ensure_newline_at_eof_on_save": true,
  "env":
  {
    "PATH": "/usr/local/bin/elixir"
  },
  "folder_exclude_patterns":
  [
    ".svn",
    ".git",
    ".hg",
    "CVS",
    ".sass-cache"
  ],
  "font_face": "Inconsolata",
  "font_size": 20.0,
  "ignored_packages":
  [
    "Vintage"
  ],
  "line_padding_bottom": 1,
  "line_padding_top": 1,
  "save_on_focus_lost": true,
  "tab_size": 2,
  "translate_tabs_to_spaces": true,
  "trim_trailing_white_space_on_save": true,
  "word_wrap": true
}
```
