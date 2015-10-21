BridgeDetection
===============

这个文件夹下是用 cmake 集成好的部分
-----------------------------------
文档有在线版本（markdown 渲染显示效果好）: https://github.com/district/changsha

### 开发需要安装的软件

Deps: 

0. Windows x64
0. Visual Studio 2010 x64 (非 express)
0. Qt4: 
    * http://7xjdjw.com1.z0.glb.clouddn.com/qt-4.8.6-x64-msvc2010.exe
    * http://7xjdjw.com1.z0.glb.clouddn.com/Qt_Config.7z
0. OpenCV: http://7xjdjw.com1.z0.glb.clouddn.com/opencv-2.4.11.exe

Options: 

0. Boost: http://7xjdjw.com1.z0.glb.clouddn.com/boost_1_58_0-msvc-10.0-64.exe
0. CGAL: 
    + installer: http://7xjdjw.com1.z0.glb.clouddn.com/CGAL-4.6-Setup.exe
    + source code: http://7xjdjw.com1.z0.glb.clouddn.com/CGAL-4.6.zip
0. QGLViewer: http://7xjdjw.com1.z0.glb.clouddn.com/libQGLViewer-2.6.1.7z

### 说明

0. 可先自行尝试用 cmake 整合自己的 project 到 solution，成功后 commit 到 SVN。
0. 不要随意修改根目录的 CMakeLists.txt


### 界面和类低耦合，可参考:

0. 在线文档说明: https://github.com/district10/changsha/doc/modulize.md
0. 代码和文档: http://cvrs.whu.edu.cn/svn/BIRX/trunk/Programs/BridgeDetection/BridgeDetection/examples/QtDemo
0. 建议互相 code review


### MISC

cmake.sh 是一个小脚本，方便生成 cmake 工程，双击即可。前提是安装:

0. CMake
0. git-bash: http://7xjdjw.com1.z0.glb.clouddn.com/Git-1.9.5-preview20150319.exe (需绑定 .sh 文件的打开方式)
