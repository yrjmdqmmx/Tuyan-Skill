# Tuyan Scientific Figure Skill

图研 Tuyan 的跨 Agent 科研图示 Skill。它在用户自己的 Agent 和本地文件系统中完成科研图示的分类、FigureSpec、可选参考检索、生成、定性评审、精修与可复现归档。

支持 8 类视觉任务：方法框架图、流程图、系统架构图、机制示意图、对比图、时间线、数据统计图和概念关系图；支持 `create`、`refine`、`evaluate` 三种工作流。

## 隐私边界

- 论文、图片、提示词、API Key、FigureSpec、草图和成品始终留在用户本机。
- Skill 只会向图研匿名 MCP 发送 5 个固定枚举，不会发送任何研究内容。
- MCP 不可用时自动使用 Skill 内置的离线知识快照。
- PaperBananaBench 只会在用户明确同意后，从固定上游 revision 下载到本机；图研不重新托管该数据集。上游当前未声明数据集许可证。

## Codex 安装

先下载 Skill 仓库：

```bash
git clone --depth 1 https://github.com/yrjmdqmmx/Tuyan-Skill.git
mkdir -p ~/.agents/skills
cp -R Tuyan-Skill/tuyan-scientific-figure ~/.agents/skills/tuyan-scientific-figure
```

再单独安装匿名 MCP（无需克隆 MCP 仓库）：

```bash
codex mcp add tuyan --url https://api.paperbanana.asia/mcp
codex mcp list
```

新建 Codex 任务后可显式调用 `$tuyan-scientific-figure`。如果只安装 Skill，也能通过离线快照完整执行本地工作流；安装 MCP 可以获得版本化的最新公共模板、规则和 Schema。

OpenClaw、Hermes 和工作区级安装方式见 [客户端安装指南](tuyan-scientific-figure/references/client-installation.md)。首版仅以 Codex 完成真实端到端验收，不宣称已完成 OpenClaw 或 Hermes 的真实客户端验收。

## 本地输出

默认输出到 `./tuyan-output/<timestamp>-<slug>/`，包含 FigureSpec、实际提示词、参考来源、各轮草图、定性 Critique、最终 PNG/真 SVG，以及记录文件 SHA-256、知识版本和 Retriever 状态的 `manifest.json`。数据统计图还会保存原始数据和绘图代码。

## 开发与校验

```bash
npm test
npm run check
```

Skill 主目录是 [`tuyan-scientific-figure/`](tuyan-scientific-figure/)，其中 `SKILL.md` 使用标准 Agent Skills frontmatter。

## 相关项目

- [图研 Tuyan 主仓库](https://github.com/yrjmdqmmx/Tuyan)
- [Tuyan MCP 独立仓库](https://github.com/yrjmdqmmx/Tuyan-MCP)
- [图研工作台与 Benchmark](https://www.paperbanana.asia/)

## 开源声明

本项目采用 [Apache License 2.0](LICENSE) 发布，由图研社区独立维护，不是 PaperBanana 上游官方发行版。详见 [NOTICE](NOTICE)。
