# UR 机械臂控制模块

---

> UR（Universal Robot）是一个机械臂，位于车机械臂末端，搭载了全部传感器。
> 共 6 个关节，均可 360 度旋转，可定点移动。


## 模块下主要文件和类

0. **`urcontroller{.h, .cpp}`**
    + 类 `URController` 用于获取 UR 状态和并可操作机械臂移动。
0. **`widget{.h, .cpp, .ui}`**
    + 类 `URPanel` 是一个 widget 界面，用于配置 `URController` 类实例。


## 输入输出
    
* 输入：UR（Modbus TCP 协议）
* 输出：控制界面显示 UR 状态，可操作 UR 机械臂


## 主界面如何使用

0.	添加一个全局 URPanel 实例：
    + 成员函数：`URPanel *urPanel;`
    + 构造函数：`urPanel = new URPanel();`
    + 使用：`urPanel->show();`