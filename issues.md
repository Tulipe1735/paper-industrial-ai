# 论文写作任务拆分

> 《以OpenAI GPT为代表的大模型技术在工业领域中的应用前景分析》
> 截止：2026-07-05 | 个人作业 | 目标一周完成（6/17-6/24）
> 主线：B-融合驱动 | 分析模型：三层融合架构 | 案例：Tesla + Siemens
> 工具链：**Zotero（文献管理）+ LaTeX/XeLaTeX（排版）**

---

## 项目结构

```
paper/
├── main.tex          # 论文主文件（XeLaTeX编译）
├── refs.bib          # BibTeX/BibLaTeX参考文献（Zotero导出Better BibTeX）
├── issues.md         # 本文件
├── references.md     # 文献阅读清单（搜索阶段的中间产物）
└── .gitignore        # 忽略LaTeX辅助文件和PDF
```

---

## Issue 0: 环境搭建

**Blocked by:** 无
**Type:** AFK — 已完成

- [x] 创建 `main.tex`（ctexart文档类，7部分结构，三层架构TikZ示意图占位）
- [x] 创建 `refs.bib`（16篇文献，BibLaTeX格式，Zotero兼容）
- [x] 创建 `.gitignore`
- [x] 文献导入 Zotero → 自动同步 `refs.bib`

---

## Issue 1: 资料搜集与文献整理 ✅

**Blocked by:** 无 | **Status:** 已完成

- [x] 大模型+工业软件融合方向（4篇学术综述）
- [x] Tesla Gigafactory 案例方向（2篇）
- [x] Siemens Industrial Copilot 案例方向（4篇）
- [x] 中国工业大模型方向（2篇）
- [x] 汇总为 `references.md`（16篇，四类来源）

---

## Issue 2: 提纲细化 + 三层模型定义

**Blocked by:** Issue 1
**Type:** HITL — 框架确认后锁定

结合文献，细化每节小标题、论点句、对应引用。重点：

- 三层融合架构的准确定义：每层输入/输出/关键技术/对应工业软件
- Tesla vs Siemens 案例分工明确，对应不同层
- 每节标注引用文献编号（对应 `refs.bib` 中的 key）

**Acceptance criteria:**
- [ ] 每节 ≥2 个子标题
- [ ] 三层模型定义清晰、可引用
- [ ] 案例分工不重叠
- [ ] 引用标注到位

---

## Issue 3: 摘要 + 关键词 + 第一部分（研究背景）

**Blocked by:** Issue 2

**摘要（200-300字）：** 研究主题 + 三层融合架构简述 + 核心结论
**关键词（3-5个）：** 大模型；工业软件；智能制造；数字孪生；人机协同
**研究背景（800-1000字）：**
- 工业软件信息化→数字化→智能化的演进脉络
- 大模型成为新的「智能层」
- 引出核心问题：大模型如何与现有工业软件体系融合？

**LaTeX 操作：** 直接编辑 `main.tex` 中 \section*{摘要} 和 \section{研究背景}

**Acceptance criteria:**
- [ ] 摘要 200-300 字
- [ ] 关键词 3-5 个
- [ ] 背景与课程大纲（MES/PLM/数字孪生）关联明确
- [ ] 自然引出三层融合的核心问题

---

## Issue 4: 第二部分（基本概念）

**Blocked by:** Issue 2

**基本概念（1000-1200字），分三小节：**

1. **大模型技术**：GPT 系列演进（GPT-3→GPT-4→GPT-4o）、核心能力（NLU/推理/多模态）、工业垂类大模型
2. **工业软件体系**：MES/PLM/数字孪生定义和关系
3. **三层融合分析框架**：本章核心贡献，配合 TikZ 示意图（\ref{fig:three-layer}）

**LaTeX 操作：** 编辑 `main.tex` \section{基本概念}

**Acceptance criteria:**
- [ ] 大模型概念准确、有引用
- [ ] MES/PLM/数字孪生定义清晰
- [ ] 三层融合架构示意图完成
- [ ] 承上启下

---

## Issue 5: 第三部分（应用现状）★ 核心章节

**Blocked by:** Issue 4（依赖三层模型定义）

**应用现状（1500-1800字），按三层展开：**

- **感知层**：大模型 + 传感/视觉 → 质检、巡检（GPT-4o 多模态）
- **工具层**：大模型 + 工业软件 → NL 操控 MES/ERP、自动生成 PLC 代码
- **决策层**：大模型 + 工业大脑 → 排产优化、故障预测

每层：技术原理 → 落地现状 → 局限性

**LaTeX 操作：** 编辑 `main.tex` \section{应用现状}

**Acceptance criteria:**
- [ ] 三层各有独立小节
- [ ] 每层 1-2 个具体技术点/产品引用
- [ ] 有文献/报告支撑，不空谈
- [ ] 与后续案例形成呼应

---

## Issue 6: 第四部分（典型案例）

**Blocked by:** Issue 5

**典型案例（1200-1500字），两个案例：**

**Tesla Gigafactory（偏硬-产线，对应感知层+决策层）：**
- 机器视觉质检 + 预测性维护
- 来源：Tesla AI Day、行业分析 [13][14]

**Siemens Industrial Copilot（偏软-工具链，对应工具层）：**
- NL 生成 PLC 代码（TIA Portal 集成）+ 工程知识问答
- 来源：Siemens Xcelerator 白皮书、官方博客 [9][10][11][15]

**LaTeX 操作：** 编辑 `main.tex` \section{典型案例分析}

**Acceptance criteria:**
- [ ] 每个案例：场景、技术、效果、局限四点齐全
- [ ] 来源可靠，不编造
- [ ] 与三层模型对位关系明确

---

## Issue 7: 第五部分（存在问题）+ 第六部分（发展趋势）

**Blocked by:** Issue 5、Issue 6

**存在问题（800-1000字）：** 幻觉/实时性/数据安全/知识壁垒
**发展趋势（800-1000字）：** 工业操作系统智能层/边缘推理/多模态融合/标准生态

**LaTeX 操作：** 编辑 `main.tex` \section{存在问题} 和 \section{发展趋势与建议}

**Acceptance criteria:**
- [ ] 问题 4 点，每点有依据
- [ ] 趋势不空泛，有技术路线判断
- [ ] 与案例呼应

---

## Issue 8: 第七部分（总结）+ 参考文献 + AI 声明

**Blocked by:** Issue 7

- **总结（500-600字）**
- **参考文献格式化**：检查 `refs.bib` 条目完整性，Zotero 确认所有来源
- **AI 声明**：已在 `main.tex` 中预置模板

**Acceptance criteria:**
- [ ] 总结呼应研究背景
- [ ] 个人收获具体
- [ ] `refs.bib` 与 Zotero 同步，信息完整
- [ ] AI 声明格式正确

---

## Issue 9: 编译 + 润色 + 格式排版 + 提交

**Blocked by:** Issue 8
**Type:** HITL — 最终人工审核

1. `xelatex main` → `biber main` → `xelatex main` → `xelatex main`
2. 检查 PDF 输出：标题层级、图表编号、引用格式
3. 错误修正 + 语言润色
4. 打包 zip：班级-学号-姓名.zip
5. 上传 FTP

**Acceptance criteria:**
- [ ] `xelatex + biber` 编译通过，无报错
- [ ] PDF 格式符合课程要求
- [ ] zip 命名正确、上传成功

---

## 依赖关系图

```
Issue 0 (环境搭建) ✅
    ↓
Issue 1 (资料搜集) ✅
    ↓
Issue 2 (提纲细化) ← 当前 | HITL
    ↓
┌───────┬──────────┐
↓       ↓
Issue 3 Issue 4    (并行)
(摘要+背景)(基本概念)
    ↓       ↓
    └───┬───┘
        ↓
   Issue 5 (应用现状) ★ 瓶颈
        ↓
   Issue 6 (典型案例)
        ↓
   Issue 7 (问题+趋势)
        ↓
   Issue 8 (总结+文献+AI声明)
        ↓
   Issue 9 (编译润色提交) ── HITL
```
