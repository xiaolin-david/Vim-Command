VIM editor common command learning！

基本上vi可以分为三种状态，分别是命令模式（command mode）、插入模式（Insert mode）和底行模式（last line mode），各模式的功能区分如下：

1) 命令模式（command mode）

控制屏幕光标的移动，字符、字或行的删除，移动复制某区段及进入插入模式、底行模式下。

2) 插入模式（Insert mode）

只有在插入模式下，才可以做文字输入，按ESC键可回到命令模式。

3) 底行模式（last line mode）

将文件保存或退出vi，也可以设置编辑环境，如寻找字符串、列出行号。不过一般我们在使用时把vi简化成两个模式，就是将底行模式也算入命令模式。

一、打开文件、保存、关闭文件(vi命令模式下使用)

vi filename     //打开filename文件

:w    	     //保存文件

:w yusi123.com        //保存至yusi123.com文件

:q    	     //退出编辑器，如果文件已修改请使用下面的命令

:q!                 //退出编辑器，且不保存

:wq               //退出编辑器，且保存文件

二、插入文本或行(vi命令模式下使用，执行下面命令后将进入插入模式，按ESC键可退出插入模式)

a      //在当前光标位置的右边添加文本
i       //在当前光标位置的左边添加文本
A     //在当前行的末尾位置添加文本
I      //在当前行的开始处添加文本(非空字符的行首)
O     //在当前行的上面新建一行
o     //在当前行的下面新建一行

三、移动光标(vi命令模式下使用)

按 Ctrl+b ：屏幕往后移动一页。

按 Ctrl+f ：屏幕往前移动一页。

按 Ctrl+u ：屏幕往后移动半页。

按 Ctrl+d ：屏幕往前移动半页。

按 Ctrl+r ：撤销多次操作。

按 u ：撤销单次操作。

按 0 ：移到当前行的开头。

按 G ：移动到文章的最后。

按 $ ：移动到光标所在行的行尾。

按 ^ ：移动到光标所在行的行首。

按 w ：光标跳到下个字的开头。

按 e ：光标跳到下个字的字尾。

按 b ：光标回到上个字的开头。

按 #l ：光标往后移的第#个位置，如：5l,56l .

四、删除、恢复字符或行(vi命令模式下使用)

x ：每按一次，删除光标所在位置的后面一个字符。

#x ：删除光标所在位置的后面#个字符，例如， 6x 表示删除光标所在位置的后面6个字符。

X ：每按一次，删除光标所在位置的前面一个字符。

#X ：删除光标所在位置的前面#个字符，例如， 20X 表示删除光标所在位置的前面20个字符。

dd ：删除光标所在行。

#dd ：从光标所在行开始删除#行。

五、搜索(vi命令模式下使用)

/yusi123     //向光标下搜索yusi123字符串
?yusi123    //向光标上搜索yusi123字符串
n               //向下搜索前一个搜素动作
N              //向上搜索前一个搜索动作

六、跳至指定行(vi命令模式下使用)

n+        //向下跳n行
n-         //向上跳n行
nG        //跳到行号为n的行
G          //跳至文件的底部

七、设置行号(vi命令模式下使用)

:set  nu       //显示行号
:set nonu    //取消显示行号

八、复制、粘贴(vi命令模式下使用)

yy    //将当前行复制到缓存区，也可以用 “ayy 复制，”a 为缓冲 区，a也可以替换为a到z的任意字母，可以完成多个复制任务。

nyy   //将当前行向下n行复制到缓冲区，也可以用 “anyy 复制，”a 为缓冲区，a也可以替换为a到z的任意字母，可以完成多个复制任务。

yw    //复制从光标开始到词尾的字符。
nyw  //复制从光标开始的n个单词。
y^    //复制从光标到行首的内容。
y$     //复制从光标到行尾的内容。

p     //粘贴剪切板里的内容在光标后，如果使用了前面的自定义缓冲区，建议使用”ap 进行粘贴。
P     //粘贴剪切板里的内容在光标前，如果使用了前面的自定义缓冲区，建议使用”aP 进行粘贴。

九、替换(vi命令模式下使用)

:s/old/new      	//用new替换行中首次出现的old
:s/old/new/g         	//用new替换行中所有的old
:n,m s/old/new/g     //用new替换从n到m行里所有的old
:%s/old/new/g     	//用new替换当前文件里所有的old

十、编辑其他文件

:e otherfilename    //编辑文件名为otherfilename的文件。

十一、修改文件格式

:set fileformat=unix   //将文件修改为unix格式，如win下面的文本文件在linux下会出现^M。

注意：如果不知道自己处在什么模式时可以按2次Esc键即可回到命令模式，会有最后提醒一点：注意大小写！！！
