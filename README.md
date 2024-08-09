# embodiedAI


内容整理自：https://github.com/AlexanderKoch-Koch/low_cost_robot

这个存储库包含了构建和控制一个成本大约为250美元的低成本机械臂所需的文件。您还可以构建第二个机械臂（领导者臂），以控制另一个臂（跟随者臂），其成本约为180美元，总计430美元。领导者的设计灵感来自[GELLO项目](https://github.com/wuphilipp/gello_mechanical)，但建造起来更简单。这样的机械臂非常适合用于[机器人学习](https://x.com/alexkoch_ai/status/1756500716854841835?s=20)。这两个机械臂还能够[折叠衣物](https://x.com/alexkoch_ai/status/1772750496174149708?s=20)。

这个机械臂使用了Dynamixel XL430和Dynamixel XL330伺服电机。XL430电机的强度几乎是XL330的两倍，用于前两个关节。XL330电机较轻，但每个仅重18克。这使得机械臂非常轻巧且快速。Dynamixel销售U2D2适配器将伺服电机连接到计算机，但这非常昂贵，且延迟非常高。这个构建使用了另一种更便宜的适配器板。机械臂可以使用Dynamixel SDK进行控制：pip install dynamixel-sdk。

![image](https://github.com/user-attachments/assets/2beca272-c254-46bd-9457-b0bd7a563bee)

![image](https://github.com/user-attachments/assets/33095350-91c8-4ce6-a29d-f50d5de362ff)

Robotis 商店通常有一个10%的折扣码。给夹持器添加一些防滑带也可能有所帮助（例如：[购买防滑带](https://a.co/d/dW7BnEN)）。连接伺服驱动板到电脑需要一根 USB-C 电缆。

![image](https://github.com/user-attachments/assets/3cd8ed18-f297-4e45-8182-7736e46c8b4d)

组装
组装视频：[点此观看](https://youtu.be/RckrXOEoWrk)

使用 3D 打印机打印所有部件
STL 文件位于 hardware/follower/stl
这些部件设计得易于打印；只有夹持器的移动部分需要支撑
扫描电机
将驱动板连接到电脑（应该适用于 Linux 和 MacOS）
找出设备名称（例如 MacOS 上的 tty.usbmodem57380045631）：执行 ls /dev/tty.* 命令
使用 Dynamixel Wizard 逐个扫描每个电机
将所有电机的波特率设置为 1M
将伺服 ID 设置为肩部为 1，夹持器伺服为 5（如果使用肘部到手腕的扩展则为 6）
组装
在没有底座的情况下组装手臂
确保伺服固定在与 CAD 中相同的位置
伺服喇叭在拧紧时应该处于默认位置
将电线焊接到电压降低器上；输入应连接到母头连接器，输出连接到公头连接器
将电压降低器和伺服驱动板拧到底座上
将底座拧到手臂上
将驱动板上的 D、V 和 G 端口连接到肩部旋转伺服
将肩部旋转伺服连接到肩部提升伺服
将电压降低器的输入连接到驱动板上的 V 和 G 端口
将电压降低器的输出和驱动板上剩余的 D 端口连接到肘部伺服
将驱动板连接到电源
连接到 XL330 伺服，并在 Dynamixel Wizard 上查看输入电压，然后调整电压降低器上的螺丝，直到输入电压为 5V

![image](https://github.com/user-attachments/assets/9530b98c-df12-4600-be13-9c15d6f3bf66)

![image](https://github.com/user-attachments/assets/bb93c751-da63-4b7b-b5b4-480bf8a8b272)

组装
领导臂的组装更简单，因为所有电机都使用5V电源。夹持器被一个手柄和一个扳机所取代。在使用过程中，可以对扳机施加一点扭矩，使其默认打开。GELLO设计为此目的使用了一个弹簧，但这在组装上要困难得多。可以使用 teleoperation.py 脚本来测试手臂。然而，可能需要调整设备名称。

