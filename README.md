# Interactive Textbook Lesson

把一课小学课本做成“能动的互动教材”的通用方法。

## 核心思维

**先读懂课本，再做互动；互动是为理解服务的，不是为热闹服务的。** 换一课只换清单内容，不换这套框架和路线。

## 一课的固定路线

导读 → 理解 → 动手 → 检验 → 巩固 → 应用

- **导读**：从这个年龄学生的真实困惑出发，先问“为什么这么做”，再教“怎么做”，最后放一个数数挑战。
- **理解**：核心例题一字不改，用一张表讲清（情境、每份几个、有几份、加法算式、几个几、乘法算式）。
- **动手**：摆一摆、圈一圈，滑块一动，图、加法、乘法一起变。
- **检验**：判断题＋自测 10 道，答错只给方向提示，不给答案。
- **巩固**：课后作业先逐题列原题，再变题。变式只用四种：换数字、换情境、反着问、加陷阱，并标明不是课本原题。
- **应用**：生活中的“几个几”＋回家任务＋家长陪练卡。

## 互动的动法

一次只走一步，旧步骤留着变淡；一支蓝笔带路（每份几个 → 有几份 → 算式）；先把“几个几”一个一个数出来，再出算式；蓝色画关键数字，黄色/橙色画要数的部分，红色框只框最后答案；每站能重播。

## 配图规矩

原题、变式各配自己的分组点阵图，个数和算式能一个一个数出来；和别人不一样的那一组用橙色标出。只考读法、选算式的题不用配图；依赖课本插图的题不编图，只写“对着课本图做”。

## 例子：别的课完全照这个样子生成

用这套方法做过《认识乘法》（人教版二年级上册第 4 单元第 1 课时）：游乐园三幅图（小飞机 5 个 3、小火车 4 个 6、过山车 7 个 2）＋气球例题（3 个 5），练习九原题逐题列出，每道原题配四种变式和分组点阵图。

**做别的课时，章节、顺序、题型、互动方式、变式种类、配图方式全部照抄这个例子，只换本课的清单内容。** 结构一个都不能少，也不能自己发明新章节。完整的示例（清单、导读 4 问、五方面、理解表、检验题、巩固原题＋变式、应用站）见 [SKILL.md](SKILL.md) 里的“完整示例：《认识乘法》”一节。

## 怎么用

### Claude Code

```bash
# 项目内使用：放到项目 skills 目录
mkdir -p .claude/skills/interactive-textbook-lesson
cp SKILL.md .claude/skills/interactive-textbook-lesson/SKILL.md

# 全局使用：放到个人 skills 目录
mkdir -p ~/.claude/skills/interactive-textbook-lesson
cp SKILL.md ~/.claude/skills/interactive-textbook-lesson/SKILL.md
```

然后在对话里说要做哪一课（课名、版本、页码），Claude 会按 SKILL.md 的方法做。

### Codex

```bash
mkdir -p ~/.codex/skills/interactive-textbook-lesson
cp SKILL.md ~/.codex/skills/interactive-textbook-lesson/SKILL.md
```

然后在 Codex 对话里说要做哪一课（课名、版本、页码），做法同上。

### Muse

放到 `~/workspace/custom-skills/interactive_textbook_lesson/SKILL.md` 即可，做课时按这个 skill 走。

### 其他支持 SKILL.md 的工具

把 `SKILL.md` 放到该工具的 skills 目录下，目录名用 `interactive-textbook-lesson`，做法不变。交付物都是标准 HTML 文件：静态学习卡一个 HTML，互动教材一个自包含的单文件 HTML（CSS、JS 内联，不依赖外链），在哪个工具里都能打开。

## 做一课前要给的信息

- 哪一课、哪个版本、哪几页
- 课本原文、课后习题页（有参考视频也一起给）
- 没给清的，工具会先问清再动手，不猜页码、不编原题
