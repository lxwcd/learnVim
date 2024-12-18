# 环境
- win10/win11

## 查看版本
查看 bash 版本和终端：
```bash
lxw@NEU-20240403OIC MINGW64 ~
$ bash --version
GNU bash, version 5.2.37(1)-release (x86_64-pc-msys)
Copyright (C) 2022 Free Software Foundation, Inc.
License GPLv3+: GNU GPL version 3 or later <http://gnu.org/licenses/gpl.html>

This is free software; you are free to change and redistribute it.
There is NO WARRANTY, to the extent permitted by law.

lxw@NEU-20240403OIC MINGW64 ~
$ echo $TERM
xterm
```

查看 vim 版本：
直接输入 vim 查看。

# 查看配置文件的路径
输入 vim 后，输入 `:verion` 查看配置文件的路径，如：
```bash
  system vimrc file: "/etc/vimrc"
     user vimrc file: "$HOME/.vimrc"
 2nd user vimrc file: "~/.vim/vimrc"
 3rd user vimrc file: "~/.config/vim/vimrc"
      user exrc file: "$HOME/.exrc"
       defaults file: "$VIMRUNTIME/defaults.vim"
  fall-back for $VIM: "/etc"
 f-b for $VIMRUNTIME: "/usr/share/vim/vim91"
```

在 Git Bash 和其他类 Unix 环境中，`/etc/vimrc` 是 Vim 编辑器的系统级配置文件的传统路径。这个路径源自 Unix 和 Linux 系统，其中 `/etc` 是用于存储系统级配置文件的目录。然而，在 Windows 系统中，并没有 `/etc` 这样的目录，这是一个 Unix 和 Linux 特有的目录结构。

在 Git Bash 中，`/etc/vimrc` 的路径是一个模拟的路径，它映射到 Windows 系统中的一个实际位置。这样做是为了保持与 Unix 和 Linux 环境的兼容性，使得 Unix 和 Linux 用户能够在 Windows 上的 Git Bash 中使用他们熟悉的 Vim 配置。

最后两行的意思是：

1. **fall-back for $VIM: "/etc"**
   - 这行表示如果环境变量 `$VIM` 没有设置，Git Bash 会回退到 "/etc" 目录来查找 Vim 相关的配置和文件。这是一个备用方案，以防 `$VIM` 环境变量未定义。

2. **f-b for $VIMRUNTIME: "/usr/share/vim/vim91"**
   - `$VIMRUNTIME` 是另一个环境变量，它指向 Vim 的运行时文件，包括语法文件、脚本等。这行表示如果 `$VIMRUNTIME` 没有设置，Git Bash 会使用 "/usr/share/vim/vim91" 作为默认路径。这里的 "vim91" 可能指的是 Vim 的某个特定版本，例如 8.1 版本。

下载 [vimrc 文件](https://github.com/lxwcd/learnVim/blob/main/vimrc.local) 重命名到 `$HOME/.vimrc`，退出后重新进入即可生效。

修改配置文件的路径：
```bash
" 设置全局自定义配置文件的路径变量
let $MYVIMRC = "$HOME/.vimrc"
```

## 修改 vim 中光标样式
```bash
" modify cursor style
if &term =~ "xterm\\|rxvt"
  " 设置插入模式下的光标样式为竖线
  let &t_SI .= "\<Esc>[5 q"  " SI = INSERT mode
  " 设置替换模式下的光标样式为竖线
  let &t_SR .= "\<Esc>[5 q"  " SR = REPLACE mode
  " 设置普通模式下的光标样式为块状
  let &t_EI .= "\<Esc>[2 q"  " EI = NORMAL mode (ELSE)
endif
```

## 复制到系统剪贴板
选中后使用 `"+ y` 复制内容，即复制到系统剪贴板。
```bash
set clipboard=unnamedplus
```
`set clipboard=unnamedplus` 是 Vim 中的一个配置选项，用于指定 Vim 如何与系统剪贴板交互。下面是这个配置选项的详细解释：

1. **`clipboard` 选项**：
   - Vim 的 `clipboard` 选项控制 Vim 如何使用系统剪贴板。通过设置这个选项，你可以让 Vim 的复制（yank）和粘贴（paste）操作直接与系统剪贴板进行交互。

2. **`unnamedplus` 的含义**：
   - `unnamedplus` 是 `clipboard` 选项的一个值，它告诉 Vim 使用系统剪贴板作为复制和粘贴操作的存储。在 Vim 中，`"+` 寄存器通常与系统剪贴板相关联，而 `unnamedplus` 使得这个寄存器的行为与系统剪贴板一致。

3. **如何工作**：
   - 当你设置了 `set clipboard=unnamedplus`，Vim 会将复制（yank）操作的内容存储到 `"+` 寄存器，这个寄存器与系统剪贴板同步。因此，当你在 Vim 中复制文本时，它也会出现在系统剪贴板上，你可以在其他程序中粘贴。
   - 同样地，从系统剪贴板粘贴（paste）文本到 Vim 中时，Vim 会从 `"+` 寄存器读取内容。

4. **在 Linux 中的配置**：
   - 这个配置同样适用于 Linux 系统。在 Linux 系统中，`"+` 寄存器可能与 X11 的 CLIPBOARD 选区相关联，这取决于你的桌面环境和配置。在大多数现代 Linux 发行版中，`"+` 寄存器用于系统剪贴板操作。

5. **检查 Vim 是否支持剪贴板**：
   - 可以使用 `vim --version | grep clipboard` 命令来检查你的 Vim 是否支持剪贴板功能。如果输出中包含 `+clipboard`，则表示支持。
