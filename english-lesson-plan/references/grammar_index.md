# Grammar Reference Index

This index maps all available grammar books to their key sections for verification use during lesson plan generation.

## Primary Reference: A Comprehensive Grammar of the English Language

By Randolph Quirk, Sidney Greenbaum, Geoffrey Leech, Jan Svartvik (Longman, 1985)
**File**: `/mnt/agents/upload/A Comprehensive Grammar of the English Language（去密码版）.pdf` (895 pages)

| Topic | Section | Pages (0-indexed) | Extracted File |
|-------|---------|---------------------|----------------|
| Verbs & Auxiliaries (Tense, Aspect, Mood, Voice) | Chapter 3 | 52-93 | `comprehensive_grammar_ch3.txt` |
| Semantics of Verb Phrase | Chapter 4 | 96-129 | `comprehensive_grammar_ch4.txt` |
| The Complex Sentence | Chapter 14 | 501-595 | `comprehensive_grammar_ch14_part*.txt` |
| Subordinate Clauses | Chapter 15 | 595-720 | `comprehensive_grammar_ch15_part*.txt` |

### Quick lookup by grammar topic:
- **Tense/Aspect**: Ch3 sections 3.52-3.74, Ch4 sections 4.2-4.68
- **Passive voice**: Ch3 sections 3.63-3.77
- **Subjunctive mood**: Ch3 sections 3.58-3.62
- **Nonfinite verbs**: Ch3 sections 3.53-3.57
- **Coordination**: Ch14 sections 13.1-13.104
- **Subordination**: Ch14 sections 14.1-14.24
- **Nominal clauses**: Ch15 sections 15.3-15.15
- **Relative clauses**: Ch17 sections 17.9-17.26
- **Adverbial clauses**: Ch15 sections 15.17-15.50
- **Conditional clauses**: Ch14 sections 14.23-14.25
- **Reported speech**: Ch14 sections 14.28-14.36

---

## Secondary Reference: 英语语法新思维 (张满胜)

### Book 1: 语法体系及底层逻辑全解密
**File**: `/mnt/agents/upload/英语语法新思维：语法体系及底层逻辑全解密 (张满胜) (Z-Library).pdf` (1347 pages)

| Chapter | Topic | Start Page |
|---------|-------|------------|
| 第01章 | 三类动词及谓语动词短语类型 | 15 |
| 第02章 | 句子的四型谓语结构与四种用途 | 37 |
| 第03章 | 五种基本句型 | 76 |
| 第04章 | 时态：时、态、动、境 | 87 |
| 第05章 | 逆天改命的被动语态 | 263 |
| 第06章 | 多情多义的情态动词 | 301 |
| 第07章 | 虚拟语气 | 337 |
| 第08章 | 主谓倒装 | 389 |
| 第09章 | 主谓一致 | 474 |
| 第10章 | 非谓语动词 | 552 |
| 第11章 | 三大从句的概述 | 668 |
| 第12章 | 名词从句 | 680 |
| 第13章 | 定语从句 | 725 |
| 第14章 | 状语从句及句子的逻辑衔接手段 | 848 |
| 第15章 | 名词、限定及名词短语 | 884 |
| 第16章 | 介词——认知语言学视角 | 960 |
| 第17章 | 副词 | 1081 |

### Book 2: 定语从句+句子成分+名词从句 超精解
**File**: `/mnt/agents/upload/英语语法新思维：（定语从句+句子成分+名词从句）超精解+语法难点妙解（套装共4册） (张满胜) (Z-Library).pdf` (2568 pages)

This is a 4-book set covering relative clauses, sentence components, and noun clauses in extreme detail. Use for in-depth explanations of:
- 定语从句 (relative clauses)
- 句子成分 (sentence components)
- 名词从句 (noun clauses)

---

## Supplementary References (Individual PDFs)

| File | Topic | Pages |
|------|-------|-------|
| `/mnt/agents/upload/2英语语法概观.pdf` | Overview of English grammar | ~50 |
| `/mnt/agents/upload/3动词和助动词.pdf` | Verbs and auxiliaries | 110 |
| `/mnt/agents/upload/10简单句.pdf` | Simple sentence | 123 |
| `/mnt/agents/upload/14复合句.pdf` | Complex sentence | 83 |
| `/mnt/agents/upload/15从属分句的句法和语义功能.pdf` | Subordinate clauses | ~400 |
| `/mnt/agents/upload/8状语的语义和语法.pdf` | Adverbial semantics and grammar | 247 |
| `/mnt/agents/upload/17名词短语.pdf` | Noun phrase | ~300 |

---

## Usage Guide for Grammar Verification

### When analyzing a sentence, consult references in this order:

1. **For tense/aspect questions**: Read `comprehensive_grammar_ch3.txt` or `comprehensive_grammar_ch4.txt`
2. **For clause type questions**: Read relevant parts from `comprehensive_grammar_ch14_part*.txt` or `comprehensive_grammar_ch15_part*.txt`
3. **For detailed Chinese explanations**: Read Zhang Mansheng's book at the relevant chapter page
4. **For specific topics** (passive, subjunctive, nonfinite): Use the index above to locate exact pages

### Read strategy:
- Use `read_file` with `offset` and `limit` to read specific sections
- Search for key terms using `browser_find` equivalent (grep-like) in the file
- For Zhang Mansheng's books, calculate offset from start page (each page ~1000 chars)
