# [RoboMIND: Benchmark on Multi-embodiment Intelligence Normative Data for Robot Manipulation](https://x-humanoid-robomind.github.io/)

[![License](https://img.shields.io/badge/License-Apache_2.0-yellow.svg)](https://opensource.org/licenses/Apache-2.0)
[![Project Page](https://img.shields.io/badge/Project%20Page-RoboMIND-blue.svg)](https://x-humanoid-robomind.github.io/)
[![arXiv](https://badgen.net/badge/icon/arXiv?icon=awesome&label&color=red&style=flat-square)](https://arxiv.org/abs/2412.13877)
[![Dataset](https://img.shields.io/badge/Dataset-Flopsera-000000.svg)](http://open.flopsera.com/flopsera-open/data-details/RoboMIND)
[![Hugging Face](https://img.shields.io/badge/Hugging_Face-RoboMIND-000000.svg)](https://huggingface.co/datasets/x-humanoid-robomind/RoboMIND)

[English](./README.md) | 中文
## 💾 数据分布 💾
<img src="./static/images/piechart_new.png" border=0 width=100%>

### 🤖 机器人平台构成 🤖
我们推出了 RoboMIND（机器人操作的多构型智能规范数据集和基准），该数据集包含了在479种不同任务中涉及96类独特物体的10.7万条真实世界演示轨迹。
RoboMIND数据集汇集了多种机器人平台的操作数据，包括52,926条Franka Emika Panda单臂机器人轨迹、19,152条"天工"人形机器人轨迹、10,629条AgileX Cobot Magic V2.0双臂机器人轨迹、以及25,170条UR-5e单臂机器人轨迹数据。
通过涵盖广泛的任务类型和多种物体类别，RoboMIND 为研究人员和开发者提供了一个宝贵的资源，以推动机器人学习和自动化技术的发展。此数据集不仅数量庞大，而且质量上乘，确保了其在实际应用中的有效性和可靠性。

### 🔎 轨迹时长分布 🔎
从轨迹长度来看，不同机器人平台呈现出独特的分布特征。Franka和UR机器人的任务通常具有较短的轨迹，时间步数少于200步，这类数据特别适合用于训练基础操作技能。相比之下，"天工"和AgileX机器人的任务轨迹普遍较长，超过500个时间步，更适合用于训练长时间跨度的任务和复杂技能组合。

### 🚀 任务类型划分 🚀
基于自然语言描述，并考虑物品大小、使用场景和操作技能等因素，我们将数据集中的任务分为铰链物体操作、双臂协作操作、基础技能、精准操作、场景理解共六大类。除了基础操作任务外，数据集还包含了大量复杂任务，为训练通用机器人策略提供了丰富的数据支持。

### 💪 物品多样性 💪
整个数据集包含了96种不同的物品类别，具体如下所示。可以看出，在厨房场景中，数据集不仅包含了常见的食物，如草莓、鸡蛋、香蕉和梨子等，也包括了复杂的可调节物体，如烤箱和面包机。在家庭场景中，数据集既包括了刚性物体，如网球，也包括了可变形物体，如玩具。办公和工业场景则包含了需要精确控制的小物体，如电池和齿轮。这样多样化的物体种类不仅增加了数据集的复杂性，也有助于训练能够在各种环境下执行操作的通用操控策略。

<img src="./static/images/Distribution_new.png" border=5 width=95%>



## 📁 数据说明 📁
构建高质量的机器人训练数据集对开发具有良好泛化能力的端到端具身智能大模型至关重要。理想的数据集应涵盖多样化的场景、任务类型和机器人平台，使模型能够适应不同环境并可靠执行各类任务。本团队构建了一个大规模、真实的机器人学习数据集，记录机器人在复杂环境中执行长程任务时的交互数据，从而支持训练出具有通用操作能力的智能模型。

本数据集的部分目录结构示例如下，展示了Franka机器人下单个任务的2条训练轨迹和2条验证轨迹：
```
.
|-- h5_agilex_3rgb
|-- h5_franka_1rgb
|   |-- bread_in_basket
|   |   `-- success_episodes
|   |       |-- train
|   |       |   |-- 1014_144602
|   |       |   |   `-- data
|   |       |   |       `-- trajectory.hdf5
|   |       |   |-- 1014_144755
|   |       |   |   `-- data
|   |       |   |       `-- trajectory.hdf5
|   |       |-- val
|   |       |   |-- 1014_144642
|   |       |   |   `-- data
|   |       |   |       `-- trajectory.hdf5
|   |       |   |-- 1014_151731
|   |       |   |   `-- data
|   |       |   |       `-- trajectory.hdf5
|-- h5_franka_3rgb
|-- h5_simulation
|-- h5_tienkung_gello_1rgb
|-- h5_tienkung_xsens_1rgb
|-- h5_ur_1rgb
```

## 🗃️ HDF5 文件格式 🗃️

请参考 [all_robot_h5_info.md](./static/all_robot_h5_info.md)。

由于设备维修，在h5_franka_3rgb文件夹中，有675条轨迹只记录了左摄像头和右摄像头的图像数据。

具体数据路径请参考 [franka_3rgb_2cam_paths.md](./static/franka_3rgb_2cam_paths.md)。

仿真数据中，相机和机械臂采集频率约为1 ：4。此外，Simulation Franka中深度图数据暂不可用。

## 📊 数据使用 📊

请参考 [Quick_Start.ipynb](./static/quick_start.ipynb)。

请注意：
1. 对于h5_franka_3rgb, h5_franka_1rgb, h5_ur_1rgb, h5_franka_fr3_dual，图像存储通道顺序为BGR。
2. 对于其他机器构型，图像存储通道顺序为RGB。


```python
if sensor_type == 'rgb_images':
    # These embodiments image data are recorded in BGR
    if cur_embodiments in ['h5_franka_3rgb', 'h5_franka_1rgb', 'h5_ur_1rgb', 'h5_franka_fr3_dual']:
        img = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
    # Other embodiments image data are recorded in RGB  
    else:
        img = img
```

## 任务语言指令

我们为每个任务提供了对应的语言指令，见[RoboMIND_instr.csv](./static/RoboMIND_v1_2_instr.csv)。

## 数据集内参
请参考此文件 [RoboMIND intrinsics](./static/RoboMIND_intrinsics.md)

## 📖 版本更新 📖

### 版本 1.1 & 1.2

相较于版本1.0，我们进一步扩充了数据集，包含107K条轨迹和469项任务，涵盖了96种不同物体。

在版本1.1的基础上，我们新增了Upright_Cup的10项任务数据，其中包括 1个来自真实世界的任务数据和9个来自数字孪生环境的任务数据。这10个任务数据的目标均为翻转马克杯，但涉及不同的环境设置，例如马克杯的摆放位置范围、桌面纹理以及马克杯外观等。

更新了帧级别的细粒度语言指令标注数据，请参考[language_description_annotation_json](./static/language_description_annotation_json)

对于更多不同构型的H5文件格式，请参考[all_robot_h5_info_v1.2.md](./static/all_robot_h5_info_v1.2.md).

### 版本 1.0

初始版本的 RoboMIND 数据集包含55K条轨迹和279项任务，涉及69种不同物体。

## 📝 引用 📝
如果您发现 RoboMIND 对您的研究有帮助，请考虑引用：
```
@article{wu2024robomind,
  title={Robomind: Benchmark on multi-embodiment intelligence normative data for robot manipulation},
  author={Wu, Kun and Hou, Chengkai and Liu, Jiaming and Che, Zhengping and Ju, Xiaozhu and Yang, Zhuqin and Li, Meng and Zhao, Yinuo and Xu, Zhiyuan and Yang, Guang and others},
  journal={arXiv preprint arXiv:2412.13877},
  year={2024}
}
```

## 参考文件 ##
模型训练时输入输出请参考 [robomind.yaml](./static/robomind.yaml)。


## 📁 FAQ 📁
数据集常见使用问题解答，请参考 [FAQ.md](https://github.com/x-humanoid-robomind/x-humanoid-robomind.github.io/issues/2))。



## 🗨️ 参与讨论 🗨️
如果您对 RoboMIND 感兴趣，欢迎加入微信群，参与讨论。

<img src="./static/images/qrcode.jpg" border=0 width=30%>
