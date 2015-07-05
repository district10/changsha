# MCU 模块

---

> MCU（Micro Controller Unit）板子连接了 C2、SP20000C、IMU 等传感器，
> 可以获取和更新传感器设置。


## 模块下主要文件和类

0. **`mcu{.h, .cpp}`**
    + 类 `MCUController` 用于获取和更新 MCU 相连的传感器设置。
0. **`mcuagent{.h, .cpp, .ui}`**
    + 类 `MCUAgent` 是一个对话框界面，用于配置 `MCUController` 类实例。


## 输入输出
    
* 输入：MCU 板子（Modbus RTU 协议）
* 输出：MCU 所连接的传感器信息


## 第三方库

QExtSerialPort


## 主界面如何使用

0.	添加一个全局 MCUController 实例：
    + 成员函数：`MCUController *mcu;`
    + 构造函数：`mcu = new MCUController();`
0. 在界面上添加一个 action，调用 `MCUAgent` 配置 mcu：
    + ```cpp
    MCUAgent agent(mcu);
    agent.show();
    ```