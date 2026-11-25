---
name: english-lesson-plan
description: Generate sentence-by-sentence lesson plans for English reading texts. Use when the user asks for sentence-by-sentence lesson plans, reading analysis, or any English article/text analysis for teaching purposes. Supports articles with or without Before you read sections, comprehension quizzes, vocabulary exercises, and translation tasks. The skill handles argumentative, expository, narrative, news reports, research reports, and any English reading material for Chinese ESL students. All grammar explanations MUST be verified against authoritative grammar references before output. Output is a formatted Word document (.docx) with an 8-section structure including cover page.
---

# English Lesson Plan Generator

Generate detailed, sentence-by-sentence lesson plans for English reading texts as a formatted Word document. All grammar explanations MUST be verified against authoritative grammar references. No grammar claim may be made without cross-checking.

## CRITICAL RULE 1: Sentence-by-Sentence Analysis -- NO OMISSIONS, NO ADDITIONS

**This rule is ABSOLUTE and NON-NEGOTIABLE.**

When generating the sentence-by-sentence analysis (Section 2 of the document), you MUST:

1. **Analyze EVERY single sentence** in the original text without exception
2. **Do NOT skip or omit any sentence** -- no matter how short, simple, or repetitive
3. **Do NOT fabricate or add any sentence** that does not exist in the original text
4. **Follow the exact sentence order** as given in the original text
5. **Quote each sentence verbatim** before analyzing it -- do not paraphrase the original sentence in the "Original sentence" field

**Enforcement**: After completing Section 2, verify the sentence count matches the original text. If the original has 30 sentences, Section 2 must have exactly 30 sentence analyses. No more, no less.

**Short sentences**: Even a sentence like "So what?" or "It is." MUST be analyzed with all 7 items.

**Consequences of violation**: Omitted sentences destroy the pedagogical value of the lesson plan. Students rely on this document for complete coverage of the text.

## CRITICAL RULE 2: Grammar Verification Is Mandatory

**Every single grammar analysis MUST be verified before output.** This includes:
- Clause type identification (relative, nominal, adverbial)
- Tense and aspect classification
- Voice (active/passive) classification
- Sentence structure (inversion, cleft, extraposition, etc.)
- Mood (indicative, subjunctive, imperative)
- Non-finite verb forms

**Common errors to avoid:**
- Do NOT assume a sentence is "simple" without checking for inversion, fronting, or ellipsis
- Do NOT misidentify the subject when inversion occurs (e.g., predicative fronting: "By far the largest... is Yulong Mountain" -- "By far the largest..." is the fronted predicative, NOT the subject; the subject is "Yulong Mountain")
- Do NOT label a clause type without verifying against the reference

## Step 1: Read the uploaded file

Read the uploaded article/docx/pdf using `read_file`. Extract all text content including title, Before you read section, body text, and any quiz/vocabulary exercises.

## Step 2: Consult the workflow reference

Read `references/workflow.md` for the complete document structure template, sentence analysis template, and section-by-section formatting guidance. This file contains:
- 8-section document structure template
- Cover page requirements
- Sentence-by-sentence analysis format (7 items per sentence)
- Templates for vocabulary, reading comprehension, translation, sentence structure, and summary sections

## Step 3: Grammar verification -- MANDATORY for EVERY sentence

For EACH sentence in the body text, before writing any analysis:

### 3.1 Identify the grammar question

Determine what grammar structures are present in the sentence. Ask yourself:
- Is there inversion? (Check for fronted predicative, fronted adverbial, negative fronting)
- What is the ACTUAL subject? (Be careful with inverted sentences)
- What clauses are present? (Verify each one)
- What is the tense/aspect? Verify with reference.

### 3.2 Consult the grammar reference -- MANDATORY

Read the relevant grammar reference file using `read_file` with `offset` and `limit`. Search for the specific grammar topic. Key references:

| Grammar Topic | Reference File | Search Keywords |
|---------------|----------------|-----------------|
| Tense & Aspect | `references/comprehensive_grammar_ch3.txt` | "tense", "aspect", "present", "past", "perfect", "progressive" |
| Tense Semantics | `references/comprehensive_grammar_ch4.txt` | "simple present", "simple past", "future" |
| Passive Voice | `references/comprehensive_grammar_ch3.txt` | "passive", "voice" |
| Complex Sentence (coordination, conditionals, reported speech) | `references/comprehensive_grammar_ch14_part*.txt` | "conditional", "reported speech", "coordination" |
| Subordinate Clauses (nominal, relative, adverbial) | `references/comprehensive_grammar_ch15_part*.txt` | "nominal clause", "relative clause", "adverbial clause" |
| Inversion & Fronting | Zhang Mansheng Ch.8 (p.389+) | "inversion", "fronting" |
| Subjunctive Mood | `references/comprehensive_grammar_ch3.txt` + Zhang Ch.7 (p.337+) | "subjunctive" |
| Non-finite Verbs | `references/comprehensive_grammar_ch3.txt` | "nonfinite", "infinitive", "participle", "gerund" |

For **each grammar claim**, you MUST:
1. Read the relevant reference section
2. Confirm your analysis matches the reference
3. If uncertain, read more context or consult a second reference

### 3.3 Document the verification

After verifying, include a brief citation in the analysis:
> (Verification basis: Quirk et al. Ch.18; Zhang Mansheng vol.1 ch.8)

## Step 4: Build the Word document

Use the docx skill to create a formatted Word document with the following structure. Read the docx skill SKILL.md first for C# + OpenXML SDK patterns.

### Document structure (8 sections):

1. **Cover page**: Title (English, large), subtitle with em-dash, "sentence-by-sentence lesson plan" label, article metadata (text type, source, word count, Flesch-Kincaid Grade Level, theme context)
2. **Table of contents**: All 9 sections listed
3. **Before you read**: Suggested warm-up questions (3, in English) + classroom guidance strategies (3 bullets, in Chinese with rationale) + key language points
4. **Sentence-by-sentence analysis**: Each sentence as H2 with 7 analysis items (see workflow.md template)
5. **Vocabulary exercises**: Word matching + fill-in-blanks + phrase translation
6. **Reading comprehension**: Each question with answer + detailed explanation
7. **Translation exercises**: Reference answer + key structure analysis
8. **Sentence structure analysis**: Structure breakdown + model translation
9. **Text structure summary**: Fill-in-blank table answers
10. **Full summary**: Teaching value, grammar points, vocabulary, cultural background, reading focus
11. **Summary writing analysis**: Discourse pattern identification + 3+2 structure breakdown + 60-word model summary (see workflow.md Section 9 template)

### Sentence analysis format (7 items per sentence):
1. Tense usage
2. Voice
3. Clause analysis
4. Sentence structure (bold key structures)
5. Fixed collocations
6. Cultural background
7. Verification basis

### Key formatting rules:
- Bold key grammar structures when they appear (see workflow.md for full list)
- Mark important/long sentences with "(key long sentence)" in the heading
- Group short related sentences together under one heading
- Provide natural Chinese translations
- Always include verification basis citing specific grammar book chapters

## Step 5: Summary

End with the full summary (section 8) covering:
- Before you read teaching value
- Key grammar points (ALL verified, with citations)
- Core vocabulary & collocations
- Cultural background knowledge
- Reading comprehension focus points

## Reference Files

| File | Purpose |
|------|---------|
| `references/workflow.md` | Complete document structure, analysis templates, and formatting guidance |
| `references/grammar_index.md` | Index of all grammar books with chapter maps |
| `references/comprehensive_grammar_ch3.txt` | Quirk et al. Ch.3: Verbs & Auxiliaries (Tense, Aspect, Mood, Voice) |
| `references/comprehensive_grammar_ch4.txt` | Quirk et al. Ch.4: Semantics of Verb Phrase |
| `references/comprehensive_grammar_ch14_part*.txt` | Quirk et al. Ch.14: Complex Sentence |
| `references/comprehensive_grammar_ch15_part*.txt` | Quirk et al. Ch.15: Subordinate Clauses |
| `references/english_grammar_new_thinking_complete_system.pdf` | Zhang Mansheng: Complete grammar system |
| `references/english_grammar_new_thinking_clauses.pdf` | Zhang Mansheng: Detailed clause analysis |
