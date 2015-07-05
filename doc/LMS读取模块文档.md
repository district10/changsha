# LMS 读取模块

---

> LMS 激光测距仪。

## 模块下主要文件和类

0. **`lmsreader{.h, .cpp}`**
    + 类 `LMSReader` 用于读取 LMS 数据并保存。
0. **`lmsreaderconfig{.h, .cpp, .ui}`**
    + 类 `LMSReaderConfigurationAgent` 是一个对话框界面，用于配置 `LMSReader` 类实例。


## 输入输出
    
* 输入：LMS 传感器（TCP 协议）
* 输出：LMS 点云数据（文本形式）

输出文件 sample：

```
    -1354.8165927534               23      1354.8165927534
    -1354.8576078916               23      1378.7131182150
    -1346.2479219495               24      1394.0805330563
    -1338.8496497244               24      1410.8531516189
    -1337.3987840826               24      1434.1846088752
```

其中第二列为时间戳（ms），从 0 开始。


## 第三方库

无


## 主界面如何使用

0.	添加一个全局 LMSReader 实例：
    + 成员函数：`LMSReader *lms;`
    + 构造函数：`lms = new LMSReader();`
0. 在界面上添加一个 action，调用 `LMSConfigurationAgent` 配置 lms：
    + ```cpp
    LMSConfigurationAgent agent(lms);
    agent.show();
    ```
0. 配置好后的 lms 便可以开始采集数据，在主界面添加相应按钮：
    + 开始读取：`void turnOnReading()`
    + 停止读取：`void turnOffReading()`

采集的数据会存在固定路径。