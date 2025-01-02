# RoboMIND 社区 QA

[English](./CommunityQA.md) | 中文

[项目页面](https://x-humanoid-robomind.github.io/) | [论文](https://arxiv.org/abs/2412.13877) | [数据平台](http://open.flopsera.com/flopsera-open/data-details/RoboMIND)

### Q1：Flopsera 平台注册流程？
**A：** Flopsera 平台注册流程：点击同意《数据使用协议》→用微信扫码→填写正确的邮箱地址和与微信绑定的手机号→获取并填入手机验证码→提交完成注册。

我们了解到目前的平台流程上有些繁琐，也在探索其他的平台，敬请期待。

### Q2：hi请问团队能否考虑每个embodiment提供一个trajectory样例，这样方便在laptop本地测试数据处理的脚本
**A：** 感谢提供建议，我们提供了一个简单 franka sample轨迹以及数据集读取的代码 [read_h5.py](https://github.com/x-humanoid-robomind/x-humanoid-robomind.github.io/blob/main/static/read_h5.py) 与 [pick_apple_into_drawer_h5.zip](https://drive.google.com/file/d/1EC26fwhftw-9h_HJ5ohqxf4kcEJe_ZzH/view?usp=sharing)。

### Q3：还想请问下，那10k条精标的数据是混在所有的数据里面的吗，有无考虑将这部分数据单独打包？谢谢
**A：** 10k现在在整理中。

### Q4：你好，请问现在网站上能下载的数据里包含深度信息吗？
**A：** 包含的，是rgbd图像。

### Q5：你好，请问目前数据中包含相机参数吗，内参外参这些？
**A：** WIP
