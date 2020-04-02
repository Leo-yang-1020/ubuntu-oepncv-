<h1>ubuntu18.04的安装与配置<h1>
首先下好iso文件，在vmpro中新建一个linux机，在配置时要选择稍后选择光盘，内存建议直接上2g(一开始使用的1g根本不够)。
配置好后，点击vm虚拟机的安装vmtools，通过tar -xvzf指令解压，解压后进入解压的安装包，./vmware-install.pl执行安装，一路回车或者y,，之后就可以设置全屏或者拖拽文件了。
  <h1>unbuntu安装配置oepncv3.4.8</h1>
 首先要配置好cmake的最新版，因为更换了阿里的软件源，因此cmake 可以直接apt-get安装最新版。cmake配置好之后进行opencv的安装。
opencv下好软件包之后，用unzip解压，解压后cd到opencv.3.4.8，mkdir一个release文件，cd进去，输入编译指令cmake -D CMAKE_BUILD_TYPE=RELEASE -D CMAKE_INSTALL_PREFIX=/usr/local ..
之后，make开始进行编译（内存至少2g才行，不然会发型swap空间不足的情况）。之后，sudo make install完成安装。
测试是否安装成功：进入/opencv-3.4.8/samples/cpp/example_cmake中 输入指令： cmake . make 运行命令： ./open_example 得到helloworld图案 并且打开摄像头即是成功。
（在测试遇到一个问题，是缺少libgtk2.0-dev,并且apt-get不能下载这个，应该是软件冲突的问题，在寻找了众多解放方法后，终于找到了此时需要降级安装。使用命令sudo aptitude install libgtk2.0-dev。
在使用该命令时需要注意，在最开始出现选择Y/n/q/？时要选择‘n’。这样才是降级安装。不然还是会安装失败。之后就可以一路选‘Y’了。
