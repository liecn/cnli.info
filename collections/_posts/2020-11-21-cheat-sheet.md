---
layout: post
title: 写在小本本上的小抄
date: 2020-11-21 23:59:59
description: 用白纸黑字对抗遗忘。
permalink: /cheat-sheet/
categories: [collections]
tags: [烂笔头]
date: 2020-11-21 12:00:00
--- 
## Linux

### awk 行处理文本
- `awk [-F|-f|-v] 'BEGIN{} // {command1; command2} END {}' -FILENAME`
- `[-F|-f|-v]`   大参数，-F指定分隔符，-f调用脚本，-v定义变量 var=value
- ''   		 引用代码块
- `BEGIN`  	 初始化代码，主要是引用全局变量，设置FS分隔符
- `//`     	 匹配代码块，可以是字符串或正则表达式
- `{}`           命令代码块，包含一条或多条命令
- `;`         	 多条命令使用分号分隔（如print,则分行输出）
- `END`     	 结尾代码块，主要是进行最终计算或输出结尾摘要信息
> demo:
```
awk -f script.awk -filename	//指定脚本文件
ls -l|awk 'BEGIN{sum=0} !/^d/{sum+=$5} END{print "total size is",sum}'	//正则匹配
awk -F: '{print NF}' /etc/passwd	//显示每行有多少字段
awk -F: '{print $NF}' /etc/passwd     	//将每行第NF个字段的值打印出来  
awk -F: 'NF>2{print $0}' /etc/passwd  	//显示每行字段数量大于2的行
awk '$6 ~ /WAIT/ || NR==1 {print NR,$4,$5,$6}' OFS="\t" netstat.txt    	//输出字段6匹配WAIT的行，其中输出每行行号，字段4，5,6，并使用制表符分割字段
```

## Git
### 工作区->暂存区->本地repo->远端repo
- 修改历史：`git log`
> 试图精简信息，可以配置 `--pretty=oneline` 参数：`git log --graph`
		  
- 版本回退：`git reset --hard [commit_id\HEAD^\HEAD^^\HEAD~100]`
- 命令历史：`git reflog`
> 用来查找[commit_id]

- 丢弃工作区的修改：`git checkout -- file`
> 让这个文件回到最近一次git commit或git add时的状态
- 丢弃暂存区的修改：`git reset HEAD file`
> 把暂存区的修改回退到工作区

- 删除：`git rm file`

### create a new repository on the command line
```
echo "# tutorial" >> README.md
git init
git add README.md
git commit -m "first commit"
git remote add origin git@github.com:liecn/tutorial.git
git push -u origin master
```
### push an existing repository from the command line
```
git remote add origin git@server-name:path/repo-name.git
git push -u origin master
```
> -u 把本地的master分支和远程的master分支关联

- Git支持多种协议，包括https，但通过ssh支持的原生git协议速度最快。

### 分支操作
- 查看分支：`git branch`
- 创建+切换分支：`git checkout -b [name]`
- 创建分支：`git branch [name]` 
- 切换分支：`git checkout [name]`
- 删除分支：`git branch -d [name]`
- 强制删除分支：`git branch -D [name]`
- 合并某分支到当前分支：`git merge [name]`
> 合并dev分支，`--no-ff`参数，表示禁用Fast forward：
`git merge --no-ff -m "merge with no-ff" dev`
### 本地repo操作
- 保存现场：`git stash`
`git stash list`
- 恢复现场
> 用`git stash apply`恢复，但是恢复后，stash内容并不删除，你需要用`git stash drop`来删除；
> 另一种方式是用`git stash pop`，恢复的同时把stash内容也删了。
### tag操作
- 命令`git tag <name> <commit id>`

> 用于新建一个标签，默认为HEAD，也可以指定一个commit id；

> `git tag -a <tagname> -m "blablabla..."`可以指定标签信息；

> `git tag -s <tagname> -m "blablabla..."`可以用PGP签名标签；

- `git show <tagname>`	可以看到说明文字
- 命令`git push origin <tagname>`可以推送一个本地标签；

- 命令`git push origin --tags`可以推送全部未推送过的本地标签；
- 命令`git tag -d <tagname>`可以删除一个本地标签；
- 命令`git push origin :refs/tags/<tagname>`可以删除一个远程标签

### 远端操作
git remote -v		查看远程库信息：
git remote rm origin 	删除已有的GitHub远程库
git push github master
git push gitee master
### tips
- `git config --global color.ui true`
> 忽略某些文件时，需要编写.gitignore；

> 当前用户的Git配置文件放在用户主目录下的一个隐藏文件.gitconfig

> 每个仓库的Git配置文件都放在.git/config文件中
### Debug
> 从本地推送分支，使用git push origin branch-name，如果推送失败，先用git pull抓取远程的新提交；

> 在本地创建和远程分支对应的分支，使用git checkout -b branch-name origin/branch-name，本地和远程分支的名称最好一致；

> 如果git pull提示“no tracking information”，则说明本地分支和远程分支的链接关系没有创建，用命令git branch --set-upstream branch-name origin/branch-name

> 从远程抓取分支，使用git pull，如果有冲突，要先处理冲突。

## tmux
利用Ctrl+b进入控制模式

### 模块
- server	输入tmux指令即开启服务器
- session 	回话，一个server可包含多个session
- window 	窗口，一个session可包含多个window
- session 	面板，一个window可包含多个panel

### 启动
- tmux
- tmux a
- tmux ls
- tmux at -t [session_name] 
- tmux kill-server 	删除所有session
- tmux kill-session -t [session_name]	删除指定session

### 系统操作
```
?		列出所有快捷键，q返回
d 		脱离并暂存当前session
D		在多个session中选择要脱离的session
Ctrl+z 		挂起当前session		
s		在多个session中选择session
:		进入命令行模式
[		进入vi模式，按q/ESC退出
~		列入提示信息缓存
```
### 窗口操作
```
c		新建window
& 		关闭当前window
数字键		切换至指定window
p 		切换至上一window	
n		下一window
l		相互切换
w		通过window列表切换
，		重命名当前window	
.		修改window编号
f		所有window中查找指定文本
```
### 面板操作
```
"/%
x		关闭当前panel
!		当前panel置于新window
Ctrl/Alt+方向键 调整panel大小	
Space		循环切换布局
q		显示panel编号
o		当前window中选择下一panel
Alt+o		逆时针旋转
Ctrl+o		顺时针旋转	
{/}		左右移动
:join-panel -t [window_name]	合并panel置window
```

## vi/vim commands

![vi 模式转换](/img/vi.png)

### 光标移动
```
[Ctrl] + f 	屏幕向下移动一页（Page Down）
[Ctrl] + b 	屏幕向上移动一页（Page Up）

[0]或[Home】 	光标移动到当前行的最前面
[$]或[End] 	光标移动到当前行的末尾

G		 光标移动到文件的最后一行（第一个字符处）
nG		 n为数字（下同），移动到当前文件中第n行
gg		 移动到文件的第一行，相当于"1G"
n[Enter]	 光标向下移动n行
```
### 查找
```
/word		 在文件中查找内容为word的字符串（向下查找）
?word		 在文件中查找内容为word的字符串（向上查找）
[n]		 表示重复查找动作，即查找下一个
[N]		 反向查找下一个
:n1,n2s/word1/word2/g	 n1、n2为数字，在第n1行到第n2行之间查找word1字符串，并将其替换成word2
:1,s/word1/word2/g	从第一行（第n行同理）到最后一行查找word1，并将其替换成word2
:1,s/word1/word2/gc	 功能同上，只不过每次替换时都会让用户确认
```
### 删除
```
x		向后删除一个字符 (Delete)
X		向前删除一个字符 (Backspace)
ndd 		删除光标所在的向下n行
```
### 复制
```
yy		复制光标所在的那一行
nyy		复制光标所在的向下n行
p		将已经复制的数据在光标下一行粘贴
		将已经复制的数据在光标上一行粘贴
```
### 撤销
```
u		撤消上一个操作
[Ctrl] + r	多次撤消
.		这是小数点键，重复上一个操作
```
### 块选择
```
v,V		将光标经过的地方反白选择
[Ctrl] + v	长方形的方式选择文本
y		将反白的地方复制到剪贴板
d		将反白的内容删除
```

### 多文件编辑
```
vim file1 file2 同时打开两个文件
:n	 	编辑下一个文件
:N	 	编辑上一个文件
:files	 	列出当前用vim打开的所有文件
```
### 多窗口编辑
```
:sp [filename]	打开一个新窗口，显示新文件，若只输入:sp，则两窗口显示同一个文件
[Ctrl] + w + j 	光标移动到下方窗口
[Ctrl] + w + k	光标移动到上方窗口
[Ctrl] + w + q 	离开当前窗口
```

### 进入插入模式
```
i		当前位置插入
a		当前光标下一位置插入
A		光标所在行最后一个字符插入
o		光标所在行的下一行插入新行并插入
O		光标所在行的上一行插入新行并插入
```

### 进入替换模式
```
r		替换一次
R		持续替换
```
### 命令行模式
```
:w		 保存文件
:w!		 若文件为只读，强制保存文件
:q		 离开vi
:q!		 不保存强制离开vi
:wq		 保存后离开
:wq!		 强制保存后离开
:! command	 暂时离开vi到命令行下执行一个命令后的显示结果
:set nu		 显示行号
:set nonu	 取消显示行号
:w newfile	 另存为
:set fileencoding 	查看当前文件编码格式
:set fileencoding=utf-8	设置当前文件编码格式为utf-8
:set fileformat		 查看当前文件的断行格式
:set fileformat=unix	 将当前文件的断行格式设置为unix格式
```

## 最后更新

2020.11.21