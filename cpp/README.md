# 如何配置VIM

## 1 配置C++开发环境
本文参考了文档[《所需即所获：像 IDE 一样使用 vim》](https://github.com/yangyangwithgnu/use_vim_as_ide)，按照其介绍配置了C++开发环境。下面介绍一下需要注意的几个地方：

### 1.1 安装插件YouCompleteMe
关于YouCompleteMe插件的使用，参考Github上的[YouCompleteMe](https://github.com/Valloric/YouCompleteMe)库。
在VIM中安装C++库的标签系统，简单步骤为：
```
    cd ~/.vim/bundle/YouCompleteMe
    ./install.py --clang-completer
```
需要在.vimrc中指定.ycm_extra_conf.py文件路径：
```
" 允许 vim 加载 .ycm_extra_conf.py 文件，不再提示
let g:ycm_confirm_extra_conf=0
let g:ycm_global_ycm_extra_conf = '/home/max/.vim/bundle/YouCompleteMe/.ycm_extra_conf.py'
```

### 1.2 安装插件UltiSnippet
在.vimrc中指定插件的脚步路径：
```
" UltiSnips 的 tab 键与 YCM 冲突，重新设定
let g:UltiSnipsExpandTrigger="<leader><tab>"
let g:UltiSnipsJumpForwardTrigger="<leader><tab>"
let g:UltiSnipsJumpBackwardTrigger="<leader><s-tab>"
let g:UltiSnipsSnippetDirectories=["/home/max/.vim/my-ultisnips"]
```
[这里有很多脚本模板](https://github.com/honza/vim-snippets/tree/master/UltiSnips)。

### 1.3 安装universal-ctags
替代多年不更新的ctags。

### 1.4 hotfix使用
```
:cc     显示详细错误信息
:cp     跳到上一个错误
:cn     跳到下一个错误
:cl      列出所有错误
:cw     如果有错误列表，则打开quickfix窗口，没有则什么也不错
:copen 打开quickfix窗口，可以在后面添加窗口高度参数，如10行： :copen 10
:cclose 关闭quickfix窗口
:col     到前一个旧的错误列表
:cnew  到后一个较新的错误列表
```

### 1.5 多窗口调整
```
1、纵向调整
:res[ize]  num		指定当前窗口为num列num行
:res[ize] +num		把当前窗口高度增加num行
:res[ize] -num		把当前窗口高度减少num行
2、横向调整
:vert[ical] res[ize]  num		指定当前窗口为num列
:vert[ical] res[ize] +num		把当前窗口增加num列
:vert[ical] res[ize] -num		把当前窗口减少num列
 
3、快捷键
Ctrl + W + =  ：让所有窗口调整至相同尺寸（平均划分）
Ctrl + W + -：将当前窗口的高度减少1行。
Ctrl + W + +：将当前窗口的高度增加1行。
 
Ctrl + W + < ：将当前窗口的宽度减少1列。
Ctrl + W + > ：将当前窗口的宽度增加1列。
 
Ctrl + W + |：将当前窗口的宽度调到最大。
```

### 1.5 关于颜色配置
颜色配置目录跟老版本不一样，放在"~/.vim/colors/"目录下。 

