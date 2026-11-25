---
name: ai-reading-article-maker
description: Process English articles for AI reading practice by removing all Chinese content and splitting sentences into individual paragraphs. Use when the user wants to (1) remove Chinese text, annotations, and markup symbols from an English article, or (2) split an English article into sentence-by-sentence paragraphs for reading aloud, or (3) prepare an English text for AI voice朗读练习. Triggered by requests involving "朗读练习", "去除中文", "句子分割", "逐句", or when the user pastes a mixed Chinese-English article asking for cleaned sentence-separated output.
---

# AI朗读练习文章制作

将输入的英语文章进行两项核心处理：去除所有中文内容及标记，并按句子分割为独立段落。

## 处理流程

### 步骤1：去除中文和标记

- 删除所有中文字符（汉字、中文标点）
- 删除括号内的中文注释，如：`(虚构的)`、`(想象力)`、`(要素)`
- 删除上标/下标编号符号：`①②③④⑤⑥⑦⑧`等
- 删除多余空行，保留段落结构
- 保留英文原文、英文标点、英文括号内的英文内容

### 步骤2：句子分割

- 按英文句号(`.`)、问号(`?`)、感叹号(`!`)分割句子
- 每个句子单独成一段（空行分隔）
- 保留引号内的完整句子不被错误分割
- 标题单独成段
- 小标题（段落标题）单独成段
- 保留原文的段落标题层次结构

## 输出格式

```
[Title]

[Sentence 1]

[Sentence 2]

[Sentence 3]
...
```

## 规则要点

- 英文括号 `()` 内如果是中文则整体删除；如果是英文则保留
- 分句时保留句末标点
- 标题和正文之间用空行分隔
- 连续空行合并为单个空行
- 输出文本可直接复制到AI朗读工具中使用
