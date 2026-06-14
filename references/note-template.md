# Paper Note Template Reference

## Recommended Section Content

### Meta Data

Use a table:

```md
| **Title** | |
| --- | --- |
| **Journal & Conference** | |
| **Authors** | |
| **Pub.date** | |
| **Project / Code** | |
```

If the paper is an arXiv preprint, write `arXiv preprint`. If a code link is absent, write `未明确给出`.

### 基础知识和概念

Add concepts the user may ask about later. For VLA/WAM papers, common concepts include:

- `action chunk`
- `flow matching`
- `diffusion policy`
- `latent action`
- `latent motion`
- `world model`
- `WAM`
- `VLA`
- `MPC`
- `value function`
- `test-time scaling`
- `open-loop / closed-loop`
- `on-board / off-board`
- `mask prompt`
- `object-centric`
- `DCT / FAST tokenization`

Explain by contrast:

```text
state = 世界现在是什么样
action = 机器人做了什么
latent action = 状态变化背后的抽象动作原因
```

### 研究背景 & 基础 & 目的

Answer:

- 这篇论文想解决什么问题？
- 之前方法的缺陷是什么？
- 它是在 VLA、WAM、World Models for VLA、latent-action 还是 robot foundation model 路线上？
- 为什么这个问题对机器人控制重要？

For WAM-related papers, explicitly discuss:

```text
VLA: observation + language -> action
World model: observation + action -> future observation
WAM: observation + language/action context -> future world/action representations + action
World Models for VLA: use world modeling to improve a VLA policy
```

### 研究内容

Always add a model configuration table when possible:

```md
| 维度 | 内容 |
|---|---|
| 模型类型 | |
| 模型骨干 | |
| VLM / LLM backbone | |
| World module | |
| Action module | |
| 动作表示 | |
| 动作生成方式 | |
| 训练方式 | |
| 数据集 | |
| 推理效率 | |
| 是否开源 | |
```

Then describe:

- Overall architecture.
- Input/output.
- Backbone and modules.
- Action representation and generation.
- Training objective.
- Dataset and training recipe.
- Inference process.
- Experiments and ablations.

### 研究结论

Summarize the central claim:

```text
这篇论文真正证明的是：...
```

Use 3 to 6 bullets for concrete findings.

### 感想 & 疑问

Connect the paper to the user's research direction:

- Does it help dynamic object recognition?
- Does it improve fast action execution?
- Does it support closed-loop re-planning?
- Does it reduce inference latency?
- Does it rely on expensive world prediction?
- Is it closer to VLA, WAM, or World Models for VLA?

Add honest questions:

```text
对于打乒乓球/接住掉落物体这类高速动态任务，当前推理频率是否足够？
```

### 研究方法

Use a simple flow diagram:

```text
observation + language
        |
        v
backbone / world module
        |
        v
action generator
        |
        v
action chunk
```

Then list strengths and weaknesses.

## Comparison Hints

When comparing methods, use these dimensions:

- Solved problem: data, action continuity, speed, planning, grounding, memory, RL/value, sim-to-real.
- Action format: token, continuous chunk, latent action, latent motion, diffusion/flow action.
- World modeling: none, future image, future latent, mask future, value future, subgoal image, video context.
- Runtime design: full world prediction, partial denoising, frozen WAM prior, asynchronous planner/executor, test-time scaling.
- Open-source status.

## Common Chinese Phrasing

Useful concise formulations:

```text
这篇论文的关键不是重新设计 VLA 主干，而是...
它更像是 World Models for VLA，而不是纯粹的新 WAM。
它最终输出的是连续 action chunk，不是离散 action token。
论文没有明确报告训练硬件，因此这里不做推测。
```

## Validation Checklist

Before finalizing a note, check:

- Has a Markdown file been created or updated in the requested folder?
- Does it follow the user's section template?
- Does it include model backbone?
- Does it include action representation?
- Does it include training details and hardware if reported?
- Does it include open-source status?
- Does it distinguish facts from inference?
- Does it connect to VLA/WAM and dynamic manipulation relevance?
