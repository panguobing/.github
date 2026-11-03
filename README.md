# OpenHUTB

OpenHUTB 简单来说是面向人机共生与智能载具研究、教学和开发，提供影视级物理模拟器、开放数字资产，以及感知、规划、控制和场景生成工具的开源仿真社区。该社区具体提供一个包含人车代理（学术研究）、模拟器（技术开发包括数据驱动、机理仿真、界面渲染）、现实场景（艺术增强）的 [模拟器](https://openhutb.github.io) ，代理包括[感知](https://openhutb.github.io/doc/algorithms/perception/) （连接）、[规划](https://openhutb.github.io/doc/algorithms/planning/) （符号）、[控制](https://openhutb.github.io/doc/algorithms/control/) （行为）；模拟器包括 Python 与 C++ 的接口（正向创建、反向构建）、LibCarla、虚幻引擎插件；现实场景包括 [静态场景孪生](https://openhutb.github.io/doc/adv_digital_twin/) 、[动态场景孪生](https://github.com/OpenHUTB/traffic_twin/) 。


以下为新手快速上手栏目：

[🚀 快速开始](https://github.com/OpenHUTB/hutb#使用示例) · [📖 在线文档](https://openhutb.github.io/) · [🧪 运行示例](https://github.com/OpenHUTB/doc/tree/master/src/examples) · [🤝 参与贡献](https://github.com/OpenHUTB/.github/blob/master/CONTRIBUTING.md) · [💬 提问与讨论](https://github.com/orgs/OpenHUTB/discussions)
- [💡 贡献小贴士](contribute-tips.md)

你可以用 OpenHUTB 做什么？
- **研究与教学**：学习感知、规划、控制和具身智能算法。
- **仿真与验证**：在可重复的场景中开发、训练和验证算法。
- **场景与内容开发**：使用开放的城镇、建筑、车辆、行人和道具资产创建仿真环境。

## 文档维护方向

- 持续核对安装教程中的系统版本、依赖和操作入口，减少照着旧截图操作却找不到选项的情况。
- 完善模拟器和研究项目之间的链接说明，让读者能从概览页继续找到安装资料、API 和示例。
- 补充实验记录中的数据来源、运行条件和评价指标，方便他人理解结果并复查过程。

核心入口

- 🟡 **[hutb 人车模拟器](https://github.com/OpenHUTB/hutb)** — 提供下载工具、Python API 和交通生成示例，目前持续开发中。
- 📚 **[doc 人车文档](https://github.com/OpenHUTB/doc)** — 人车模拟器配套安装说明、API与教程文档。

### 研究与实验项目

- 🧪 **[traffic_twin 人车孪生](https://github.com/OpenHUTB/traffic_twin)** — 交通数字孪生相关研究和示例，使用前请查看仓库说明。
- 🧠 **[neuro 神经原理](https://github.com/OpenHUTB/neuro)** — 用于感知与神经网络算法的相关研究与实验。
- 🧭 **[PFC 规划](https://github.com/OpenHUTB/PFC)** — 智能规划与决策相关研究。
- 🎮 **[move 控制原理](https://github.com/OpenHUTB/move)** — 运动控制与生物力学相关。

人车模拟器的技术架构如下图所示：

<a href="https://github.com/OpenHUTB/.github/blob/master/fig/repositories.md">
<img src="https://github.com/OpenHUTB/.github/blob/master/profile/repositories.png?raw=true" width="40%" >
</a>




<!--所有项目关系的思维导图。-->
<!-- 使用markmap进行编辑并生成svg：https://markmap.js.org/repl -->
<!-- 在profile/markmap.md中去保存图的数据 -->
<!-- svg图片预览：https://raw.githack.com/ -->

## 社区项目之间的关系

```mermaid
graph LR
    A[人的模型 <a href='https://github.com/OpenHUTB/opensim-core'>OpenSim</a>] --> B[多体物理 <a href='https://github.com/OpenHUTB/chrono'>chrono</a>]
    B --> C[<b>人车模拟器 <a href='https://github.com/OpenHUTB/hutb'>hutb</a> </b>]
    A --> F[<a href='https://github.com/MyoHub/myoconverter'>格式转换</a> <a href='https://github.com/OpenHUTB/mujoco_plugin'>mujoco_plugin</a> ]
    F --> C
    C --> D[文档 <a href='https://github.com/OpenHUTB/doc'>doc</a>]
