# Paper Note Skill

这是一个用于生成 VLA / WAM / 具身智能 / 机器人论文中文学习笔记的 Codex skill。

它沉淀了我在阅读 Physical Intelligence π 系列、GR00T N1、OpenVLA-OFT、UniVLA、CoWVLA、HiF-VLA、Motus、Fast-WAM、AHA-WAM、MaskWAM、WLA-0 等论文时形成的笔记流程。

## 适用场景

当你希望 Codex 帮你完成以下任务时，可以使用这个 skill：

- 阅读本地 PDF 论文并生成中文 Markdown 笔记。
- 按固定模板整理 VLA / WAM / robot foundation model 论文。
- 提取模型骨干、动作表示、训练 recipe、数据集、硬件、推理效率和是否开源。
- 分析论文和 VLA / WAM / World Models for VLA 的关系。
- 结合动态物体识别、快速动作执行、重规划等研究方向做启发总结。

## 目录结构

```text
paper-note-skill/
├── SKILL.md
├── agents/
│   └── openai.yaml
└── references/
    └── note-template.md
```

## 使用方式

可以直接这样对 Codex 说：

```text
使用 paper-note skill，帮我阅读这个文件夹下的论文并生成笔记。
```

或者：

```text
用论文笔记 skill，按照我之前的模板总结这篇 WAM 论文。
```

生成的笔记默认使用中文，并采用类似下面的结构：

```md
# <论文名> 论文笔记
------
## 💡 Meta Data
## 💡基础知识和概念
## 📜 研究背景 & 基础 & 目的
## 📊 研究内容
## 🚩 研究结论
## 📌 感想 & 疑问
## 🔬 研究方法
```

## 重点抽取字段

笔记会优先关注：

- 模型类型：VLA、WAM、World Models for VLA、latent-action VLA 等。
- 模型骨干：VLM、LLM、DiT、AR Transformer、World Expert、Action Expert。
- 动作表示：action chunk、action token、latent action、latent motion、diffusion / flow action。
- 训练细节：pretraining、post-training、fine-tuning、loss、数据集、batch、steps。
- 硬件与效率：GPU / TPU、推理延迟、控制频率、on-board / off-board。
- 是否开源：GitHub、project page、model release、data release。
- 与已有论文的关系：π 系列、FAST、GR00T N1、OpenVLA-OFT、UniVLA、CoWVLA、HiF-VLA、Motus、Fast-WAM 等。
- 对动态任务研究的启发：动态物体识别、快速执行、未来状态预测、动作重规划。

## 注意

如果论文没有明确报告训练硬件、代码仓库或模型权重，笔记会明确写出“论文未明确报告”，不会推测成事实。
