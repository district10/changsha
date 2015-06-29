# 用一个 demo 说明项目分工

(代码仅内部分享)

Notice
> 用 VS 的说明方式，这里把整个项目称为 **solution**，
> 每个人自己的模块称为一个 **project**。


### 代码目录

这是 Qt 工程, demo solution 有一个主界面（mainwindow），有一个 project: lms.
其中 LMSReader 是读取 LMS 的类，
可完全脱离界面运行，也包含一个 dialog 界面，调用接口设置参数。
文件树如下:

```
Solution                           =======================> 整个 solution
├── Changsha.pro                   *
├── LICENSE
├── lms                            ------------------|
│   ├── lmsreaderconfig.cpp                          |
│   ├── lmsreaderconfig.h                            |
│   ├── lmsreaderconfig.ui                           |
│   ├── lmsreader.cpp                                |----> 每个人自己的 project, 可以独立运行
│   ├── lmsreader.h                                  |
│   ├── lmsreader.pro              *                 |
│   ├── main.cpp                                     |
│   └── README.md                  *-----------------|
├── main.cpp
├── mainwindow.cpp
├── mainwindow.h
├── mainwindow.ui
└── README.md                      *  
```

[>> 下载 demo <<](https://github.com/district10/changsha/archive/master.zip)


### 对每个 project 的要求

以 LMSReader 为例。它位于文件夹 `lms`，可独立运行，包含文档。

```
Project
├── lmsreaderconfig.cpp
├── lmsreaderconfig.h                  --> 一个低耦合的界面（完全是函数调用）
├── lmsreaderconfig.ui
├── lmsreader.cpp
├── lmsreader.h                        --> 类实现
├── lmsreader.pro
├── main.cpp
└── README.md
```

界面（相当于一个代理）和类（实际干活的人）应当低耦合。
界面只做简单的 validation, confinement，将按钮对应相应的函数。

> **不要在界面里写太多的代码！！！**

除此, 要有一份 README 文档, 包括:

* 一个简要的说明，用途，**输入输出**, 以及
* 可供调用的 public **函数**，可以获取的**变量**和**信号**

可参考 [LMSReader README 文档](lms/README.md)

> **文档用简单的纯文本写，不要用 MS Office Word。不要写太多。**

代码写的不恰当，文档不清楚，会使项目整合起来难度太大！

## 代码风格

Coding style 不要求大家一致，但**自己的代码要和自己的代码一致**。
最重要的是能运行**易于理解**且美观，
其次才是高效。

> 用 **UTF-8 without BOM** 编码 (VS，Qt，Notepad++ 已默认此编码)

## What's more

如何给控制台下运行的类封装一个 configuration 界面类，可以参考 [LMSReaderConfigurationAgent 类](lms/lmsreaderconfig.h)

关键是

```c++
explicit LMSReaderConfigurationAgent(LMSReader *lms, QDialog *parent = 0);
LMSReader *lmsReader;
```

见

https://github.com/district10/changsha/blob/master/lms/lmsreaderconfig.h#L40

https://github.com/district10/changsha/blob/master/lms/lmsreaderconfig.cpp#L7


## 文件组织

如果用到了别人的代码，不要把所有代码混在一起。
分开一个文件夹，把所有**第三方**的 `.h`, `.cpp` 参考 [imu](imu) 文件夹下的 [bundle](imu/bundle)


---

## 自己的界面不要用 mainwindow
## 用 dialog！！！
