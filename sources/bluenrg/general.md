本文翻译BlueNRG-MS的芯片手册的核心内容。

> 源文档是BlueNRG-MS的芯片手册，下载请点击[这里](http://www2.st.com/resource/en/datasheet/bluenrg-ms.pdf)。

> 关于BlueNRG-MS的所有官方资料，请点击[这里](http://www2.st.com/content/st_com/en/products/wireless-connectivity/bluetooth-bluetooth-low-energy/bluenrg-ms.html)。


***
## 概述

BlueNRG-MS是低功耗蓝牙(Bluetooth Low Energy, BLE)处理器芯片，主要特点如下：

###1. 主从一体的协议栈

BlueNRG-MS的后缀'MS'指Master/Slave，该芯片可以支持同时工作于蓝牙的主设备/从设备模式，遵循了蓝牙4.1标准。

芯片内嵌ARM Cortex-M0内核，实现了低功耗蓝牙协议栈。

> 主设备/从设备，是蓝牙协议中的技术用语，您可以查阅蓝牙部分的学习资料。


###2. 远距离

BlueNRG-MS芯片端最大可以做到+8 dBm的输出功率。配合普通PCB天线或陶瓷天线，可以轻松达到50米乃至上百米的传输距离，是市面上传输距离最远的低功耗蓝牙芯片。

###3. 低功耗

- 工作电压：1.7V ~ 3.6V;
- 支持LDO和DC-DC稳压器;
- 发射电流：8.2mA @ 0dBm, 3V;
- 发射电流：15mA @ +8dBm, 3V;
- 待机电流：1.7uA(BLE协议栈处于工作状态);

###4. 即灵活、又规范

BlueNRG-MS的典型方案是：BlueNRG-MS+MCU。其中BlueNRG-MS负责完成蓝牙协议栈和蓝牙数据收发，MCU负责完成profile和应用层的事务，MCU和BlueNRG-MS之间通过基于SPI的ACI规范(ACI, Application-Controller Interface)进行交互。

让我们来对比一下常见的低功耗蓝牙实现方案：

- SoC方案：典型代表为Nordic nRF51822、TI CC254x系列等。它们的优势在于成本更低、系统简单、PCB可以做的小巧。不足之处在于资源有限，比如MCU的计算能力弱，难以实现复杂算法算法；GPIO、ADC、TIMER等数量不多；系统实时性不高等。
- “MCU+蓝牙透传模块”方案：使用SoC作为蓝牙透传模块负责蓝牙通信，外接MCU弥补SoC资源不足的问题。不足之处在于：MCU和蓝牙透传模块之间欠缺标准的指令和总线协议，不同蓝牙透传模块的通信品质参差不齐，而且整体成本不够理想。

综上，BlueNRG-MS可以灵活配备MCU，和MCU之间又有规范的ACI通信方式，是一个优秀的BLE解决方案。











