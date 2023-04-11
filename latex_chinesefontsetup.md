## latex中文字体设置完美解决方案
### 2023.04.11

设计文档类时慢慢总结出来的，具体就是调用自己的字体文件，自定义自己的字体与命令。不会产生烦人的橘色报错（texpage）
代码如下：
```latex
diydocument.cls
\RequirePackage{xeCJK}
\setmainfont{Times New Roman}      % 缺省英文字体 Times New Roman
\setCJKmainfont[Path=fontsetup/]{simsun.ttc}  % 中文主字体：宋体
\setCJKsansfont[Path=fontsetup/]{simhei.ttf}  % 中文无衬线字体：黑体
\setCJKmonofont[Path=fontsetup/]{simsun.ttc}  % 中文等宽字体：宋体

\setCJKfamilyfont{song}[Path=fontsetup/]{simsun.ttc}      % 导入宋体字体
\setCJKfamilyfont{kai}[Path=fontsetup/]{kaitiGB2312.ttf}  % 导入楷体字体
\setCJKfamilyfont{hei}[Path=fontsetup/]{simhei.ttf}       % 导入黑体字体
\setCJKfamilyfont{xkai}[Path=fontsetup/]{hgxkCNKI.TTF}    % 导入行楷字体

\newcommand{\song}{\CJKfamily{song}} 			 % 设置宋体快捷命令
\newcommand{\kai}{\CJKfamily{kai}}   			 % 设置楷体快捷命令
\newcommand{\hei}{\CJKfamily{hei}}   			 % 设置黑体快捷命令
\newcommand{\xkai}{\CJKfamily{xkai}}   			 % 设置行楷快捷命令
```
使用时将字体文件夹fontsetup放置在同一个项目文件夹之中，使用这些代码用xeLaTeX编译，就可以完美运行。为了方便，将fontsetup上传了腾讯微云，登录QQ下载就能使用。（提醒自己的）
