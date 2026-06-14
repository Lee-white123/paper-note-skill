---
name: paper-note
description: Generate structured Chinese Markdown notes for VLA, WAM, robotics, embodied AI, world model, diffusion policy, action-tokenization, and robot foundation model papers from PDFs or paper text. Use when the user asks to read papers, create paper notes, follow their note template, summarize model details, compare VLA/WAM methods, or extract backbone, action representation, training recipe, datasets, hardware, inference speed, open-source status, innovations, limitations, and relevance to dynamic manipulation research.
---

# Paper Note

## Core Workflow

When asked to generate paper notes, read the paper source first. Prefer local PDFs or files supplied by the user. If details are missing or likely current, verify with web search only when needed.

For each paper, produce one Markdown note using the user's Chinese note style:

```text
# <论文/模型> 论文笔记
------
## 💡 Meta Data
## 💡基础知识和概念
## 📜 研究背景 & 基础 & 目的
## 📊 研究内容
## 🚩 研究结论
## 📌 感想 & 疑问
## 🔬 研究方法
```

Always include the following high-value fields when available:

- Title, venue/preprint type, authors, publication date, project/code links.
- Model category: VLA, WAM, World Models for VLA, latent-action VLA, robot foundation model, diffusion policy, etc.
- Backbone / model base: VLM, LLM, DiT, AR Transformer, diffusion model, video model, action expert, world expert.
- Action representation: continuous action chunk, action token, latent action, latent motion, trajectory prior, diffusion/flow action, L1 regression.
- Action generation method: next-token prediction, flow matching, diffusion denoising, autoregressive prediction, decoder head, latent planning, MPC-like inference.
- Training recipe: pretraining/post-training/fine-tuning, data sources, dataset scale, sampling, losses, masking, LoRA, frozen modules.
- Hardware and efficiency: GPU/TPU, training steps, batch size, inference latency/frequency, on-board/off-board if reported.
- Open-source status: code/model/data availability; distinguish clearly between "paper gives project page" and "code repository explicitly provided".
- Experiments and results: benchmarks, real robot setup, success rate, ablations, failure cases.
- Relationship to previous papers the user has studied: π series, FAST, GR00T N1, OpenVLA-OFT, UniVLA, CoWVLA, HiF-VLA, Motus, Fast-WAM, OA-WAM.
- Relevance to the user's current research: dynamic object recognition, fast action execution, moving-object manipulation, re-planning, WAM/VLA boundary.

## Writing Style

Write in clear Chinese for a PhD student learning the field. Prefer explanatory notes over terse abstract summaries. Define unfamiliar concepts in the "基础知识和概念" section, but do not overfill it when the user says they will add concepts later.

Use compact tables for model configuration and comparison. Use simple equations or pseudocode blocks when they make mechanisms easier to understand.

When paper details are uncertain, say so explicitly:

```text
论文未明确报告训练 GPU 数量。
截至本笔记整理时，论文只给出 project page，未看到明确 GitHub 代码仓库。
```

Do not invent missing training settings, hardware, code links, or open-source status.

## Output Files

For a single paper, create:

```text
<模型名或论文短名>_论文笔记.md
```

For multiple papers in a folder, create one note per paper in the same folder unless the user specifies another location.

Keep original PDFs unchanged. Do not overwrite user-edited notes unless the user explicitly asks to update the current note.

## Reference

For the detailed reusable checklist and section-level content guidance, read `references/note-template.md` when generating or revising notes.
