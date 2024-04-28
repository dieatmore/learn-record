# Learn Record
## Overview
This repository records the learning content of the school laboratory.

## Development Environments
+ VS Code
+ Prettier
+ Git

## Update


### 2024.04.26
#### CSS
```
element/id/class Selectors; Cascading; Units; Box Model;
Background/Image/Text/Opacity; Combinators Selectors; display;
Vertical-Align; table; float; position; Box-Sizing; Navigation Bar
```
***
### 2024.04.20
+ 掌握基本 git/github 本地远程版本控制
+ 掌握基于 gihub pull request 的团队项目开发
```
 origin; master; branch; branch types; commit; commit message types;
 push; pull; marge
```
#### Github PR
操作基本可通过 vs code 实现
1. fork，源仓库至个人远程仓库
2. clone，个人仓库至本地
3. upstream，关联源仓库
4. branch，创建 docs branch。有点麻烦，但还是掌握了吧
5. commit，docs branch 中修改提交
6. pull，更新拉取源仓库至当前 docs branch
7. merge，将源仓库 upstream merge 至 docs branch。目的：如果有冲突，要在 branch 解决而不是 master
8. branch，切换回 master branch，再从 master merge docs branch。由于 upstream/docs branch 冲突已经在 docs branch 解决，因此可直接整合 upstream 至 master branch。此时，upstream/master/bocs 汇聚为最新提交节点
9. push，可直接向源仓库 push upstream。等待源仓库合并代码
10. pull，收到源仓库 merge 通知后，更新本地 master branch，并再次 push 至个人远程仓库
11. 此时，master branch; origin/master; upstream/master，同步
12. del branch，删除完成使命的 docs branch
***
### 2024.04.16
#### HTML
```
div; span; p; h1; br; hr; table; ul; img;
```
#### Emmet
```
>; +; ^; (); *; $; lorem;
```
#### markdown
维护学习文档
***
### 2024.04.10
项目目录？目录下的文件？文件中的配置？
熟悉 vscode 功能。
创建基本网页，在 vscode 中调用浏览器打开。
熟悉基本 HTML 标签。
熟悉基本 Emmet 语法。.vscode/.prettierrc.json
