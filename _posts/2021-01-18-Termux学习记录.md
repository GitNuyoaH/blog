---
title: "Termux"
data: 2021-01-18
categories:
  - blog
tags:
  - NuyoaH
  - 更新
  - Termux
---
Termux是一个Android终端模拟器和Linux环境应用程序，可以直接使用，无需root或设置。自动安装最小基本系统 - 使用APT包管理器可以使用其他软件包。

下载

[**F-droid下载**](https://f-droid.org/packages/com.termux/)

[**Google play下载**](https://play.google.com/store/apps/details?id=com.termux)

[**酷安下载**](https://www.coolapk.com/apk/com.termux)

[**国光Termux教程**](https://www.sqlsec.com/2018/05/termux.html)

```ruby
长按屏幕
├── COPY:    # 复制
├── PASTE:   # 粘贴
├── More:    # 更多
   ├── Select URL:             # 提取屏幕所有网址
   └── Share transcipt:        # 分享命令脚本
   └── Reset:                  # 重置
   └── Kill process:           # 杀掉当前会话进程
   └── Style:                  # 风格配色 需要自行安装
   └── Keep screen on:         # 保持屏幕常亮
   └── Help:                   # 帮助文档
```
```ruby
pkg search <query>              # 搜索包
pkg install <package>           # 安装包
pkg uninstall <package>         # 卸载包
pkg reinstall <package>         # 重新安装包
pkg update                      # 更新源
pkg upgrade                     # 升级软件包
pkg list-all                    # 列出可供安装的所有包
pkg list-installed              # 列出已经安装的包
pkg show <package>              # 显示某个包的详细信息
pkg files <package>             # 显示某个包的相关文件夹路径
```
首先更新源`pkgupdate`

如果觉得慢可以通过更换源[**清华镜像源**](https://mirrors.tuna.tsinghua.edu.cn/help/termux/)

输入以下命令自动更换
```ruby
sed -i 's@^\(deb.*stable main\)$@#\1\ndeb https://mirrors.tuna.tsinghua.edu.cn/termux/termux-packages-24 stable main@' $PREFIX/etc/apt/sources.list

sed -i 's@^\(deb.*games stable\)$@#\1\ndeb https://mirrors.tuna.tsinghua.edu.cn/termux/game-packages-24 games stable@' $PREFIX/etc/apt/sources.list.d/game.list

sed -i 's@^\(deb.*science stable\)$@#\1\ndeb https://mirrors.tuna.tsinghua.edu.cn/termux/science-packages-24 science stable@' $PREFIX/etc/apt/sources.list.d/science.list

pkg update
```
也可以手动修改

编辑`$PREFIX/etc/apt/sources.list`修改为如下内容
```ruby# The termux repository mirror from TUNA:
deb https://mirrors.tuna.tsinghua.edu.cn/termux/termux-packages-24 stable main
```
编辑 `$PREFIX/etc/apt/sources.list.d/science.list`修改为如下内容
```ruby
# The termux repository mirror from TUNA:
deb https://mirrors.tuna.tsinghua.edu.cn/termux/science-packages-24 science stable
```
编辑`$PREFIX/etc/apt/sources.list.d/game.list`修改为如下内容
```ruby
# The termux repository mirror from TUNA:
deb https://mirrors.tuna.tsinghua.edu.cn/termux/game-packages-24 games stable
```
请使用内置或安装在 Termux 里的文本编辑器，例如 vi / vim / nano 等，不要使用 RE 管理器等其他具有 ROOT 权限的外部 APP 来修改 Termux 的文件




我安装的包

`pkg install vim`Vim编辑器

`pkg install less`Termux下Vim支持触摸移动光标移动位置

`pkg install clang`C语言

`pkg install tree`生成文件目录树形结构

`pkg install tmux`终端复用器

`pkg install fish`一个命令行 shell非常推荐这个包

这个包支持:

 _ 语法高亮

 _ 推荐命令

 _ VGA颜色
 
 _ 以及更多

以上命令可以通过

`pkg install vim less clang tree tmux fish`

一键安装

最后测试一下

输入`vim test.c`回车
```ruby
#include <stdio.h>
int main()
{
   printf("Hello world! \n");
   return 0;
}
```
成功运行(●°u°●)​ 」
