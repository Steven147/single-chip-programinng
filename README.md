# single-chip-programinng

嵌入式系统大作业记录

[oc网址](https://oc.sjtu.edu.cn/courses/30511)

官方 datasheet stm32

## 作业1

[oc课程链接](https://oc.sjtu.edu.cn/courses/30511/pages/keilruan-jian-xia-zai-di-zhi?module_item_id=405030)

安装keil5集成开发环境

[官网](http://www.keil.com/download/product/)

[百度网盘链接1 软件本体与芯片包](http://pan.baidu.com/s/1bpc7Xmf)

F1 F4 F7芯片包：[STM32的命名方法](https://www.cnblogs.com/Pual623548198/p/6654650.html)

百度网盘链接2 激活软件
链接：https://pan.baidu.com/s/1KAkNV1KyqUOKVozx2YZsSw 
提取码：cshb

流程
- 运行Keil软件安装包
- 运行F1芯片安装包
- 使用注册机注册

## 作业2：分别用DAP仿真器和串口下载跑马灯程序

[oc课程链接](https://oc.sjtu.edu.cn/courses/30511/assignments/88358?module_item_id=402099)

分别用DAP仿真器和用串口下载并运行开机例程的跑马灯程序，

请详细列出你的操作步骤，并仔细体会串口下载与DAP仿真器的异同，

请思考两者需要开发板具有什么样的支撑条件？

### DAP仿真器运行

该方法将电脑、仿真器和单片机串联起来，无需安装驱动，可以直接在keil IDE中为单片机下载程序。

> 硬件连接

- 仿真器连接电脑
- 单片机使用USB线供电（仅供电）
- 使用4条杜邦线连接仿真器和单片机：仿真器全速版只支持SW模式，只需要4根线，3V3不需要接

> 软件准备

- 打开魔术棒选项卡
- Debug选项配置：选择仿真器型号
- Utilities选项配置：选择默认配置的仿真器
- Debug选项具体配置：Settings
- 选择目标板、勾选reset&run：型号STM32F10x，用到之前下载的F1芯片包
- 在keil IDE中直接点击load

> 此时单片机正常显示流水灯效果，DAP仿真器下载程序成功


### 串口下载程序

该方法使用串口方式直接连接单片机与电脑，在电脑上安装相应的驱动，启动串口软件就能将文件写入单片机内存。

> 硬件准备

- 直接连接STM32与计算机，数据线同时进行供电和数据传输

> 软件准备

- 安装串口驱动CH340
- 打开MCUISP串口下载软件
- 如果驱动安装成功、连接成功，在MCUISP中可以搜索到相应的串口：Port COM2
- 选择工程输出的hex文件：流水灯.hex
- 配置：勾选校验、编程后执行、DTR低电平复位，RTS高电平进bootLoader
- 点击开始编程，终端显示下载成功
- （可选）点击清除芯片可以删除已经下载的程序

> 此时单片机正常显示流水灯效果，串口下载程序成功







