```
# How_to_debug_C_by_vscode_on_linux_remoteMode


重头记录vscode 运行linux c++代码的方法:

1. 首先安装远程链接.Remote Development
2.C:/Users/用户名/.ssh/config 
	Host 设备名称(不影响连接)
  HostName Linux的地址(域名或ip)
  Port 端口
  PreferredAuthentications 验证方式(password或publickey)
  User 用户名
  IdentityFile 私钥文件全路径,如果上面选择了publickey,需要用这个指出私钥文件的全路径

3.在链接上之后,的窗口中,安装c/c++
4.写main.c makefile 

test:add.o sub.o
	gcc -g -o test add.o sub.o
add.o: add.c test.h
	gcc -g -c add.c
sub.o:sub.c test.h
	gcc -g -c sub.c
clean:
	rm -rf test
	rm -rf *.o



5.然后shell 里面make掉.
6.然后vscode里面main函数加断点就可以debug了.
7.如果有需要操作的命令, 点view-terminal即可. 推荐不用, 因为里面rz命令不好使.功能没有xshell厉害.






护眼色:	#CCEED0

跑一些c项目试试.
https://www.zhihu.com/question/20792016


第一个:
	https://github.com/begeekmyfriend/bplustree
	装上cmake插件. cmake-tools.


	CMake Error: your CXX compiler: "CMAKE_CXX_COMPILER-NOTFOUND" was not found...问题的解决
	https://blog.csdn.net/paulkim23/article/details/71675630



	更新cmake版本:
	https://blog.csdn.net/m0_37587722/article/details/109026872

	代码上打上断点,然后camkelists.txt打开后,在最下面状态栏上点虫子即可debug了.

	这个项目外层一个cmakelists.txt 然后里层还有2个文件夹,一个lib一个test
	运行后都会跑里面代码,所以里面的main函数加断点即可.
```
