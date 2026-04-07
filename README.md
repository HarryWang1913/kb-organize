# 个人知识库启动包

一套基于 AI 的个人知识库搭建方案。不需要编程基础，只需要 [Obsidian](https://obsidian.md/)（免费笔记软件）+ 一个能读写 Markdown 文件的 AI 助手，大约 30 分钟就能搭好自己的知识库。

---

## 1. 这是什么

这不是一个数据库，也不是一个全自动归档器。

这是一套**「让 AI 按规则持续维护你的个人知识」的结构化模板**。

你负责判断"什么值得记住"，AI 负责帮你分类、打标签、建链接、更新索引。你积累的知识越多，这套系统就越有价值——因为 AI 会自动帮你维护知识之间的关联，让旧知识和新知识真正连起来。

---

## 2. 适合谁

- **有长期知识积累需求的个人创作者**：写公众号、做短视频、运营个人品牌的人
- **知识工作者**：顾问、销售、研究者、教师、设计师、产品经理……靠经验和知识吃饭的人
- **想用 Obsidian + AI 搭建知识库，但不想先学复杂技术的人**
- **已经有一些笔记、文章、课程内容，想把它们真正"用起来"的人**

---

## 3. 不适合谁

- 主要存客户隐私、财务数据、合同原件的人（这些不应该交给 AI 处理）
- 希望"一键自动整理全部资料"的人（知识管理需要你持续参与判断）
- 还没有任何内容积累、只想先搭复杂系统的人（先有内容，再建系统）

---

## 4. 方法论来源

### Karpathy LLM Wiki

[Andrej Karpathy](https://x.com/karpathy)（前特斯拉 AI 总监、OpenAI 联合创始人）在 2025 年公开了他用 AI 维护个人知识库的方法。核心思想很简单：

> **知识管理的瓶颈不是"阅读"，而是"记账"。**

人写完笔记就忘了更新索引、补链接、加标签。但 AI 不会忘。它可以同时修改 15 个文件，自动维护交叉引用，让你的每一次学习都能复利。

本启动包直接采用了他的三层架构（原始素材 → 概念页 → 索引），并扩展为适合中文用户的四层架构。

### GBrain

[Garry Tan](https://x.com/garrytan)（Y Combinator CEO）也分享了类似的实践：用 AI 把日常读的文章、开的会、学的课都整合进一个知识库。他的经验验证了一个观点：**这套方法不只适合技术人员，任何靠知识吃饭的人都能用**。

---

## 5. 你需要准备什么

- [Obsidian](https://obsidian.md/)（免费，本地笔记软件）
- 一个能读写 Markdown 文件的 AI 助手
  - 推荐：Claude + [Claudian 插件](https://claudian.app/)
  - 也可以使用：ChatGPT、Cursor、其他同类 AI 工具
- 大约 30 分钟完成初始化

---

## 6. 文件夹结构

```
_starter-kit/
├── 00_schema/
│   ├── AGENTS.md                        ← AI 操作规则
│   ├── SKILL.md                         ← 整理技能说明
│   └── references/
│       ├── tag-taxonomy.md              ← 标签体系
│       └── templates.md                 ← 文件模板
├── 概念/
│   └── 概念示例_你的核心主题.md            ← 概念页模板
├── index.md                             ← 知识库总索引
├── sources.md                           ← 外部素材导航
├── .gitignore
└── README.md                            ← 本文件
```

---

## 7. 推荐初始化顺序

不要一次搭完所有东西。按这 4 步来：

1. **先改 `00_schema/AGENTS.md`** — 填你的名字、行业、核心概念、主要产出
2. **复制并改写第一个概念页** — 把 `概念/概念示例_你的核心主题.md` 改成你自己的核心概念
3. **补 `index.md`** — 把你的概念页和已有文件加进索引
4. **导入外部素材** — 把你的课程笔记、行业文章等放进来，在 `sources.md` 中登记

---

## 8. 快速开始（5步）

### 第1步：下载并打开

把这个文件夹下载到本地，用 Obsidian 打开它（选「打开文件夹作为仓库」）。

### 第2步：修改 AGENTS.md

打开 `00_schema/AGENTS.md`，把里面的占位符改成你自己的信息。这是 AI 每次工作前必读的规则文件，填得越准确，AI 帮你整理的效果越好。

### 第3步：建你的第一个概念页

把 `概念/概念示例_你的核心主题.md` 复制一份，改个名字。写上你对这个主题当前最核心的判断（不需要写很多，3 句话就够了）。

这是知识库的核心——概念页不是笔记，是你对一个主题「现在怎么看」的实时快照。

### 第4步：导入外部素材

把你积累的文章、课程笔记、行业报告放到一个独立文件夹（建议叫「外部素材」或类似名字），然后在 `sources.md` 里登记。

重要原则：**外部素材只读，不修改原文**。读完后把有价值的洞察整合到概念页里。

### 第5步：建立日常使用习惯

- 写完新内容 → 让 AI 帮你加标签和链接（对 AI 说「帮我把这篇文章入库」）
- 读到好文章 → 提炼 3 句洞察写进概念页
- 每月 → 让 AI 做一次 Lint 检查（对 AI 说「检查一下知识库」）

---

## 9. 踩坑经验

这些是实际使用中踩过的坑，提前避开能省很多时间：

### ❌ 把别人的内容和自己的内容混在一起
> 外部文章和你自己的笔记必须分开放。外部素材只读，你的思考写进概念页。混在一起会让你分不清哪些是自己的判断，哪些是别人的观点。

### ❌ 概念页只有结论，没有时间线
> 概念页最大的价值是「时间线」——你什么时候改过想法、为什么改。没有时间线的概念页三个月后你自己都不知道当时为什么这么写。

### ❌ 想先把所有资料整理完再开始
> 不要等。先建一个概念页，先整理 3 篇文章，先用起来。知识库是"越用越有用"的，不是"越完美越有用"的。

### ❌ 工具越搭越复杂，反而用不起来
> 不要装太多插件、不要设计太复杂的分类。这套启动包故意做得很轻量——概念页 + 标签 + 索引，够用了。

### ❌ AI 每次都忘了先读规则
> 每次让 AI 帮你整理知识库时，开头说一句：「先读 00_schema/AGENTS.md」。这是让 AI 按你的规则工作而不是乱来的关键。

---

## 10. 核心使用原则

**AI 负责：**
- 分类、归档
- 更新交叉引用和反向链接
- 维护标签和索引的一致性
- 按模板格式化新文件

**你负责：**
- 判断什么值得放进知识库
- 写「当前判断」——AI 帮你整理，但判断是你的
- 提出问题、检查质量
- 决定什么时候更新概念页的结论

---

## 11. 使用提醒

> ⚠️ **请不要把以下内容直接交给 AI 工具处理：**
>
> - 客户的姓名、身份证、联系方式
> - 财务账户、合同原件
> - 医疗记录、法律文件

本启动包更适合管理你的：

- 知识和方法论
- 文章和课程笔记
- 公开资料
- 可脱敏后的总结材料
- 行业洞察和判断

---

## 12. 致谢

- [Andrej Karpathy](https://x.com/karpathy) — LLM Wiki 方法论的提出者，证明了用 AI 维护个人知识库的可行性
- [Garry Tan](https://x.com/garrytan) — GBrain 实践的分享者，验证了这套方法对非技术人员同样有效

---

## 13. License

MIT License

Copyright (c) 2026

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
