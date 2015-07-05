# IMU 读取模块

---

> IMU（Inertial measurement unit，惯性测量单元）是测量物体三轴姿态角(或角速率)以及加速度的装置。

## 模块下主要文件和类

0. **`imureader{.h, .cpp}`**
    + 类 `IMUReader` 用于读取 IMU 数据并保存。
0. **`imureaderconfigurationagent{.h, .cpp, .ui}`**
    + 类 `IMUAgent` 是一个对话框界面，用于配置 `IMUReader` 类实例。


## 输入输出
    
* 输入：IMU 传感器（串口）
* 输出：IMU 数据（文本形式）

输出文件 sample：

```
23     18019   -23    33     1233    482    -127    69
23     14      59     19     1277    479    -131    74
23     28      101    -9     1273    472    -138    83
24     41      33     16     1222    459    -159    87
24     54      106    -9     1253    441    -181    86
24     67      62     -13    1263    416    -196    88
```

其中第一列为时间戳（ms），从 0 开始。


## 第三方库

QExtSerialPort


## 主界面如何使用

0.	添加一个全局 IMUReader 实例：
    + 成员函数：`IMUReader *imu;`
    + 构造函数：`imu = new IMUReader();`
0. 在界面上添加一个 action，调用 `IMUConfigurationAgent` 配置 imu：
    + ```cpp
    IMUConfigurationAgent agent(imu);
    agent.show();
    ```
0. 配置好后的 imu 便可以开始采集数据，在主界面添加相应按钮：
    + 连接 IMU：`void openIMU()`
    + 关闭连接：`void closeIMU()`
    + 开始读取：`void turnOn()`
    + 停止读取：`void turnOff()`

采集的数据会存在固定路径。