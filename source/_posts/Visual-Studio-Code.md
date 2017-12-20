---
title: Visual Studio Code
date: 2017-12-13 18:19:03
updated_at: 2017-12-14 11:41:39
tags: ['tool']
categories: ['tool']
---

# 介绍
## 快捷键
*   命令行框
    
    >   `Shift + ⌘ + P`

*   打开文件

    >   `⌘ + P`

*   显示终端
    
    >   `Ctrl + ``

*   代码格式化

    >   `Shift + Alt + F ` 或 `Ctrl + Shift + P 后输入 format code`
    
*   上下移动一行

    >   `Alt + Up` 或 `Alt + Down`
    
 
## Ctrl + P 模式
*   直接输入文件名，快速打开文件
*   `?` 列出当前可执行的动作
*   `!` 显示Errors或Warnings，也可以Ctrl+Shift+M
*   `: ` 跳转到行数，也可以Ctrl+G直接进入
*   `@` 跳转到symbol（搜索变量或者函数），也可以Ctrl+Shift+O直接进入
*   `@:` 根据分类跳转symbol，查找属性或函数，也可以Ctrl+Shift+O后输入:进入
*   `#` 根据名字查找symbol，也可以Ctrl+T
    
## 插件
### 插件安装
*   `Ctrl/Cmd + P` (或 `Ctrl/Cmd + E`) 输入 `ext install [插件关键字/名称]`
*   `Ctrl/Cmd + Shift + P (或 F1)` 输入 Extensions, 选中 `Install Extension` 然后输入插件名称/关键字
*   在 `查看 -> 扩展` 中搜索插件安装 

### 常用插件
*   [EditorConfig for VS Code](https://marketplace.visualstudio.com/items?itemName=EditorConfig.EditorConfig)

    >   使不同 IDE 统一编码风格
    >   http://editorconfig.org/
    
*   [Angular 5 Snippets](https://marketplace.visualstudio.com/items?itemName=Mikael.Angular-BeastCode)
*   [HTML Snippets](https://marketplace.visualstudio.com/items?itemName=abusaidm.html-snippets)
*   [HTML CSS Support](https://marketplace.visualstudio.com/items?itemName=ecmel.vscode-html-css)

    >   html 标签智能提示当前项目所支持的 class

*   [jQuery Code Snippets](https://marketplace.visualstudio.com/items?itemName=donjayamanne.jquerysnippets) 
*   [vscode-icons](https://marketplace.visualstudio.com/items?itemName=robertohuertasm.vscode-icons)
*   [Path Intellisense](https://marketplace.visualstudio.com/items?itemName=christian-kohler.path-intellisense)
*   [Npm Intellisense](https://marketplace.visualstudio.com/items?itemName=christian-kohler.npm-intellisense)
*   [npm](https://marketplace.visualstudio.com/items?itemName=eg2.vscode-npm-script)
*   [ESlint](https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint)
*   [TSLint](https://marketplace.visualstudio.com/items?itemName=eg2.tslint)
*   [HTMLHint](https://marketplace.visualstudio.com/items?itemName=mkaufman.HTMLHint)

    >   如果需要修改默认的规则，则需要在项目中提供 `.htmlhintrc` 文件，对原有规则进行覆盖
    
*   [Project Manager](https://marketplace.visualstudio.com/items?itemName=alefragnani.project-manager)
*   [CSScomb](https://marketplace.visualstudio.com/items?itemName=mrmlnc.vscode-csscomb)
*   [Auto Rename Tag](https://marketplace.visualstudio.com/items?itemName=formulahendry.auto-rename-tag)
*   [vscode-fileheader](https://marketplace.visualstudio.com/items?itemName=mikey.vscode-fileheader)
*   [filesize](https://marketplace.visualstudio.com/items?itemName=mkxml.vscode-filesize)
*   [Bracket Pair Colorizer](https://marketplace.visualstudio.com/items?itemName=CoenraadS.bracket-pair-colorizer)
*   [background](https://marketplace.visualstudio.com/items?itemName=shalldie.background)
*   [Better Comments](https://marketplace.visualstudio.com/items?itemName=aaron-bond.better-comments)
*   [vscode-caniuse](https://marketplace.visualstudio.com/items?itemName=agauniyal.vscode-caniuse)
*   [Insert Date String](https://marketplace.visualstudio.com/items?itemName=jsynowiec.vscode-insertdatestring)
*   [Color Info](https://marketplace.visualstudio.com/items?itemName=bierner.color-info)
    
    >   小窗口显示颜色值，rgb、hsl、cmyk、hex 等
    
*   [GitLens](https://marketplace.visualstudio.com/items?itemName=eamodio.gitlens)
    
    >   显示文件最近的commit和作者，显示当前行commit信息

*   [Output Colorizer](https://marketplace.visualstudio.com/items?itemName=IBM.output-colorizer)
*   [lodash](https://marketplace.visualstudio.com/items?itemName=oysun.Lodash)
*   [Version Lens](https://marketplace.visualstudio.com/items?itemName=pflannery.vscode-versionlens)

    >   显示 package.json 中模块当前版本和最新版本

*   [stylelint](https://marketplace.visualstudio.com/items?itemName=shinnn.stylelint)
*   [CSS Peek](https://marketplace.visualstudio.com/items?itemName=pranaygp.vscode-css-peek)

    >   查找 `HTML` 标签中 `class` 定义位置

*   [Debugger for Chrome](https://marketplace.visualstudio.com/items?itemName=msjsdiag.debugger-for-chrome)
*   [open-in-browser](https://marketplace.visualstudio.com/items?itemName=coderfee.open-html-in-browser)
*   [Quokka.js](https://marketplace.visualstudio.com/items?itemName=WallabyJs.quokka-vscode)

    >   Quokka 是一个调试工具，可以对变量的函数和计算值的结果实时预览

*   [Settings Sync](https://marketplace.visualstudio.com/items?itemName=Shan.code-settings-sync)

    >   重新成功 github token 后需重置配置，步骤如下：
    >   
    >   1    `cmd + shift + p`  输入 `sync:reset`
    >
    >   2   `cmd + shift + p`  输入 `sync:sync` 输入最新的 github token，重新上传配置即可




