# Vim常用操作  
## Vim简介  
Vim是一个功能强大的全屏幕文本编辑器，是Linux/UNIX最常用的文本编辑器，它的作用是建立、编辑、显示文本文件。  
***Vim只有命令没有菜单***  
## Vim工作模式  
<img src="D:\Github客户端\My Github\Vacation\Linux\图片\Vim工作模式.png" alt="Vim工作模式" style="zoom:150%;" />
命令模式：vi或者vim加文件名，进入或者创建一个文件就会进入命令模式  
插入模式：
编辑模式：
## Vim常用命令（都是命令模式下，加：的时编辑模式）  
### 插入命令  
|命令|作用|
|:-:|:-:|
|a|在光标所在字符后插入|
|A|在光标所在行行尾插入|
|i|在光标所在字符前插入|
|I|在光标所在行行首插入|
|o|在光标下插入新行|
|O(大写)|在光标上插曲新行|
插入模式按ESC回到命令模式  
### 定位命令  
|命令|作用|
|:-:|:-:|
|:set nu|设置行号|
|:set nonu|取消行号|
|gg|到第一行|
|G|到最后一行|
|nG|到第n行（不推荐，因为输入n的时候n不显示）|
|:n|到第n行|
|$|移至行尾|
|0|移至行首|
### 删除命令  
|命令|作用|
|:-:|:-:|
|x|删除光标所在处字符|
|nx|删除光标所在处后n个字符|
|dd|删除光标所在行，如果是ndd删除n行|
|dG|删除光标所在行到文本末尾内容|
|D|删除光标所在处到行尾内容|
|:n1,n2d|删除指定范围行|
### 复制和剪切命令  
|命令|作用|
|:-:|:-:|
|yy|复制当前行|
|nyy|复制当前行以下n行|
|dd|剪切当前行|
|ndd|剪切当前行以下n行|
|p、P|粘贴在当前所在行下或行上|
### 替换和取消命令  
|命令|作用|
|:-:|:-:|
|r|取代光标所在处字符|
|R|从光标所在处开始替换字符，按ESC结束***就是那个之前不知道的蜜汁操作***|
|u|取消上一步操作|
### 搜索和搜索替换命令  
|命令|作用|
|:-:|:-:|
|/string|搜索指定字符串，n下一个。如果要搜索时忽略大小写：先set ic再/字符串|
|n|搜索指定字符串的下一个出现位置|
|:%s/old/new/g|全文替换指定字符串，g不询问，c询问一下|
|:n1,n2s/old/new/g|在一定范围内替换指定字符串|
### 保存和退出命令  
|命令|作用|
|:-:|:-:|
|:w|保存修改|
|:w new_文件名|另存为指定文件|
|:wq|保存修改并退出|
|ZZ|快捷键，保存修改并退出|
|:q!|不保存修改退出|
|:wq!|保存修改并退出（只有文件所有者和root能使用）|
# Vim使用技巧  
### 导入命令执行结果：  
：r! 命令  
把命令执行的结果导入编辑器中  
### 定义快捷键：  
：map 快捷键 触发命令  
按完map之后必须是按Ctrl+V+要定义的键或者Ctrl+V再Ctrl+要定义的键  
触发命令就是想给他什么功能，这就是之前讲的Vim命令  
### 连续注释行  
:n1,n2s/^/#/g       ^代表行首，//之间的是新旧内容  
:n1,n2s/^#//g       把行首#替换为空，即删除#  
:n1,n2s/^/\/\//g    在行首添加//，但是必须用\转义每一个/
### 替换或者说是定义  
：ab 表面 本质  
：ab qvshen chengguo  只要输入qvshen空格或者回车，她就会自动变为chengguo  
这个编辑命令是临时的，如果想要永久生效，写在配置文件里，文件名为.vimrc  
如果是管理员/root/.vimrc  
普通用户/home/用户名/.vimrc  
***在配置文件里，ab前不用加冒号***