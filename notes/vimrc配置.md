# 环境  
- Ubuntu 22.04.1，Vim 8.2  
  
# 学习资源  
> 将配置 Vim 的基本语法，新手入门学习：[笨方法学Vimscript](https://www.kancloud.cn/kancloud/learn-vimscript-the-hard-way/49321)  
> [How to boost your Vim productivity](https://sheerun.net/2014/03/21/how-to-boost-your-vim-productivity/)  
  
  
# 初始默认的 Vimrc 文件  
- 初始时用户没有自己的 Vimrc  文件，在 vim 中输入 `:version`，或者终端输入 `vim --version` 可以查看默认使用的 Vimrc 文件  
```bash  
   system vimrc file: "$VIM/vimrc"  
     user vimrc file: "$HOME/.vimrc"  
 2nd user vimrc file: "~/.vim/vimrc"  
      user exrc file: "$HOME/.exrc"  
```  
  
- 系统的 vimrc 文件的路径为 `$VIM/vimrc`，可以 vim 中输入 `:echo $VIM` 查看其路径  
```bash  
/usr/share/vim  
```  
  
- vim 中输入 `:e $VIM/vimrc` 查看该文件，该文件是初始加载的文件  
![3](https://img-blog.csdnimg.cn/868565486ee841c396acbe5a06f16bd8.png)  
  
  
- `/usr/share/vim/vimrc` 是 `/etc/vim/vimrc` 的符号链接文件  
```bash  
[root@ubuntu22-c0 ~]$ ll /usr/share/vim/vimrc  
lrwxrwxrwx 1 root root 14 Apr 18 19:40 /usr/share/vim/vimrc -> /etc/vim/vimrc  
```  
  
- 如果用户没有自定义的 vimrc 文件，则会加载 `$VIMRUNTIME/defaults.vim` 文件，  
  可以在 vim 中输入 `:e $VIMRUNTIME/defaults.vim` 查看，文件路径如下：  
```bash  
"/usr/share/vim/vim82/defaults.vim" 143L, 4568B   
```  
![5](https://img-blog.csdnimg.cn/90c7d762e91e4afbb2768dd02d7d90bc.png)  
![6](https://img-blog.csdnimg.cn/9e053cd50f834e1aa7a43795bba8835c.png)  
![7](https://img-blog.csdnimg.cn/a70cfd49a5294749b480befda8c9d033.png)  
  
  
# 用户自定义配置文件  
- 环境：vim 8.2 版本  
- 在 vim 中输入 `:h vimrc` 可查看，一般将自定义的文件放在 `$HOME` 路径下，即家目录，  
文件名为 `.vimrc`；或者 `$HOME/.vim/vimrc`。  
![1](https://img-blog.csdnimg.cn/9ff729bbd82c45a58ca69535f31808ee.png)  
- 进入家目录，新建一个文件 `.vimrc`，进入 vim，输入 `:echo $MYVIMRC` 可以看见自定义配置文件的路径  
- 无自定义配置文件时，变量 `$MYVIMRC` 无值  
  
  
# 让自定义的 vimrc 对所有用户生效  
## 将 vimrc 文件复制到 `/etc/skel/` 目录下  
- 如自定义的配置文件在 `~/.vim/vimrc` 中，则将 `~/.vim` 文件夹拷到 `/etc/skel` 目录下，则新创建的普通用户 vimrc 文件相同  
  
## 创建 `/etc/vim/vimrc.local` 文件  
- vim 版本为 `version 8.0.1763`  
- vimrc 文件如下  
```bash  
   system vimrc file: "/etc/vimrc"  
     user vimrc file: "$HOME/.vimrc"  
 2nd user vimrc file: "~/.vim/vimrc"  
      user exrc file: "$HOME/.exrc"  
       defaults file: "$VIMRUNTIME/defaults.vim"  
  fall-back for $VIM: "/etc"  
 f-b for $VIMRUNTIME: "/usr/share/vim/vim80"  
```  
  
- 系统 vimrc 文件为 `/etc/vimrc`，初始执行的文件，后面执行的文件中有相同配置会覆盖此文件的设置  
  
- 执行完系统 vimrc 配置文件后，加载用户各自的配置文件  
默认没有该文件，为用户创建的自定义配置，有两种路径  
    - `$HOME/.vimrc`  
    - `~/.vim/vimrc`  
  
- 如果没有自定义的 vimrc 文件，则会执行 `$VIMRUNTIME/defaults.vim`，即使前面在 `/etc/vimrc` 中调用了 `/etc/vim/vimrc.local`，因此如果全局使用 `/etc/vim/vimrc.local` 文件，则需要禁用 `$VIMRUNTIME/defaults.vim` 文件，可以在 `$VIMRUNTIME/defaults.vim` 文件的最上面设置变量 `skip_defaults_vim` 变量，即 `let g:skip_defaults_vim = 1`  
```bash  
   " The default vimrc file.  
  1 "  
  2 " Maintainer:   Bram Moolenaar <Bram@vim.org>  
  3 " Last change:  2021 Nov 17  
  4 "  
  5 " This is loaded if no vimrc file was found.  
  6 " Except when Vim is run with "-u NONE" or "-C".  
  7 " Individual settings can be reverted with ":set option&".  
  8 " Other commands can be reverted as mentioned below.  
  9  
 10 let g:skip_defaults_vim = 1  
 11  
 12 " When started as "evim", evim.vim will already have done these settings.  
 13 if v:progname =~? "evim"  
 14   finish  
 15 endif  
 16  
 17 " Bail out if something that ran earlier, e.g. a system wide vimrc, does not  
 18 " want Vim to use these default values.  
 19 if exists('skip_defaults_vim')  
 20   finish  
 21 endif  
```  
  
vim 中命令行输入 `:h  defaults.vim` 查看说明：  
```bash  
defaults.vim E1187  
If Vim is started normally and no user vimrc file is found, the  
$VIMRUNTIME/defaults.vim script is loaded.  This will set 'compatible' off,  
switch on syntax highlighting and a few more things.  See the script for  
details.  NOTE: this is done since Vim 8.0, not in Vim 7.4. (it was added in  
patch 7.4.2111 to be exact).  
  
This should work well for new Vim users.  If you create your own .vimrc, it is  
recommended to add these lines somewhere near the top:  
        unlet! skip_defaults_vim  
        source $VIMRUNTIME/defaults.vim  
```  
  
- 在 `/etc/vimrc` 文件最后加上下面内容，执行 `/etc/vim/vimrc.local` 文件  
创建 `/etc/vim/vimrc.local` 后文件中，将自定义的配置写入其中，可以让该配置全局生效，即所有用户使用    
```vim  
" Source a global configuration file if available  
if filereadable("/etc/vim/vimrc.local")  
  source /etc/vim/vimrc.local  
endif  
```  
  
vim 8.2 版本的初始 vimrc 文件为 `/etc/vim/vimrc`，而且在该文件最后默认加了上面调用 `/etc/vim/vimrc.local` 的命令  
  
  
# 自定义按键映射写法  
![1](https://img-blog.csdnimg.cn/97a9a2e5468f4679907fa521095a30a2.png)  
![2](https://img-blog.csdnimg.cn/954796c63f60475fb78bb993d8fb8edc.png)  
![2](https://img-blog.csdnimg.cn/bd4a98299de24e69b0ae0fd2ea4d98eb.png)  
  
<br/>  
  
- `:h key-notation` 查看帮助文档  
- `<C-G>` 表示按下 `Ctrl` 和 `G` 两个按键  
  
  
# 各种模式的符号  
![1](https://img-blog.csdnimg.cn/0385c35d9c77424cbbea0c33d67e96a0.png)  
  
<br/>  
  
- `:h map-listing` 查看帮助  
  
# 非递归映射  
> [精确映射](https://www.kancloud.cn/kancloud/learn-vimscript-the-hard-way/49311)  
  
  
- `nnoremap inoremap vnoremap` 分别对应普通模式、插入模式和可视模式非递归映射  
  
  
# 取消映射  
![1](https://img-blog.csdnimg.cn/d34f0d7505b44ce69db8ae9ba82f5bb7.png)  
  
<br/>  
  
- `:h :unmap` 查看帮助文档  
- `nunmap iunmap vunmap`  
  
  
# 设置 Leader 键  
> [Leaders](https://www.kancloud.cn/kancloud/learn-vimscript-the-hard-way/49313)  
  
  
![0](https://img-blog.csdnimg.cn/e6c623a4fc094f66af547989949eb8ba.png)  
![1](https://img-blog.csdnimg.cn/0c43c125470043498dbcef02e4fc7cc8.png)  
![2](https://img-blog.csdnimg.cn/1d976b877c8a42adbf24daec58630588.png)  
  
  
- `:h <Leader>` 查看 Leader 键介绍  
- 可以设置很容易按到的空格键为 Leader 键  
- `:h expr-quote` 可以查看特殊字符书写的格式  
- `:h key-notation` 可查看空格键的表示为 `<Space>`  
![3](https://img-blog.csdnimg.cn/9f4d7adbf0314c1c9a04555fff9f36f6.png)  
- `let mapleader = "\<Space>"` 表示设置空格键为 Leader 键  
  
## LocalLeader  
  
![1](https://img-blog.csdnimg.cn/f3602e852e504e4e928ffe04ced3be49.png)  
<br/>  
  
- `:h LocalLeader` 查看帮助文档  
- 利用 `LocalLeader` 为不同语言设置不同的 `Leader  
  
  
# 使自定义设置生效  
- 在自定义配置文件中输入 `:source $MYVIMRC`  
- 可以设置快捷方式映射该命令，每次修改配置后通过快捷方式立即使配置生效  
  
# 设置缩写  
> [Abbreviations](https://www.kancloud.cn/kancloud/learn-vimscript-the-hard-way/49283)  
  
  
![1](https://img-blog.csdnimg.cn/3bded2bc23fd489296b5680f6d1aa6f1.png)  
  
<br/>  
  
- `:h abbreviate` 查看帮助  
  
  
# 文件类型  
  
- `:h FileType` 查看帮助文档  
- `$VIMRUNTIME/filetype.vim` 可查看文件类型  
- c++ 文件类型为 `cpp`  
![1](https://img-blog.csdnimg.cn/5f29a864aa384748a5ed17f475865333.png)- javascript 文件的类型为 `javascript`  
![2](https://img-blog.csdnimg.cn/6178bf74407842f6b69d8b2cd682d381.png)  
<br/>  
t  
  
# 本地缓冲区  
> [本地缓冲区的选项设置和映射](https://www.kancloud.cn/kancloud/learn-vimscript-the-hard-way/49284)  
  
  
- `:h map-<buffer>` 查看帮助文档  
- 如果打开多个文件，只想对一个文件做一些设置，则用 `<buffer` 选项  
  
  
  
# 自动命令 和 自动命令组  
> [自动命令](https://www.kancloud.cn/kancloud/learn-vimscript-the-hard-way/49338)  
> [自动命令组](https://www.kancloud.cn/kancloud/learn-vimscript-the-hard-way/49339)  
  
- 打开 vim 输入 `:h autocmd` 查看帮助  
  
## 创建文件时自动保存  
```bash  
augroup bufRW  
    autocmd!  
    " 自动命令 创建文件时保存  
    autocmd BufNewFile * :write  
augroup END  
```  
  
## 创建 shell 脚本时自动添加注释  
```  
" 自动命令组 为 shell 脚本创建时自动添加说明信息  
augroup shellScriptAutoCmds  
autocmd!  
autocmd BufNewFile *.sh exec ":call AddShellScriptHeader()"  
function! AddShellScriptHeader()  
        call setline(1,"#!/bin/bash")  
        call setline(2,"#")  
        call setline(3,"#********************************************************************")  
        call setline(4,"#Author:            my name")  
        call setline(5,"#Date:              ".strftime("%Y-%m-%d"))  
        call setline(6,"#FileName:          ".expand("%"))  
        call setline(7,"#URL:               http://github.com")  
        call setline(8,"#Description:       shell script")  
        call setline(9,"#Copyright (C):     ".strftime("%Y")." All rights reserved")  
        call setline(10,"#********************************************************************")  
        call setline(11,"")  
        call setline(12,"")  
        call setline(13,"")  
endfunction  
autocmd BufNewFile * :normal G  
augroup END  
```  
  
  
# 查看当前设置  
- `:set number?` 会显示是否行号  
  
# tab 键设置  
## tab 键用空格代替  
- 如果设置了 `:set list`，制表符会显示出来 `^I` 符号；用空格代替制表符后 `:set expandtab`，不会显示制表符号  
![1](https://img-blog.csdnimg.cn/c5e45161ebe046ada5477cf02ced03fe.png)  
<br/>  
  
## 指定 tab 键对应的空格数目  
![1](https://img-blog.csdnimg.cn/cd50ffbf6f674598b84acd8a39efeb76.png)  
<br/>  
  
- 如 `:set tabstop=4`  
  
# 文本缩进设置  
## 设置缩进宽度  
![1](https://img-blog.csdnimg.cn/edfe1e168f634aeea971452df352f556.png)  
<br/>  
  
- `:h 'shiftwidth` 设置缩进宽度，即用 `<<` 或 `>>` 缩进时的宽度  
- 如 `:set shiftwidth=4`  
  
  
# 设置文本宽度  
![1](https://img-blog.csdnimg.cn/52c2a1e62a594a8c888cf1a448440c67.png)  
  
<br/>  
  
- `:set textwidth?` 可查看当前文本宽度  
- 超过所设置的宽度后会换行显示，实际仍属于同一行，屏幕行为两行  
  
# 显示光标所在行列  
> [vim 光标高亮行列的颜色设置](https://blog.csdn.net/iynu17/article/details/51509830)  
  
  
- `:set cursorline`  显示光标所在的行  
- `:set cursorcolumn` 显示光标所在的列  
  
  
# 查看全部 set 设置选项  
![1](https://img-blog.csdnimg.cn/69ec959d3dd74adea819abfaa5721fc1.png)  
  
<br/>  
  
- `:h option-llist` 或 `:set  all` 查看全部选项  
  

# 录制宏  
```vim  
" 宏录制，行末尾添加两个空格  
let @a = "A\<Space>\<Space>\<Esc>"  
```
在选中的一行，按 `@a` 即可执行宏命令  


# 安装插件管理器 vim-plug  
> github：[vim-plug](https://github.com/junegunn/vim-plug)  
  
  
# 安装文本对齐插件 tabular  
> github ：[tabular](https://github.com/godlygeek/tabular)  
> 教程：[Aligning text with Tabular.vim](http://vimcasts.org/episodes/aligning-text-with-tabular-vim/)  
  
  
# 安装 markdown 插件  
## 安装 vim-markdown 插件  
> github：[vim-markdown](https://github.com/preservim/vim-markdown)  
>   
  
- 安装该插件前要先装 tabular 插件  
