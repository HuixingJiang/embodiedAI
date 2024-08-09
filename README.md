# embodiedAI


内容整理自：https://github.com/AlexanderKoch-Koch/low_cost_robot

这个存储库包含了构建和控制一个成本大约为250美元的低成本机械臂所需的文件。您还可以构建第二个机械臂（领导者臂），以控制另一个臂（跟随者臂），其成本约为180美元，总计430美元。领导者的设计灵感来自[GELLO项目](https://github.com/wuphilipp/gello_mechanical)，但建造起来更简单。这样的机械臂非常适合用于[机器人学习](https://x.com/alexkoch_ai/status/1756500716854841835?s=20)。这两个机械臂还能够[折叠衣物](https://x.com/alexkoch_ai/status/1772750496174149708?s=20)。

这个机械臂使用了Dynamixel XL430和Dynamixel XL330伺服电机。XL430电机的强度几乎是XL330的两倍，用于前两个关节。XL330电机较轻，但每个仅重18克。这使得机械臂非常轻巧且快速。Dynamixel销售U2D2适配器将伺服电机连接到计算机，但这非常昂贵，且延迟非常高。这个构建使用了另一种更便宜的适配器板。机械臂可以使用Dynamixel SDK进行控制：pip install dynamixel-sdk。
