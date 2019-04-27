问题:

　　Windows上面安装Visual Studio Code编辑器后,常常会因为安装的时候忘记勾选等原因,没有将"Open with Code(右键快捷方式)"添加到鼠标右键菜单里,使用起来多有不便,所以需要我们手动将VSCode添加至鼠标右键菜单之中.

解决:

1.新建reg文件.在桌面上新建一个文本文件,然后将文件后缀改为:*.reg,文件名任意,例如:add_shortcut.reg.

2.编写文本文件内容.将下面的内容Copy到刚才新建的*.reg文件中,文本内容如下:

按 Ctrl+C 复制代码


Windows Registry Editor Version 5.00

[HKEY_CLASSES_ROOT\*\shell\VSCode]
@="Open with Code"
"Icon"="D:\\StudyKu\\Microsoft VS Code\\Code.exe"

[HKEY_CLASSES_ROOT\*\shell\VSCode\command]
@="\"D:\\StudyKu\\Microsoft VS Code\\Code.exe\" \"%1\""

Windows Registry Editor Version 5.00

[HKEY_CLASSES_ROOT\Directory\shell\VSCode]
@="Open with Code"
"Icon"="D:\\StudyKu\\Microsoft VS Code\\Code.exe"

[HKEY_CLASSES_ROOT\Directory\shell\VSCode\command]
@="\"D:\\StudyKu\\Microsoft VS Code\\Code.exe\" \"%V\""

Windows Registry Editor Version 5.00

[HKEY_CLASSES_ROOT\Directory\Background\shell\VSCode]
@="Open with Code"
"Icon"="D:\\StudyKu\\Microsoft VS Code\\Code.exe"

[HKEY_CLASSES_ROOT\Directory\Background\shell\VSCode\command]
@="\"D:\\StudyKu\\Microsoft VS Code\\Code.exe\" \"%V\""

按 Ctrl+C 复制代码

3.上面代码中的地址表示VSCode在电脑上的安装路径,如果不是默认安装的或者路径不一样,需要改成和电脑上实际安装路径一致的.

4.文件编辑好了之后保存关闭.然后双击运行 add_shortcut.reg ,遇到提示点击 "确定"或"是".不出意外,便大功告成了!
