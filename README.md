# llvm.lldb-vscode
vscode lldb调试插件.

此插件目的是在openharmony编译设备与openharmony运行设备网络不通状况下，使用数据线连接两个设备，解决openharmony运行设备 调试难 问题。

此插件是基于openharmony sdk中lldb的platform select remote-ohos模式，

硬件环境:

openharmony编译设备A,用于发起远程调试

openharmony运行设备B,要被调试程序运行环境

设备A与设备B可以通过数据线相连，并且可以使用hdc指令进行通讯

软件环境

1openharmony编译设备A安装DevEco Studio（openharmony app开发环境），然后安装openharmony  sdk。

![image-20240223102622547](images\image-20240223102622547.png)

将Sdk目录\openharmony\10\toolchains加入环境变量。确保hdc指令可以执行成功。

2 安装vscode 

openharmony编译设备A安装本仓库的lldb-vscode-0.1.0.vsix插件，windows环境下将本仓库中llvm.lldb-vscode-0.1.0_window.7z加压覆盖到之前安装插件目录中（通常是C:\Users\XXX\\\.vscode\extensions\llvm.lldb-vscode-0.1.0）,linux环境下将llvm.lldb-vscode-0.1.0_linux.tar.xz解压到\.vscode\extensions目录

3 根据openharmony运行设备B架构，将本仓库lldb-server目录中对应架构的lldb-server拷贝到设备上去，确保设备B中可以执行lldb-server指令。

最新lldb-server可以在"Sdk目录\openharmony\10\native\llvm\lib\clang\15.0.4\bin" 找到

4 openharmony编译设备A上编译本代码仓中helloworld程序（编译指令参照目录中readme.txt，仓库中有arm架构已编译好的程序），将编译好的程序拷贝到设备B中，确认程序可以运行输出helloworld日志

5 调试。

openharmony运行设备B上使用lldb-server *p --server --listen "*:1234" 启动lldb-server

使用vscode打开helloworld程序所在目录，选择lldb-vscode remote launch启动调试

![image-20240223114946789](images\image-20240223114946789.png)

6 调试成功

![image-20240223114515373](images\image-20240223114515373.png)

