Vim 学习  
  
# 安装 Vim 和 NeoVim  
> [How is NeoVim Different From Vim?](https://www.baeldung.com/linux/vim-vs-neovim)  
  
## 安装 Vim  
> [Linux下vim的安装及其设置细节](https://zhuanlan.zhihu.com/p/98031976)  
  
  
## 安装 NeoVim  
> git 官网：[neovim/neovim](https://github.com/neovim/neovim/wiki/Installing-Neovim)  
  
  
# 学习 Vim 资源  
## Vim 命令  
> 在线环境：[蓝桥云课](https://www.lanqiao.cn/courses/2)  
> [vimdoc](https://vimdoc.sourceforge.net/)  
> [Vim 从入门到精通](https://github.com/wsdjeg/vim-galore-zh_cn)  
> [Vim 实用技巧](https://pan.baidu.com/s/108t5WDRtobHHXEQdWpr6vA?pwd=0zxn)  
> [vim user manual](https://pan.baidu.com/s/1nqkUcFNQ81L-JNG2Sqo1LA?pwd=k6aa)  
> vscode 中一个插件，这个教程挺不错：[learn vim](https://marketplace.visualstudio.com/items?itemName=vintharas.learn-vim)  
  
  
- 借助帮助文档，在 shell 中直接输入 `vimtutuor` 可打开入门的帮助文档，跟着练习一遍  
![1](https://img-blog.csdnimg.cn/3ed9acd1632a45b3bf3ca662d4dcb73d.png)  
  
- 在 vim 中输入 `:h vimtutor` 会介绍不同平台查看帮助文档  
![2](https://img-blog.csdnimg.cn/e23c9e3f933f49a1838f7ccecc7fd538.png)  
  
  
## Vimrc 配置  
> [笨方法学Vimscript](https://www.kancloud.cn/kancloud/learn-vimscript-the-hard-way/49321)  
  
  
# vim 内置组合按键含义  
- `vim` 中输入 `:h key-notation`。  
  
- `vim` 中输入 `:h notation` 查看帮助  
  
# 不用自定义配置，用默认配置  
- `vim -u NONE -N` 运行 vim  
  
  
# 定义  
## word  
## WORD  
## sentence  
- `:h sentence`   
![1](https://img-blog.csdnimg.cn/a540f417673a44e38e86cead43069168.png)  
  
  
  
# 普通模式  
## 查看命令的说明  
如果光标所在的单词为 `ls`，按大写 `K`，则会弹出 `ls` 的文档说明，相当于 `man ls`。  
  
![1](https://img-blog.csdnimg.cn/3fba6fed3e7b40428e996f20c23db80d.png)  
  
  
## 查看光标下字符的 ASCII 码  
普通模式下按` ga`，显示该字符的 ASCII，即 get ascii。  
  
![1](https://img-blog.csdnimg.cn/711ef7594f294fd6ab6422237a7c3117.png)  
  
  
## 合并两行  
  
![1](https://img-blog.csdnimg.cn/1d745993f1cc46929b7a6a1949e9426b.png)  
  
<br/>  
  
- `J` 将光标下行和当前行合并   
  
  
## 撤销修改  
![1](https://img-blog.csdnimg.cn/c529a7a81bc046a89851008ad3c4f1dc.png)  
![2](https://img-blog.csdnimg.cn/84ad03d195874f90aaf068c72c5bd046.png)  
  
<br/>  
  
- `u` 撤销一次修改，`2u` 撤销最后 2  次修改  
- `U` 撤销全部修改  
- `CTRL-R` 取消上次通过 `u` 的撤销  
  
  
## 删除  
![1](https://img-blog.csdnimg.cn/c80976e4401849dc81a2e614aa7009ec.png)  
  
<br/>  
  
  
- `:h deleting` 查看所有删除相关命令  
- `D` 相当于 `d$`  
  
  
## 插入文本  
![1](https://img-blog.csdnimg.cn/3d0746792fe147b88077af98dcb058f2.png)  
  
<br/>  
  
- `i` 在当前光标之前插入文本  
- `3i` 在当前光标前插入3次输入的文本，输入文本结束按 <Esc> 键后会看到输入的文本复制了2份  
- `I` 在当前行第一个非空白字符前插入文本  
- `gI` 在当前行最前面（第一列，可能是空白字符）出插入文本，同样前面加数字可以重复插入多次  
- `gi` 上次结束插入的位置插入文本  
  
# 插入模式  
## 复制粘贴  
  
## 做算术运算  
- `CTRL-R_=`  
- `:h i_CTRL-R_=` 查看命令说明  
  
## 字符编码输入非常用字符  
![1](https://img-blog.csdnimg.cn/26330c742fcf473a8ab5fecf1b7741bd.png)  
  
<br/>  
  
## i_CTRL-V  
[What does CTRL+V do in vim?](https://unix.stackexchange.com/questions/366869/what-does-ctrlv-do-in-vim)  
  
  
![1](https://img-blog.csdnimg.cn/fa25bb2e86004035b468aabdb7d7cbb0.png)  
## 切换到普通模式  
- `Esc` 回到普通模式  
- `CTRL-[` 回到普通模式  
- `CTRL-C` 回到普通模式  
- `CTRL-O` 回到普通模式后执行一个命令后回到插入模式  
  
## 插入模式更正错误  
这些快捷键在 bash 中也可用（set -o vi 切换为 vi 模式）  
  
- `CTRL-h` 删除左边的一个字符  
- `CTRL-w` 删除前一个单词  
- `CTRL-u` 删除至行首  
  
# 可视模式  
![1](https://img-blog.csdnimg.cn/554b4c70904143bbbbc3754cb8233468.png)  
  
- 上面三种可视模式中，按同样的按键回到普通模式，按其他可视模式按键切换可视模式类型。  
- 可视模式中按 `o` 切换光标位置，在首尾两端切换。  
  
  
# 命令行模式  
## print 打印指定范围的文本内容  
- `:p` 或 `:print` 在最下方打印当前行。  
- `:3,8p` 打印第 3 行到第 8 行的内容。  
- `:4,$p` 打印从第 4 行到最后一行的内容。  
- `:.,5p` 打印从当前行到第 5 行的内容。  
- `:%p` 打印从第 1 行到最后一行的内容。  
- `:1+p` 打印第2 行，`:2-p` 打印第 1 行。  
- `:.,.+3p` 打印当前行到当前行往下 3 行的内容。  
  
  
## 跳转到特定行  
- `:1` 跳转到第1行，和普通模式输入 `1gg` 或 `1G` 效果相同  
  
  
## copy 复制行  
- `:copy` 和 `:t` 等价  
- `:27t 4` 将第 27 行复制到第 4 行下面  
- `1t .` 将第 1 行复制到当前行下面  
- `:t3` 将当前行复制到第 3 行下面  
- `:t.` 复制当前行并粘贴到当前行下面  
- `t0` 将当前行复制到第 1 行上面  
  
  
## move 移动行  
- `:move` 和 `:m` 相同  
- `1m 9` 将第 1 行移动到第 9 行的位置，原来的第 9 行变成第 8 行  
- `20m9` 将第 20 行移到第 9 行下面，原来的第 10 行变成第 11 行  
- `m28` 将当行移到第 28 行处（当前行在 28 行前），或者移到第 28 行下面（当前行在第 28 行后）  
-   
  
   
## 选定范围执行 normal 模式命令  
  
![1](https://img-blog.csdnimg.cn/2ce76e72e17e4819af4ae9da40710e6f.png)  
  
![2](https://img-blog.csdnimg.cn/b23c1e878ba54155b01fedef25f4c467.png)  
<br/>  
  
## 重复上次 Ex 命令  
- `:@:` 重复上次 Ex 命令  
  
  
## 自动补全 Ex 命令  
- `CTRL + D` 自动补全 Ex 命令  
- `: h c_CTRL-D` 查看快捷键介绍   
![1](https://img-blog.csdnimg.cn/6dfe695905004881bf02d5de11d7de13.png)  
- `Tab` 按键可以在不同选项之间切换，`Shift + Tab` 反向遍历选择  
![2](https://img-blog.csdnimg.cn/7d905aacbee14340b58d9a40f178f4ce.png)  
  
## 命令行中插入光标下的 Word  
  
- `CTRL-R CTRL-W` 组合快捷键  
- `c_CTRL-R_CTRL-W` 查看快捷键说明  
  
![1](https://img-blog.csdnimg.cn/fa59339bdff14fef8afcbc6a0625e1d0.png)  
  
  
  
![1](https://img-blog.csdnimg.cn/5a37c8168b0b4501814d7487a91d8572.png)  
![2](https://img-blog.csdnimg.cn/83eb25afc61b44ccaef15315d9954e41.png)  
![3](https://img-blog.csdnimg.cn/5e6d812669b04e1f9f5763f809853d9b.png)  
  
## 查看历史 Ex 命令  
- `: ` 上下方向键查看  
- `q:` 在普通模式打开 Ex 历史命令窗口，`:q` 关闭该窗口  
- `CTRL-F` 在命令行模式切换到命令行窗口  
  
  
## 打开历史查找命令的窗口  
- `q/` 在普通模式查看历史查找命令  
- `:q` 关闭该窗口  
- `CTRL-F` 在命令行模式切换到命令行窗口  
  
  
## 执行 Shell 中的程序  
- `!ls` 执行 Shell 中的 `ls` 命令  
  
## 切换到 Shell  
- `:shell` 将 Vim 置于后台，回到 Shell 中  
- `exit` 退出 Shell，回到 Vim  
  
## 缓冲区的内容作为标准输入输出  
- `:read !ls` 或 `:r !ls` 将 `ls` 输出内容复制到当前行下  
- `:write !sh` 或 `:w !sh` 将当前缓冲区内容作为 `sh` 命令的输入  
  
  
## 使用外部命令过滤文本内容  
![1](https://img-blog.csdnimg.cn/16efecee555e41e39d580a00e077af68.png)  
![2](https://img-blog.csdnimg.cn/adb535f4e43d45e88af5a7a1c58fca65.png)  
![3](https://img-blog.csdnimg.cn/7c77c5fece884f6090aa9e3259773f85.png)  
  
  
## 批处理运行 Ex 命令  
  
  
  
## 用 root 权限保存 vim 修改的文档  
> [How does the vim "write with sudo" trick work?](https://stackoverflow.com/questions/2600783/how-does-the-vim-write-with-sudo-trick-work)  
  
普通用户编辑一个需要 root 权限的文档时，不能直接用 `:w` 保存，此时可以在命令行输入  
`:w !sudo tee % > /dev/null` 保存  
  
后面的 `> /dev/null` 将标准输出的内容不显示，因为 `tee` 命令会将当前 vim buffer 的内容显示到标准输出  
  
`%` 表示当前的文档名  
  
# 模式切换  
## 插入模式下切换回普通模式  
- Esc  
- Ctrl-[  
- CTRL-C  
- Ctrl-O  
切换到普通模式后输入一个命令后回到插入模式  
输入 `:h i_CTRL-O` 查看该组合按键的解释  
![1](https://img-blog.csdnimg.cn/34f5a503300c4c4b82e2004ecbb478b9.png)  
# 管理多个文件  
## :ls 查看缓冲区全部文件列表  
- `:h ls` 可查看符号 `%` `a` 等的含义  
![1](https://img-blog.csdnimg.cn/afbf68c431c44fe3a51934944671b4b9.png)  
![2](https://img-blog.csdnimg.cn/fa148fa623d24522abba36b7763c6e5b.png)  
  
  
## 不同文件之间切换  
- `bfirst` 或 `bf` 切换到第一个文件  
- `blast` 或 `bl` 切换到第一个文件  
- `bprev` 或 `bp` 切换到列表中上一个文件  
- `bnext` 或 `bn` 切换到列表中下一个文件  
- `b2` 切换到列表序号为 2 的文件  
- `b` 是 `buffer` 的简写，`buffer3` 和 `b3` 等价，切换到编号为 3 的文件  
  
![1](https://img-blog.csdnimg.cn/28945cb9aec8414088ce324d273416f2.png)  
  
******************  
  
- 如果一个文件编辑了但未保存，切换时会提示，强制切换则需要加后缀 `!`  
- 未保存的文件切换到其他文件后，查看列表时有 `+`  
- 再次切换会已修改但未保存的文件时，上次编辑的内容还在  
  
![2](https://img-blog.csdnimg.cn/d3c2954a121441758f21bfcb04789c07.png)  
  
## 删除缓冲区的内容  
- `bdelete 1` 或 `bd 1` 删除缓冲区列表中编号为 1 的内容  
- 从缓冲区删除，并不是删除该文件  
- 如果缓冲区的内容被修改，且已经保存（写入到文件中），则删除后文件的内容已经更新   
- 如果缓冲区的内容被修改，但未保存，删除会提示，`bd! 1` 加上 `!` 可强制删除，删除后文件的内容未更新  
- `bd 2` 和 `2 bd` 等价  
- `3,5 bd` 删除编号 3，4，5 的缓冲区内容，如果 4 不存在则跳过  
  
  
## args 向缓冲区添加文件  
- `args {3..5}.txt` 向缓冲区添加 `3.txt 4.txt 5.txt` 三个内容，可以是已存在的文件，或是不存在的文件  
  
  
## 读写缓冲区  
- `w[rite]` 将缓冲区的内容写入到磁盘的文件中  
-  `e[dit]!` 将磁盘文件的内容读入缓冲区，如果是当前文件，则表示丢弃当前缓冲区未保存的修改；如果是未在缓冲区列表中内容，则读入缓冲区  
- `q[uit]!` 不保存退出  
- 普通模式输入 `ZQ` 和 `:q!` 效果相同  
- `qa[ll]!` 关闭所有窗口，摒弃所有修改而无需警告  
- `wa[ll]!` 将所有改变的缓冲区的内容写入磁盘  
- `:x` 保存并退出  
- 普通模式输入 `ZZ` 和 `:x` 相同效果  
- 命令后加 `!` 表示强制执行  
  
  
## 给文件加密  
![1](https://img-blog.csdnimg.cn/1acd2b209c7344c78ea368daca4084c8.png)  
  
<br/>  
  
- `:X` 会要输入密码，保存后下次打开文件需要输入密码  
- `:X` 弹出输入密码提示时，直接回车，则无需密码  
  
  
## 相对于活动文件目录打开文件  
- `e[dit] %<Tab>`，`%` 代表活动缓冲区的文件名，按 `Tab` 键将填充文件名  
  
  
  
  
# 窗口管理  
  
## 切分窗口  
- `CTRL-W_s` 水平切分窗口（上下），窗口显示当前缓冲区，`:h CTRL-W_s` 查看帮助  
- `CTRL-W_v` 垂直切分窗口（左右），窗口显示当前缓冲区  
- `sp[lit] {file}` 水平切分当前窗口，新窗口载入文件 file，如果没有指明文件，则显示当前缓冲区内容  
- `vsp[lit] {file}` 垂直切分当前窗口，新窗口载入文件 file，如果没有指明文件，则显示当前缓冲区内容  
  
  
  
## 在窗口间切换  
- `:h window-move-cursor` 查看帮助文档  
- `CTRL-W_j` 切换到下面的窗口  
- `CTRL-W_h` 切换到左边的窗口  
- `CTRL-W_k` 切换到上边的窗口  
- `CTRL-W_l` 切换到右边的窗口  
- `CTRL-W_w` 在窗口间循环切换  
  
## 关闭窗口  
- `clo[se]` 命令模式关闭活动窗口  
- `CTRL-W_c` 普通模式关闭活动窗口  
- `on[ly]` 命令模式只保留活动窗口，关闭其他窗口   
- `CTRL-W_o` 普通模式只保留活动窗口，关闭其他窗口  
  
## 改变窗口大小  
- `:h window-resize` 查看帮助文档  
- `CTRL-W_=` 使所有窗口等宽、等高  
- `CTRL-W {N}-` 使当前活动窗口**高度减小** N（无则默认 1）  
- `CTRL-W {N}+` 使当前活动窗口**高度增大** N（无则默认 1）  
- `CTRL-W _` 使当前活动窗口**高度最大化**  
- `CTRL-W {N}_` 设置当前窗口**高度为N**  
- `z{N}CR` 设置当前窗口**高度为N**  
***********  
- `CTRL-W {N}<` 使当前活动窗口**宽度减小** N（无则默认 1）  
- `CTRL-W {N}>` 使当前活动窗口**宽度增大** N（无则默认 1）  
- `CTRL-W |` 使当前活动窗口**宽度最大化**  
- `CTRL-W {N}|` 设置当前活动窗口**宽度为N**  
  
  
## 打开文件  
- `e[dit] {file}` 打开相对于当前工作目录的文件  
- `pwd` 打印当前工作目录  
  
  
  
  
#  在文档中移动  
## 上下左右移动 —— 实际行和屏幕行  
- `h j k l` 跳转到屏幕行  
- `gh gj gk gl` 跳转到屏幕行  
  
![1](https://img-blog.csdnimg.cn/67efd7064b5e454699b44a495c853093.png)  
***************  
  
- `0 ^ $` 分别跳转实际行的行首，行首第一个非空白字符，行尾  
- `g0 g^ g$` 分别对应屏幕行的相应功能  
![2](https://img-blog.csdnimg.cn/12949eed31ca41108e824ba4679a8541.png)  
![3](https://img-blog.csdnimg.cn/f250030629534be187170d0fc078952c.png)  
![4](https://img-blog.csdnimg.cn/18b7bff70ae645f5b7ad27bbb66254d8.png)  
  
  
## 区分单词（word）和字串（WORD）  
- `:h word` 查看帮助文档  
  
![1](https://img-blog.csdnimg.cn/7395f2d04e964c2f9a3a697cd586f57e.png)  
![2](https://img-blog.csdnimg.cn/89f05833157b47dc9cbf952c4ec8295f.png)  
  
  
## 基于单词（word）移动  
- w  
移动到下一个单词的开头  
- b  
光标在当前单词开头，则移到前一个单词开头；否则移动到当前单词开头  
- e  
光标在当前单词末尾，则移到下一个单词末尾；否则移动到当前单词末尾  
- ge  
移动到前一个单词末尾  
  
## 基于字串（WORD）移动  
- `W B E gE` 对于 word 的功能，只是跳转从单词改为字串  
  
  
## 基于句子和段落移动  
  
![1](https://img-blog.csdnimg.cn/8e80722da3e44575ae8419bda826b65c.png)  
  
<br/>  
  
  
- `(` 和 `)` 分别跳到上一句和下一句  
- `{` 和 `}` 分别跳到上一段和下一段  
  
  
## 上下翻页  
![1](https://img-blog.csdnimg.cn/93c03174aba3446f9ff62f010a254c31.png)  
![2](https://img-blog.csdnimg.cn/5b2017a35723454b8e892c1020b48202.png)  
  
<br/>  
  
- `CTRL-U` page up，向上翻半页  
- `CTRL-D` page down，向下翻半页  
- `CTRL-B` page backward，向上翻一页  
- `CTRL-F` page forward，向下翻一页  
  
  
  
## 定位到特殊位置  
![1](https://img-blog.csdnimg.cn/e5899bef7df34a4b9960267ab2820188.png)  
![2](https://img-blog.csdnimg.cn/a44fa9165b354911812649e4ea84c081.png)  
  
<br/>  
  
- `H` 光标移到当前窗口第一行的第一个非空白字符处  
- `M` 光标移到当前窗口中建行的第一个非空白字符处  
- `L` 光标移到当前窗口最后一行的第一个非空白字符处  
  
*************  
- `z<CR>` 让当前行处于窗口最上方，光标位于第一行的第一个非空白字符处  
- `zt` 让当前行处于窗口最上方，但光标仍在相同的列，即在原来的字符 处  
- `z.` 让当前行位于窗口正中间，光标移到当前行的第一个非空白字符处  
- `zz` 让当前行处于窗口中间，但光标保持在原来的列处  
- `z-` 让当前行处于窗口最下方，光标移到当前行的第一个非空白字符处  
- `zb`，和 `z-` 相同，但光标和原来的列相同  
***********  
- `z{height}<CR>` 调整当前窗口的高度为 `{height}`  
  
  
# 查找  
## 一行中查找字符  
- f {char}   
	- 如果输入 `fa` ，则从光标所在位置开始，向**右**查找字符 `a`，按 `;`可以跳到下一个（右边）字符 `a` 所在处，直到该行（实际行）最后一个字符，到最后一个后不能反向查找  
	- 按 `,` 才能向**左**跳转查找  
  
- F {char}  
	 - 与 f {char} 相反，默认向**左**查找，`;` 向左跳转到下一个符合字符处，`,` 向右跳转到符合的字符处  
  
- t {char}  
	- 查找方向与 f {char} 相同，但**光标在查找字符的前一个字符处**  
	  
- T {char}  
	 - 查找方向与 F {char} 相同，但**光标在查找字符的后一个字符处**  
  
****************  
查找命令与其他动作命令结合：  
![1](https://img-blog.csdnimg.cn/f124ba281e844ee9bd96753b7c52311f.png)  
  
## 全文查找  
- `/` 进入命令行模式，输入待查找的单词，然后按回车键，全文查找  
- `n` 向右查找下一个符合的单词  
- `N` 向左查找下一个符合的单词  
  
***********  
  
查找单词然后操作：  
可以通过 `v` 切换到可视模式，然后用 `/` 在命令行输入查找单词，光标会跳转到找到单词的首字符上，并且将当前光标位置到查找到位置选中，这是可以用 `d` 删除该部分内容。  
  
  
# 选择特定区域  
  
![0](https://img-blog.csdnimg.cn/ec6e0d02b75b4b4397d6afd9f546cf82.png)  
![0](https://img-blog.csdnimg.cn/2c21134f14ee4af5bde1f5b2a3dcfa4a.png)  
  
  
- `:h text-objects` 查看帮助文档  
![·](https://img-blog.csdnimg.cn/5c12d8a2fef24abb82b30b2bc0e53b4d.png)  
   
 - aw 和 iw  
 ![2](https://img-blog.csdnimg.cn/4564ac1a09bc4bde86b006ff9bde4f67.png)  
  
- a" 和 i"  
- a( 和 i(  
- a{ 和 i{  
- a< 和 i<  
- a[ 和 i[  
- at 和 it  
![3](https://img-blog.csdnimg.cn/ab2f2853bb3e4b0da683e519b2600bc4.png)  
![4](https://img-blog.csdnimg.cn/6f1e943f63464298b00f027a2c6ba0bf.png)  
  
   
  
# 设置标记  
 ![1](https://img-blog.csdnimg.cn/c53c06679ca44334b47f7bff154c5013.png)  
![2](https://img-blog.csdnimg.cn/ae0ce421dff24903a6207cbd46e051ce.png)  
![3](https://img-blog.csdnimg.cn/4bffd55628ae491da5a6311b2535672d.png)  
  
<br/>  
  
- `:h mark-motions` 查看帮助文档  
- `m{a-z} 小写的标记只在本文件中使用  
- `m{A-Z} 大写的标记可以跨文件使用  
***********  
- `ma` 设置标签，`'a` 将光标跳转到设置的标签所在行的行首的第一个非空白字符上；**`a** 将光标跳转到标签所在的具体字符处（行和列）  
  
**************************  
- `:marks` 列出当前全部标签  
- `:marks a` 列出标签 a 的位置  
  
********************  
- `delm[arks] a` 删除标签 a  
- `delm[arks]!` 删除当前缓冲区的全部标签，除了大写字母和数字标签  
  
  
# 在匹配的括号间跳转  
![1](https://img-blog.csdnimg.cn/a414b7b3dfa544cd9c4179b483995439.png)  
  
<br/>  
  
- `:h %` 查看帮助文档  
- `%` 跳转到下一个括号处  
  
  
# 文件内跳转  
  
![1](https://img-blog.csdnimg.cn/cb540b5fcd3541a096db1ebb2d261f49.png)  
<br/>  
  
- `CTRL-O` 跳转到上一个位置  
- `CTRL-]` 跳转到单词所在的定义处，类似 windows 中的超链接，但没有超链接的地方也会查找该单词所在的定义处跳转。  
  
# 查看缓冲区所作的修改  
- `:h changes` 查看帮助文档  
![1](https://img-blog.csdnimg.cn/0134eeaeb57141519d03b83808c71071.png)  
- `changes` 查看修改  
![2](https://img-blog.csdnimg.cn/980e82f21e6049abb5751b54e1acf7bf.png)  
- `g;` 和 `g,` 命令来反向或正向遍历修改的位置  
- `g;` 会跳转到上次完成编辑的位置  
  
  
# 复制 粘贴 删除  
- `d` 表示 delete 删除，后面跟范围  
- `y` 表示 yank 赋值，后面跟范围  
- `p` 表示 put 粘贴，粘贴在光标后  
- `P` 粘贴在光标前  
  
*********  
  
- `yy` 复制整行  
- `dd` 删除整行  
- 如果整行，`p` 粘贴在本行下面，`P` 粘贴在本行上一行处  
  
************  
`gp` 和 `gP` 粘贴后光标位于最后一行而非第一行，粘贴多行文本时 `p` 和 `gp` 差异显著  
  
  
## Paste 模式  
  
![1](https://img-blog.csdnimg.cn/e1626a83a7044ff6afc550b878d9b684.png)  
  
  
  
  
## 与系统剪贴板互动  
> [Accessing the system clipboard](https://vim.fandom.com/wiki/Accessing_the_system_clipboard)  
  
将系统剪贴板的内容复制到 vim 编辑的文档中，或者在不同的 vim 编辑的文档中复制粘贴  
  
- 需要安装 `vim-gtk`   
  
例如 WLS ubuntu 20.04 中安装插件：  
```bash  
apt update && apt install -y vim-gtk  
```  
  
安装插件后，可以在用 vim 编辑一个文档时选择文本后复制到 `+` 寄存器中，如 `"+yy` 将当前行复制到系统剪贴板，随后可以在另一个文档中用 `"+p` 粘贴，或者到记事本等其他地方粘贴  
  
  
WLS ubuntu 22.04 中查看剪贴板  
```bash  
root@LAPTOP-VB238NKA:/etc/apt# vim --version | grep clipboard  
+clipboard         +keymap            +printer           +vertsplit  
+emacs_tags        +mouse_gpm         -sun_workshop      +xterm_clipboard  
```  
  
- `+` 和 `*` 寄存器的区别  
> [In Vim what is the difference between "+ and "* registers?](https://superuser.com/questions/624231/in-vim-what-is-the-difference-between-and-registers)  
  
  
  
  
  
  
## 粘贴时保留原格式  
  
# 寄存器  
## `""` 无名寄存器  
  
![1](https://img-blog.csdnimg.cn/3ecca76ea5c945658171630c209df6f2.png)  
  
<br/>  
  
- `:h quote_quote` 查看帮助文档  
- `""` 为无名寄存器，为默认寄存器  
- `x, s, d{motion}, c{motion}, y{motion}` 默认均改变无名寄存器的内容  
  
## `"0` 复制专用寄存器  
  
![1](https://img-blog.csdnimg.cn/ad65a92b48ae4ac0af86272ef0706e32.png)  
  
<br/>  
  
- `:h quote_number` 查看帮助文档  
- `y{motion}` 的内容默认写到复制专用寄存器中（也会写入无名寄存器）  
- `"0p` 粘贴复制专用寄存器的内容  
  
  
## `"a - "z` 有名寄存器  
  
![1](https://img-blog.csdnimg.cn/7a714280de5747a4b595592a650b28cb.png)  
  
<br/>  
  
- `:h quote_alpha` 查看帮助文档  
- `"ayaw` 将当前单词复制到寄存器 `a` 中，通过 `"ap` 粘贴  
  
## 黑洞寄存器  
  
![1](https://img-blog.csdnimg.cn/ce8ae7cde0d04671be508689fb4802f1.png)  
  
  
- `:h quote_` 查看帮助文档  
- `"_` 为黑洞寄存器，内容不会影响任何其他寄存器  
- `"_dd` 删除改行的内容，且不覆盖无名寄存器的内容   
  
  
## `"=` 表达式寄存器  
  
![1](https://img-blog.csdnimg.cn/dc4760bda17e46dda518fbce89ef1805.png)  
  
- `:h quote=` 查看帮助文档  
- `"=` 表达式寄存器  
  
******************  
表达式寄存器的使用：  
- 插入模式下做算数运算  
插入模式按 `CTRL-R =` 后在命令行输入算术表达式，再按回车，将计算结果显示在光标位置  
  
  
## 其他寄存器  
  
![1](https://img-blog.csdnimg.cn/a5fe415c6a5b4713b30d3cd0a61d22c4.png)  
<br/>  
  
- 普通模式下，输入`"%p` 将当前文件路径粘贴到光标后  
  
  
  
  
## 查看寄存器的内容  
  
![1](https://img-blog.csdnimg.cn/5ec4b2ec9fbe4630a7502f9cbcea6934.png)  
  
- `:reg "0` 查看复制专用寄存器的内容  
- `:reg ""` 查看无名寄存器的内容  
- `:reg` 查看全部寄存器的内容  
  
  
## 插入模式使用寄存器内容  
  
  
![1](https://img-blog.csdnimg.cn/e4404c1f46cc4e8a81d9a6ab32f9178d.png)  
  
  
- `:h i_CTRL-R` 查看帮助文档  
- `CTRL-R 0` 插入复制专用寄存器的内容  
  
  
## 应用  
  
### 交换两个词  
![1](https://img-blog.csdnimg.cn/8fbc0fb6bfd444f7bab2b53389f88c1e.png)![2](https://img-blog.csdnimg.cn/8de551112b644696b81246528c41ff31.png)  
  
  
### 将文件中的内容粘贴到命令模式中  
先将文件中的内容复制到某个寄存器中，如 `"ryy` 当前行复制到寄存器 r 中，然后 `:` 到命令行模式，按 `CRTL-R r` 即可粘贴寄存器的内容  
  
  
# 宏  
## 将命令录制成宏  
  
![1](https://img-blog.csdnimg.cn/9f0a40aa602a4bd9af16f17f3a67a602.png)  
  
<br/>  
  
  
- `:h q` 查看帮助文档  
- `q{register}` 录制宏  
- 录制结束后按 `q`  
- 如果录制结束后再次录制宏到同样的寄存器，则覆盖原来寄存器的内容  
  
## 查看录制的宏  
  
![1](https://img-blog.csdnimg.cn/6068b0529a1e460099ff7f30371f5ab1.png)  
  
<br/>  
  
  
- 如果录制宏到寄存器 `a`，即 `qa` 命令，则录制结束后用 `:reg a` 查看录制的宏  
- 例如录制一个宏，在最后添加 `;`，然后在最前面添加 `#`   
![2](https://img-blog.csdnimg.cn/ed9b9dab2ac74b2b9a31cc91ae39147f.png)  
  
<br/>  
  
## 执行寄存器的内容来回放宏的内容  
  
![1](https://img-blog.csdnimg.cn/a1d2f89af7e04ec989e8699f1933e1d5.png)  
  
<br/>  
  
- 如果录制到寄存器 `a` 中，则通过 `@a` 可以执行录制的内容  
- 通过 `@@` 可以执行上次调用的宏  
  
  
## 批量修改  
- 如果有规律的批量修改内容，如每行最后添加分号，如录制在 `a` 寄存器中，有其他连续文本需要同样的操作，有两种方法：  
	- 录制完添加分号的指令后，加一个向下一行的指令。如果从某行到向下连续 5 行重复该操作，则执行 `5@a`。  
	- 录制完添加分号的指令后结束录制，用 `V` 指令进入可视模式，选择需要执行的行，然后输入 `:` 进入命令行模式，此时已填充高亮选择的返回，加上 `normal @a`，则选中的行全部执行 `a` 寄存器的指令。  
- 如果批量执行时，在某行执行失败则终止执行。  
  
  
## 在寄存器中追加指令  
- 如果已录制宏到寄存器 `a` 中，可通过 `qA` 向寄存器 `a` 中追加指令，而不覆盖。  
  
  
## 多个文件中执行宏  
  
## 录制递增的数字  
- 初始：  
![1](https://img-blog.csdnimg.cn/71a31697cb4d434ba06c9ecf20077ba3.png)  
- 最终：  
![2](https://img-blog.csdnimg.cn/f0714e5ed9bf434bad1517f6c1df7133.png)  
- 过程  
	- 先设置变量 `i`   
![3](https://img-blog.csdnimg.cn/dc91335fb3364eabbf39c5e61991b62d.png)  
	- 开始录制宏到寄存器，如 `a`，在最前面添加 `1) `，然后切换到普通模式，再将变量 `i`    加 1，即 `:let i+=1`，最后结束录制。  
	- 向下一行，通过 `VG` 选择当前行到最后一行，输入 `:` 进入命令行模式，会自动填充选中行范围，然后输入 `normal @a`，将选中行全部执行寄存器 `a` 中的指令。  
  
  
## 将宏的内容复制到文本中  
  
![1](https://img-blog.csdnimg.cn/3645126ad9d74919989549440c8eacb0.png)  
<br/>  
  
- `:h put` 查看帮助文档  
- `"a p[ut]` 将寄存器 `a` 的内容粘贴到光标后  
- `:put a` 将寄存器 `a` 的内容粘贴到光标下面一行  
  
## 将编辑的宏内容复制到寄存器中  
- 先在文本中编辑宏的内容  
- `"add` 将宏的内容删除并保存到寄存器 `  
  
  
  
# 模式  
## 设置大小写敏感  
  
![1](https://img-blog.csdnimg.cn/148fed7f1a6847168f7b176488873e64.png)  
  
<br/>  
  
- `set ignorecase` 忽略大小写  
  
## 查找时不区分大小写  
- `/a\c` 查找 `a` 且不区分大小写，利用 `n` 和 `N` 分别向前和向后查询  
- `/a\C` 区分大小写查找 `a`   
  
##  查找时智能调整是否区分大小写  
  
![1](https://img-blog.csdnimg.cn/dfb3236482e7439295e8ab3cc12162b0.png)  
  
<br/>  
  
- `:h smartcase` 查看帮助  
- `:set smartcase` 开启设置  
- `:set ignorecase` 开启忽略大小写设置  
- 如果查找字符包含大写字母，`ignorecase` 设置将被忽略，查找将区分大小写  
- 如果查找字符全部不包含大写字母，则忽略大小写  
  
  
## 元字符  
  
![1](https://img-blog.csdnimg.cn/f4c8884d4146483fabad980625ce471d.png)  
  
<br/>  
  
- `:h pattern-atoms` 查看帮助文档  
  
## very magic 模式  
  
![1](https://img-blog.csdnimg.cn/0f852361b069420baf181f17781b745f.png)  
  
  
<br/>  
  
- `:h \v` 查看帮助文档  
- `0-9 a-z A-Z _` 以外的字符均有特殊含义  
![2](https://img-blog.csdnimg.cn/3a33a3b85eca44569a762c1cdfbac924.png)  
- 有些字符本身并没有特殊含义，如 `#`，则保留原本含义，使用本身暂时无需转义  
  
不用 very magic 模式：  
```bash  
%s/\(\S\)\s\{2,\}$/\1/g  
```  
  
用 very magic 模式：  
```bash  
%s/\v(\S)\s{2,}$/\1/g  
```  
  
## 利用字符集简化书写  
  
![1](https://img-blog.csdnimg.cn/4f84037fb4434de28908e60829bcd2a2.png)  
  
<br/>  
  
- `:h /character-classes` 查看帮助文档  
  
  
## very nomagic 模式  
  
![1](https://img-blog.csdnimg.cn/a96a0408de0740a599083805ebf36c05.png)  
  
<br/>  
  
- `:h \V` 查看帮助文档  
- 正向查找 `/` 和反向查找 `?` ，结束符 `$` ，反斜杠 `\` 仍需要转义  
  
  
## 圆括号捕获子匹配  
  
![1](https://img-blog.csdnimg.cn/07fe21685bdb41059261aef2ff00ce49.png)  
![2](https://img-blog.csdnimg.cn/945af09254e14b639c128d31bda12ac8.png)  
![3](https://img-blog.csdnimg.cn/2c297938092945bbb5d1cce744ae1c9e.png)  
  
<br/>  
  
- `:h \_` 可查看帮助文档，`\_` 表示匹配的字符集中加上换行符，因此 `\_s` 表示空白字符加换行符。  
  
  
## 圆括号匹配但不捕获其内容  
  
- `/\v%(a|b)cd`，圆括号匹配 `a` 或 `b` 但不捕获，因为前面加了 `%`  
## 界定单词的边界  
  
- 查找时不确定边界，如下，指向查找 `the`，但将 `these` 也包含了：  
![1](https://img-blog.csdnimg.cn/7aba2ee4a7ea409b9b12fa2b0ec50583.png)  
- 通过 `<>` 确定边界：  
![2](https://img-blog.csdnimg.cn/30d5e00f8d2448858e5c3254d6fcc565.png)  
  
<br/>  
  
## 界定匹配的边界  
  
![1](https://img-blog.csdnimg.cn/24aa9cacc2854a2fa516fe4cf326c5b4.png)  
  
  
<br/>  
  
- `zs` 即 `zoom start`；`ze` 为 `zoom end`  
- `\zs` 和 `\ze` 分别匹配起始和结束处  
  
![2](https://img-blog.csdnimg.cn/5ff0d86321a846389c305ed03d688957.png)  
   
 ## 以编程的方式转义字符  
  
![1](https://img-blog.csdnimg.cn/c09b0be4e4fb4c51829f75cb9bb34ec5.png)  
  
<br/>  
  
# 查找  
## 正向查找和反向查找命令  
  
![1](https://img-blog.csdnimg.cn/ff84d58a8f494728ac0eca410fe906d1.png)  
![2](https://img-blog.csdnimg.cn/29d3defb74344240b97897fd07f47fce.png)  
  
<br/>  
  
- `/` 和 `?` 分别为正向查找和反向查找  
- `n` 和 `N` 分别跳转到下一个和上一个匹配处  
- 默认查找到最后一处匹配位置后跳转到第一个匹配处，可以通过 `:set ws` 或 `:set nows` 来开启或禁用该功能  
- `q/` 可以打开历史查找命令的窗口，`:q` 回车退出该窗口  
  
## 高亮匹配的查找内容  
  
![1](https://img-blog.csdnimg.cn/7574a1e362004d66b0b7b9791602af1e.png)  
![2](https://img-blog.csdnimg.cn/0f717d46e56d4f078b6e2e0046ec6450.png)  
  
<br/>  
  
- `:se[t] hls[earch]` 开启高亮查找的内容，`se[t] nohls[earch]` 关闭高亮查找的内容  
- `:noh[lsearch]` 临时关闭高亮查找的功能，但下次查找任然高亮  
  
## 一边查找一边匹配  
  
![1](https://img-blog.csdnimg.cn/38ebf1ec35fd49aab2515d85d5fbc743.png)  
  
<br/>  
  
- `:set i[nc]s[earch]` 开启功能，`:set noi[nc]s[earch]` 关闭功能  
  
## 将光标定位在匹配到的单词的其他位置  
  
![1](https://img-blog.csdnimg.cn/b0ef8699977c406ea72222ba019c6054.png)  
  
<br/>  
  
- `:h search-offset` 查看帮助文档  
- `/the` 回车后默认光标在匹配到单词的首部即 `t` 上，`/the/e` 则光标在单词尾部 `e` 上  
  
  
## 操作匹配的内容  
  
![1](https://img-blog.csdnimg.cn/3f407aecae764d6eb168d8646a18fb10.png)  
  
<br/>  
  
- `gn` 命令  
- 如果查找单词 `\the` 按回车后，光标在匹配单词的首字母 `t` 上，此时按 `gn`，则将该单词完整的选中，此时可以操作该单词，如按 `gU` 换成大写，再按 `n` 转到下一个匹配处，按 `.` 重复之前操作。  
  
## 统计匹配到的个数  
  
- `:%s/vim//gn`，在整个文本查找 `vim`，替换域为空，标志位 `n` 表示不替换，只统计匹配的个数  
  
![1](https://img-blog.csdnimg.cn/ec025df6d70248e296e7d9ebc46968d0.png)  
  
如果查找模式为空，则使用上次的查找模式，对于复杂的查找，可以先查找，然后用 `n` 标识符不实际替换  
```vim  
:%s///gn  
```  
  
# 替换  
  
![1](https://img-blog.csdnimg.cn/7157357670654577a871643bbcafad5d.png)  
  
- `:h substitute` 查看帮助文档  
- `q:` 打开替换的历史窗口，`:q` 退出窗口，和 `Ex` 命令的历史纪录在一起  
  
  
## 分隔符  
![1](https://img-blog.csdnimg.cn/aeea8f9317cb42dfa419b203ecbe7d42.png)![2](https://img-blog.csdnimg.cn/87e12418a8ac4eb08280caee325be889.png)  
  
<br/>  
  
  
- 默认用 `/` 作为分隔符，但也可以是别的  
- 分隔符说明，可以在 `pattern-delimiter` 处按 `CTRL-]` 跳转到该定义处  
- 如果查找替换的内容中包含 `/`，则可以换为其他的符号  
  
## 标志位  
  
![1](https://img-blog.csdnimg.cn/8baba9fcd7ac4c48985811fb756682a2.png)  
![2](https://img-blog.csdnimg.cn/d03ea4e2913d40ca8377929d51c02ce8.png)  
![3](https://img-blog.csdnimg.cn/5cf60e6b405940c3b9d74ce780a4d8c1.png)  
  
<br/>  
  
- `:h s_flags` 查看帮助文档  
  
  
## 替换域中的特殊字符  
  
![1](https://img-blog.csdnimg.cn/fd8720d352704f74ac33b08b359ca16f.png)  
![2](https://img-blog.csdnimg.cn/9e2eca011511415d9a318197de90fc9f.png)  
![3](https://img-blog.csdnimg.cn/ca391835c1354ec2abf8d0d77f216ab1.png)  
  
<br/>  
  
- `:h sub-replace-special` 查看帮助文档  
  
## 文件的整个范围内查找并替换  
  
- 默认 `:s` 作用范围为当前行  
- 加上标志位 `g` 可替换**整行**里全部匹配的内容，默认只替换当前行的第一个匹配处  
- 指定范围 `%` 可以全文查找替换  
- `:%s/m/a/g` 将**全文中所有**的 `m` 替换为 `a`   
- `:%s/m/a` 将全文中查找到的**所有行的第一个匹配**的 `m` 替换为 `a` ，改行其他的匹配处不处理  
  
## 每次替换均询问  
  
![1](https://img-blog.csdnimg.cn/cca4b9df8999488296ad69fdc1d355d9.png)  
![2](https://img-blog.csdnimg.cn/c3f1a215c9fd448696f907d3942ed6dc.png)  
![3](https://img-blog.csdnimg.cn/8a1015f8bf2348b982cdda5efa0306bd.png)  
  
<br/>  
  
- 用标志位 `c` 实现  
  
  
## 重复上次的查找模式  
  
- 查找域为空，则重复上次的查找域  
  
## 用寄存器的内容替换  
  
![1](https://img-blog.csdnimg.cn/90062c90351049ae9a61f6156f33bb3e.png)  
![2](https://img-blog.csdnimg.cn/fb750c30afee4aca9b566433d6698d15.png)  
  
<br/>  
  
## 重复上次的替换命令  
  
![1](https://img-blog.csdnimg.cn/05960221b00c465d9e892286c61a6831.png)  
![2](https://img-blog.csdnimg.cn/79a70b5d36a84796bbbb4250226bbad4.png)  
![3](https://img-blog.csdnimg.cn/e52a0fae673446ff8a846368a96babd6.png)  
  
<br/>  
  
- `g&` 命令可以在整个文件范围内重复上次替换命令  
- `:&&` 只作用于当前行，可以在可视模式选择一个范围，再输入该命令，则将功能应用于特定范围  
  
  
## 利用子匹配交换顺序  
![1](https://img-blog.csdnimg.cn/cec91deeb3784abc959120fdbe0f04cb.png)  
  
<br/>  
  
## 在替换过程中执行算术运算  
  
![1](https://img-blog.csdnimg.cn/ce8793ca285a489a9cdad9add87bf280.png)  
![2](https://img-blog.csdnimg.cn/1b2fb78e4bb5457abecd3e893809767f.png)  
![3](https://img-blog.csdnimg.cn/ebd2195524cf4e6ab0240a398624b172.png)  
  
<br/>  
  
## 在多个文件中执行查找与替换  
  
![1](https://img-blog.csdnimg.cn/4192cb974f3e4103b52ca8a7ebe868fe.png)  
  
  
- 用 `:vimgrep` 命令  
  
  
## 交换多个单词  
  
- 利用达式寄存器和字典数据结构，需要学 Vim 脚本语法  
  
# global 命令  
  
  
  
# 折叠命令  
![1](https://img-blog.csdnimg.cn/08227f7c673c44aea3507bc0b5f2d08e.png)![2](https://img-blog.csdnimg.cn/0beca65f60fc4b1a8c8d8fe5d87d8991.png)  
  
  
- `:h fold commands`  查看折叠命令  
- 折叠命令以 `z` 开头，因为 `z` 从侧面看像这起来的纸  
- 要设置折叠方案，`:h foldmethod` 查看帮助文档  
![3](https://img-blog.csdnimg.cn/c36de4a3b8ef4fcbbf5d27f3d66bf20d.png)  
   
<br/>  
  
  
# list 模式：显示文本中结束符和制表符  
![1](https://img-blog.csdnimg.cn/ec88deb895b347c0b9c6d1aff3298bc7.png)![2](https://img-blog.csdnimg.cn/ec0da9b15c794822ad58da76dcdd21e9.png)  
  
<br/>  
  
- `:h 'list'` 查看帮助  
- `set list` 设置后，可以看见上图中蓝色的 `^I` 指标符和 `$` 表示一行结束的符号，能方便区分指标符和空格   
  
# 文本格式 fileformat  
  
![1](https://img-blog.csdnimg.cn/9efdac605fb64775b386659998b3f1c0.png)  
<br/>  
  
- `:h 'fileformat` 查看帮助文档  
- 如果是 windows 格式文本，可以用 `hexdump` 查看其内容，再用 `:set ff=unix` 转换为 `unix` 格式并保存，再次用 `hexdump` 查看其区别  
![2](https://img-blog.csdnimg.cn/b7c34305ae2b45efbd93b218e5ad1f68.png)  
  
  
  
# 为文本加密  
![1](https://img-blog.csdnimg.cn/4f7af21a70514f71a6ae54130c038121.png)  
  
  
- 编辑完后命令行模式输入 `:X` 则会出现输入密码的提示，以后再打开该文件，则需要输入密码，如果想取消密码，则输入密码时直接回车  
- 也可通过 `:set key=` 直接输入密码  
  
  
# 将命令行输出内容写入到文件中  
  
在命令行中输入下面内容，将当前  
```vim  
:let @a = expand("%")  
```  
  
# vim 启动选项  
查看帮助：  
```bash  
vim -h | less  
```  
  
## vim --cmd 执行命令  
```bash  
--cmd <command>      Execute <command> before loading any vimrc file  
```  
  
不进入 vim 加载 vimrc 配置文件  
```bash  
root@ubuntu2204c12:/usr/local/src# vim --cmd "source /etc/vim/vimrc.local" --cmd "q"  
```  
  
## vim -c 执行命令  
```bash  
-c <command>         Execute <command> after loading the first file  
```  
  
# 获取 vim 版本号  
```bash  
root@ubuntu2204c12:/usr/local/src# vim --version | head -n 1 | awk '{print $5}'  
8.2  
```  
  
  
# 例子  
  
## 查询匹配的内容，高亮显示但不替换  
  
`:g/pattern/p`，如下查询 `${ }` 内容，不替换  
```vim  
: g/[^"]\${\([^}]*\)}/p  
```  
  
## 将 shell 脚本中的 ${} 的变量加上引号  
shell 脚本中，在 `[ ]` 中使用变量时，忘记加引号，容易引发一些错误，利用 vim 的查找替换加上引号：  
  
```vim  
:%s/[^"]\${\([^}]*\)}/ "\${\1}" /gc  
````  
  
加上 `c` 标识会在每个匹配的内容替换前询问  
```vim  
replace with  "\${\1}"  (y/n/a/q/l/^E/^Y)?  
```  
- `Press y` to replace the current occurrence.  
- `Press n` to skip the current occurrence.  
- `Press a` to replace all remaining occurrences without further prompting.  
- `Press q` to quit the substitution.  
- `Press l` to replace the current occurrence and then quit.  
- `Press Ctrl+E` to scroll up and display more context.  
- `Press Ctrl+Y` to scroll down and display more context.  
  
## 行末尾添加空格  
每行末尾添加两个空格  
  
利用宏，普通模式，按 q，然后选择一个寄存器，如 a，开始录制：按 `A` 切换到行末尾且切换到插入模式，输入两个空格，按 `Esc` 回到普通模式，按 `q` 录制结束  
  
选择需要处理的行，如全文处理，则切换到第一行，按 `V` 选择当前行，按 `G` 选择到最后一行，即选中全文，然后按 `:` 切换到命令行模式，此时自动选中选择的行 `:'<,'>`，后面输入 `normal @a`，即 `:'<,'>normal @a`  
  
  
## 删除行末尾空格  
上传到 github 上的文档，行末尾需要添加两个空格才会换行，在文档上传前，批量处理每行，在其末尾加两个空格，但文档可能重复修改，不能每次上传都加空格，因此在加空格前，先删除末尾的空格  
  
规则为：不处理空白行，包含多个空格的行，仅处理有内容，末尾有两个或以上空格的行，删除末尾空格  
  
不用 very magic 模式：  
```bash  
%s/\(\S\)\s\{2,\}$/\1/g  
```  
  
用 very magic 模式：  
```bash  
%s/\v(\S)\s{2,}$/\1/g  
```  
  
可用 `:set list` 查看文本  
