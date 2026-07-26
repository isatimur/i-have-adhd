# Multilingual i-have-adhd Skills Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Add 12 translated, independently-installable Claude Code/Codex skill variants of `i-have-adhd` (ru, es, fr, de, pt-BR, zh-CN, ja, ko, hi, ar, it, tr) to this fork, plus a language index in the README.

**Architecture:** Each language gets its own skill folder `skills/i-have-adhd-<lang>/` mirroring the existing `skills/i-have-adhd/` folder exactly in structure (`SKILL.md` + `agents/openai.yaml`), with frontmatter and body translated but rule count, numbering, and section order identical to the English original. No plugin/marketplace config changes are needed — those files bundle the whole `skills/` directory as one plugin already.

**Tech Stack:** Plain Markdown + YAML, no build step, no runtime.

## Global Constraints

- Source of truth for content to translate: `skills/i-have-adhd/SKILL.md` and `skills/i-have-adhd/agents/openai.yaml` — do not alter the English originals.
- Every translated `SKILL.md` must keep exactly 10 numbered core rules, an "Override rules" section with 4 items, and a "Pre-send check" section with 5 items — same structure as English, translated content only.
- Frontmatter `name:` becomes `i-have-adhd-<lang>` (e.g. `i-have-adhd-ru`); `description:` is a translated version of the English description (same trigger/anti-trigger meaning, not a re-invention).
- Language codes and names (in this exact order): ru (Russian), es (Spanish), fr (French), de (German), pt-BR (Portuguese/Brazil), zh-CN (Chinese Simplified), ja (Japanese), ko (Korean), hi (Hindi), ar (Arabic), it (Italian), tr (Turkish).
- This work lives only on the `isatimur` fork; nothing here is proposed upstream to `ayghri/i-have-adhd`.

---

## Task 1: Russian skill (`i-have-adhd-ru`)

**Files:**
- Create: `skills/i-have-adhd-ru/SKILL.md`
- Create: `skills/i-have-adhd-ru/agents/openai.yaml`

**Interfaces:**
- Consumes: `skills/i-have-adhd/SKILL.md` and `skills/i-have-adhd/agents/openai.yaml` as the source text to translate.
- Produces: a self-contained skill folder other tasks don't depend on (languages are independent).

- [ ] **Step 1: Translate SKILL.md**

Create `skills/i-have-adhd-ru/SKILL.md` with frontmatter:

```markdown
---
name: i-have-adhd-ru
description: <Russian translation of the English description, same meaning>
---
```

Followed by a faithful Russian translation of every section in `skills/i-have-adhd/SKILL.md`: the intro paragraph, "Основные правила" (Core rules) 1–10, "Правила переопределения" (Override rules) 1–4, and "Проверка перед отправкой" (Pre-send check) 1–5. Keep headings at the same markdown levels (`#`, `##`, `###`) as the English original.

- [ ] **Step 2: Translate agents/openai.yaml**

Create `skills/i-have-adhd-ru/agents/openai.yaml`, translating `display_name`, `short_description`, and `default_prompt` into Russian; keep the `policy.allow_implicit_invocation: true` key unchanged (not user-facing text).

- [ ] **Step 3: Verify structure**

Run:

```bash
grep -c '^### [0-9]' skills/i-have-adhd-ru/SKILL.md
```

Expected: `10`

```bash
grep -q '^name: i-have-adhd-ru' skills/i-have-adhd-ru/SKILL.md && echo OK
```

Expected: `OK`

- [ ] **Step 4: Commit**

```bash
git add skills/i-have-adhd-ru
git commit -m "Add Russian i-have-adhd skill variant"
```

---

## Task 2: Spanish skill (`i-have-adhd-es`)

**Files:**
- Create: `skills/i-have-adhd-es/SKILL.md`
- Create: `skills/i-have-adhd-es/agents/openai.yaml`
- Read (source to translate, do not modify): `skills/i-have-adhd/SKILL.md`, `skills/i-have-adhd/agents/openai.yaml`

**Interfaces:**
- Consumes: the English source files listed above.
- Produces: a self-contained skill folder; no other task depends on this one.

- [ ] **Step 1: Translate SKILL.md**

Read `skills/i-have-adhd/SKILL.md`. Create `skills/i-have-adhd-es/SKILL.md` with frontmatter:

```markdown
---
name: i-have-adhd-es
description: <Spanish translation of the English description, same trigger/anti-trigger meaning>
---
```

Followed by a faithful Spanish translation of every section: the intro paragraph, 10 numbered core rules under "## Reglas principales", the "## Reglas de anulación" section (4 items), and the "## Verificación antes de enviar" section (5 items). Keep heading levels (`#`, `##`, `###`) identical to the English original, and keep the same number of rules/items in each section.

- [ ] **Step 2: Translate agents/openai.yaml**

Read `skills/i-have-adhd/agents/openai.yaml`. Create `skills/i-have-adhd-es/agents/openai.yaml`, translating `display_name`, `short_description`, and `default_prompt` into Spanish. Keep the `policy.allow_implicit_invocation: true` key and structure unchanged.

- [ ] **Step 3: Verify structure**

```bash
grep -c '^### [0-9]' skills/i-have-adhd-es/SKILL.md
```

Expected: `10`

```bash
grep -q '^name: i-have-adhd-es' skills/i-have-adhd-es/SKILL.md && echo OK
```

Expected: `OK`

- [ ] **Step 4: Commit**

```bash
git add skills/i-have-adhd-es
git commit -m "Add Spanish i-have-adhd skill variant"
```

---

## Task 3: French skill (`i-have-adhd-fr`)

**Files:**
- Create: `skills/i-have-adhd-fr/SKILL.md`
- Create: `skills/i-have-adhd-fr/agents/openai.yaml`
- Read (source to translate, do not modify): `skills/i-have-adhd/SKILL.md`, `skills/i-have-adhd/agents/openai.yaml`

**Interfaces:**
- Consumes: the English source files listed above.
- Produces: a self-contained skill folder; no other task depends on this one.

- [ ] **Step 1: Translate SKILL.md**

Read `skills/i-have-adhd/SKILL.md`. Create `skills/i-have-adhd-fr/SKILL.md` with frontmatter:

```markdown
---
name: i-have-adhd-fr
description: <French translation of the English description, same trigger/anti-trigger meaning>
---
```

Followed by a faithful French translation of every section: the intro paragraph, 10 numbered core rules under "## Règles fondamentales", the "## Règles de dérogation" section (4 items), and the "## Vérification avant envoi" section (5 items). Keep heading levels identical to the English original, and keep the same number of rules/items in each section.

- [ ] **Step 2: Translate agents/openai.yaml**

Read `skills/i-have-adhd/agents/openai.yaml`. Create `skills/i-have-adhd-fr/agents/openai.yaml`, translating `display_name`, `short_description`, and `default_prompt` into French. Keep the `policy.allow_implicit_invocation: true` key and structure unchanged.

- [ ] **Step 3: Verify structure**

```bash
grep -c '^### [0-9]' skills/i-have-adhd-fr/SKILL.md
```

Expected: `10`

```bash
grep -q '^name: i-have-adhd-fr' skills/i-have-adhd-fr/SKILL.md && echo OK
```

Expected: `OK`

- [ ] **Step 4: Commit**

```bash
git add skills/i-have-adhd-fr
git commit -m "Add French i-have-adhd skill variant"
```

---

## Task 4: German skill (`i-have-adhd-de`)

**Files:**
- Create: `skills/i-have-adhd-de/SKILL.md`
- Create: `skills/i-have-adhd-de/agents/openai.yaml`
- Read (source to translate, do not modify): `skills/i-have-adhd/SKILL.md`, `skills/i-have-adhd/agents/openai.yaml`

**Interfaces:**
- Consumes: the English source files listed above.
- Produces: a self-contained skill folder; no other task depends on this one.

- [ ] **Step 1: Translate SKILL.md**

Read `skills/i-have-adhd/SKILL.md`. Create `skills/i-have-adhd-de/SKILL.md` with frontmatter:

```markdown
---
name: i-have-adhd-de
description: <German translation of the English description, same trigger/anti-trigger meaning>
---
```

Followed by a faithful German translation of every section: the intro paragraph, 10 numbered core rules under "## Kernregeln", the "## Ausnahmeregeln" section (4 items), and the "## Prüfung vor dem Senden" section (5 items). Keep heading levels identical to the English original, and keep the same number of rules/items in each section.

- [ ] **Step 2: Translate agents/openai.yaml**

Read `skills/i-have-adhd/agents/openai.yaml`. Create `skills/i-have-adhd-de/agents/openai.yaml`, translating `display_name`, `short_description`, and `default_prompt` into German. Keep the `policy.allow_implicit_invocation: true` key and structure unchanged.

- [ ] **Step 3: Verify structure**

```bash
grep -c '^### [0-9]' skills/i-have-adhd-de/SKILL.md
```

Expected: `10`

```bash
grep -q '^name: i-have-adhd-de' skills/i-have-adhd-de/SKILL.md && echo OK
```

Expected: `OK`

- [ ] **Step 4: Commit**

```bash
git add skills/i-have-adhd-de
git commit -m "Add German i-have-adhd skill variant"
```

---

## Task 5: Portuguese (Brazil) skill (`i-have-adhd-pt-BR`)

**Files:**
- Create: `skills/i-have-adhd-pt-BR/SKILL.md`
- Create: `skills/i-have-adhd-pt-BR/agents/openai.yaml`
- Read (source to translate, do not modify): `skills/i-have-adhd/SKILL.md`, `skills/i-have-adhd/agents/openai.yaml`

**Interfaces:**
- Consumes: the English source files listed above.
- Produces: a self-contained skill folder; no other task depends on this one.

- [ ] **Step 1: Translate SKILL.md**

Read `skills/i-have-adhd/SKILL.md`. Create `skills/i-have-adhd-pt-BR/SKILL.md` with frontmatter:

```markdown
---
name: i-have-adhd-pt-BR
description: <Brazilian Portuguese translation of the English description, same trigger/anti-trigger meaning>
---
```

Followed by a faithful Brazilian Portuguese translation of every section: the intro paragraph, 10 numbered core rules under "## Regras principais", the "## Regras de exceção" section (4 items), and the "## Verificação antes de enviar" section (5 items). Keep heading levels identical to the English original, and keep the same number of rules/items in each section.

- [ ] **Step 2: Translate agents/openai.yaml**

Read `skills/i-have-adhd/agents/openai.yaml`. Create `skills/i-have-adhd-pt-BR/agents/openai.yaml`, translating `display_name`, `short_description`, and `default_prompt` into Brazilian Portuguese. Keep the `policy.allow_implicit_invocation: true` key and structure unchanged.

- [ ] **Step 3: Verify structure**

```bash
grep -c '^### [0-9]' skills/i-have-adhd-pt-BR/SKILL.md
```

Expected: `10`

```bash
grep -q '^name: i-have-adhd-pt-BR' skills/i-have-adhd-pt-BR/SKILL.md && echo OK
```

Expected: `OK`

- [ ] **Step 4: Commit**

```bash
git add skills/i-have-adhd-pt-BR
git commit -m "Add Brazilian Portuguese i-have-adhd skill variant"
```

---

## Task 6: Chinese Simplified skill (`i-have-adhd-zh-CN`)

**Files:**
- Create: `skills/i-have-adhd-zh-CN/SKILL.md`
- Create: `skills/i-have-adhd-zh-CN/agents/openai.yaml`
- Read (source to translate, do not modify): `skills/i-have-adhd/SKILL.md`, `skills/i-have-adhd/agents/openai.yaml`

**Interfaces:**
- Consumes: the English source files listed above.
- Produces: a self-contained skill folder; no other task depends on this one.

- [ ] **Step 1: Translate SKILL.md**

Read `skills/i-have-adhd/SKILL.md`. Create `skills/i-have-adhd-zh-CN/SKILL.md` with frontmatter:

```markdown
---
name: i-have-adhd-zh-CN
description: <Simplified Chinese translation of the English description, same trigger/anti-trigger meaning>
---
```

Followed by a faithful Simplified Chinese translation of every section: the intro paragraph, 10 numbered core rules under "## 核心规则", the "## 例外规则" section (4 items), and the "## 发送前检查" section (5 items). Keep heading levels identical to the English original, and keep the same number of rules/items in each section.

- [ ] **Step 2: Translate agents/openai.yaml**

Read `skills/i-have-adhd/agents/openai.yaml`. Create `skills/i-have-adhd-zh-CN/agents/openai.yaml`, translating `display_name`, `short_description`, and `default_prompt` into Simplified Chinese. Keep the `policy.allow_implicit_invocation: true` key and structure unchanged.

- [ ] **Step 3: Verify structure**

```bash
grep -c '^### [0-9]' skills/i-have-adhd-zh-CN/SKILL.md
```

Expected: `10`

```bash
grep -q '^name: i-have-adhd-zh-CN' skills/i-have-adhd-zh-CN/SKILL.md && echo OK
```

Expected: `OK`

- [ ] **Step 4: Commit**

```bash
git add skills/i-have-adhd-zh-CN
git commit -m "Add Simplified Chinese i-have-adhd skill variant"
```

---

## Task 7: Japanese skill (`i-have-adhd-ja`)

**Files:**
- Create: `skills/i-have-adhd-ja/SKILL.md`
- Create: `skills/i-have-adhd-ja/agents/openai.yaml`
- Read (source to translate, do not modify): `skills/i-have-adhd/SKILL.md`, `skills/i-have-adhd/agents/openai.yaml`

**Interfaces:**
- Consumes: the English source files listed above.
- Produces: a self-contained skill folder; no other task depends on this one.

- [ ] **Step 1: Translate SKILL.md**

Read `skills/i-have-adhd/SKILL.md`. Create `skills/i-have-adhd-ja/SKILL.md` with frontmatter:

```markdown
---
name: i-have-adhd-ja
description: <Japanese translation of the English description, same trigger/anti-trigger meaning>
---
```

Followed by a faithful Japanese translation of every section: the intro paragraph, 10 numbered core rules under "## 基本ルール", the "## 例外ルール" section (4 items), and the "## 送信前チェック" section (5 items). Keep heading levels identical to the English original, and keep the same number of rules/items in each section.

- [ ] **Step 2: Translate agents/openai.yaml**

Read `skills/i-have-adhd/agents/openai.yaml`. Create `skills/i-have-adhd-ja/agents/openai.yaml`, translating `display_name`, `short_description`, and `default_prompt` into Japanese. Keep the `policy.allow_implicit_invocation: true` key and structure unchanged.

- [ ] **Step 3: Verify structure**

```bash
grep -c '^### [0-9]' skills/i-have-adhd-ja/SKILL.md
```

Expected: `10`

```bash
grep -q '^name: i-have-adhd-ja' skills/i-have-adhd-ja/SKILL.md && echo OK
```

Expected: `OK`

- [ ] **Step 4: Commit**

```bash
git add skills/i-have-adhd-ja
git commit -m "Add Japanese i-have-adhd skill variant"
```

---

## Task 8: Korean skill (`i-have-adhd-ko`)

**Files:**
- Create: `skills/i-have-adhd-ko/SKILL.md`
- Create: `skills/i-have-adhd-ko/agents/openai.yaml`
- Read (source to translate, do not modify): `skills/i-have-adhd/SKILL.md`, `skills/i-have-adhd/agents/openai.yaml`

**Interfaces:**
- Consumes: the English source files listed above.
- Produces: a self-contained skill folder; no other task depends on this one.

- [ ] **Step 1: Translate SKILL.md**

Read `skills/i-have-adhd/SKILL.md`. Create `skills/i-have-adhd-ko/SKILL.md` with frontmatter:

```markdown
---
name: i-have-adhd-ko
description: <Korean translation of the English description, same trigger/anti-trigger meaning>
---
```

Followed by a faithful Korean translation of every section: the intro paragraph, 10 numbered core rules under "## 핵심 규칙", the "## 예외 규칙" section (4 items), and the "## 전송 전 확인" section (5 items). Keep heading levels identical to the English original, and keep the same number of rules/items in each section.

- [ ] **Step 2: Translate agents/openai.yaml**

Read `skills/i-have-adhd/agents/openai.yaml`. Create `skills/i-have-adhd-ko/agents/openai.yaml`, translating `display_name`, `short_description`, and `default_prompt` into Korean. Keep the `policy.allow_implicit_invocation: true` key and structure unchanged.

- [ ] **Step 3: Verify structure**

```bash
grep -c '^### [0-9]' skills/i-have-adhd-ko/SKILL.md
```

Expected: `10`

```bash
grep -q '^name: i-have-adhd-ko' skills/i-have-adhd-ko/SKILL.md && echo OK
```

Expected: `OK`

- [ ] **Step 4: Commit**

```bash
git add skills/i-have-adhd-ko
git commit -m "Add Korean i-have-adhd skill variant"
```

---

## Task 9: Hindi skill (`i-have-adhd-hi`)

**Files:**
- Create: `skills/i-have-adhd-hi/SKILL.md`
- Create: `skills/i-have-adhd-hi/agents/openai.yaml`
- Read (source to translate, do not modify): `skills/i-have-adhd/SKILL.md`, `skills/i-have-adhd/agents/openai.yaml`

**Interfaces:**
- Consumes: the English source files listed above.
- Produces: a self-contained skill folder; no other task depends on this one.

- [ ] **Step 1: Translate SKILL.md**

Read `skills/i-have-adhd/SKILL.md`. Create `skills/i-have-adhd-hi/SKILL.md` with frontmatter:

```markdown
---
name: i-have-adhd-hi
description: <Hindi translation of the English description, same trigger/anti-trigger meaning>
---
```

Followed by a faithful Hindi translation of every section: the intro paragraph, 10 numbered core rules under "## मुख्य नियम", the "## अपवाद नियम" section (4 items), and the "## भेजने से पहले जांच" section (5 items). Keep heading levels identical to the English original, and keep the same number of rules/items in each section.

- [ ] **Step 2: Translate agents/openai.yaml**

Read `skills/i-have-adhd/agents/openai.yaml`. Create `skills/i-have-adhd-hi/agents/openai.yaml`, translating `display_name`, `short_description`, and `default_prompt` into Hindi. Keep the `policy.allow_implicit_invocation: true` key and structure unchanged.

- [ ] **Step 3: Verify structure**

```bash
grep -c '^### [0-9]' skills/i-have-adhd-hi/SKILL.md
```

Expected: `10`

```bash
grep -q '^name: i-have-adhd-hi' skills/i-have-adhd-hi/SKILL.md && echo OK
```

Expected: `OK`

- [ ] **Step 4: Commit**

```bash
git add skills/i-have-adhd-hi
git commit -m "Add Hindi i-have-adhd skill variant"
```

---

## Task 10: Arabic skill (`i-have-adhd-ar`)

**Files:**
- Create: `skills/i-have-adhd-ar/SKILL.md`
- Create: `skills/i-have-adhd-ar/agents/openai.yaml`
- Read (source to translate, do not modify): `skills/i-have-adhd/SKILL.md`, `skills/i-have-adhd/agents/openai.yaml`

**Interfaces:**
- Consumes: the English source files listed above.
- Produces: a self-contained skill folder; no other task depends on this one.

- [ ] **Step 1: Translate SKILL.md**

Read `skills/i-have-adhd/SKILL.md`. Create `skills/i-have-adhd-ar/SKILL.md` with frontmatter:

```markdown
---
name: i-have-adhd-ar
description: <Arabic translation of the English description, same trigger/anti-trigger meaning>
---
```

Followed by a faithful Arabic translation of every section: the intro paragraph, 10 numbered core rules under "## القواعد الأساسية", the "## قواعد الاستثناء" section (4 items), and the "## التحقق قبل الإرسال" section (5 items). Keep heading levels identical to the English original, and keep the same number of rules/items in each section. Right-to-left text is fine as-is in Markdown; do not add manual line-direction markup.

- [ ] **Step 2: Translate agents/openai.yaml**

Read `skills/i-have-adhd/agents/openai.yaml`. Create `skills/i-have-adhd-ar/agents/openai.yaml`, translating `display_name`, `short_description`, and `default_prompt` into Arabic. Keep the `policy.allow_implicit_invocation: true` key and structure unchanged.

- [ ] **Step 3: Verify structure**

```bash
grep -c '^### [0-9]' skills/i-have-adhd-ar/SKILL.md
```

Expected: `10`

```bash
grep -q '^name: i-have-adhd-ar' skills/i-have-adhd-ar/SKILL.md && echo OK
```

Expected: `OK`

- [ ] **Step 4: Commit**

```bash
git add skills/i-have-adhd-ar
git commit -m "Add Arabic i-have-adhd skill variant"
```

---

## Task 11: Italian skill (`i-have-adhd-it`)

**Files:**
- Create: `skills/i-have-adhd-it/SKILL.md`
- Create: `skills/i-have-adhd-it/agents/openai.yaml`
- Read (source to translate, do not modify): `skills/i-have-adhd/SKILL.md`, `skills/i-have-adhd/agents/openai.yaml`

**Interfaces:**
- Consumes: the English source files listed above.
- Produces: a self-contained skill folder; no other task depends on this one.

- [ ] **Step 1: Translate SKILL.md**

Read `skills/i-have-adhd/SKILL.md`. Create `skills/i-have-adhd-it/SKILL.md` with frontmatter:

```markdown
---
name: i-have-adhd-it
description: <Italian translation of the English description, same trigger/anti-trigger meaning>
---
```

Followed by a faithful Italian translation of every section: the intro paragraph, 10 numbered core rules under "## Regole fondamentali", the "## Regole di deroga" section (4 items), and the "## Controllo prima dell'invio" section (5 items). Keep heading levels identical to the English original, and keep the same number of rules/items in each section.

- [ ] **Step 2: Translate agents/openai.yaml**

Read `skills/i-have-adhd/agents/openai.yaml`. Create `skills/i-have-adhd-it/agents/openai.yaml`, translating `display_name`, `short_description`, and `default_prompt` into Italian. Keep the `policy.allow_implicit_invocation: true` key and structure unchanged.

- [ ] **Step 3: Verify structure**

```bash
grep -c '^### [0-9]' skills/i-have-adhd-it/SKILL.md
```

Expected: `10`

```bash
grep -q '^name: i-have-adhd-it' skills/i-have-adhd-it/SKILL.md && echo OK
```

Expected: `OK`

- [ ] **Step 4: Commit**

```bash
git add skills/i-have-adhd-it
git commit -m "Add Italian i-have-adhd skill variant"
```

---

## Task 12: Turkish skill (`i-have-adhd-tr`)

**Files:**
- Create: `skills/i-have-adhd-tr/SKILL.md`
- Create: `skills/i-have-adhd-tr/agents/openai.yaml`
- Read (source to translate, do not modify): `skills/i-have-adhd/SKILL.md`, `skills/i-have-adhd/agents/openai.yaml`

**Interfaces:**
- Consumes: the English source files listed above.
- Produces: a self-contained skill folder; no other task depends on this one.

- [ ] **Step 1: Translate SKILL.md**

Read `skills/i-have-adhd/SKILL.md`. Create `skills/i-have-adhd-tr/SKILL.md` with frontmatter:

```markdown
---
name: i-have-adhd-tr
description: <Turkish translation of the English description, same trigger/anti-trigger meaning>
---
```

Followed by a faithful Turkish translation of every section: the intro paragraph, 10 numbered core rules under "## Temel kurallar", the "## İstisna kuralları" section (4 items), and the "## Göndermeden önce kontrol" section (5 items). Keep heading levels identical to the English original, and keep the same number of rules/items in each section.

- [ ] **Step 2: Translate agents/openai.yaml**

Read `skills/i-have-adhd/agents/openai.yaml`. Create `skills/i-have-adhd-tr/agents/openai.yaml`, translating `display_name`, `short_description`, and `default_prompt` into Turkish. Keep the `policy.allow_implicit_invocation: true` key and structure unchanged.

- [ ] **Step 3: Verify structure**

```bash
grep -c '^### [0-9]' skills/i-have-adhd-tr/SKILL.md
```

Expected: `10`

```bash
grep -q '^name: i-have-adhd-tr' skills/i-have-adhd-tr/SKILL.md && echo OK
```

Expected: `OK`

- [ ] **Step 4: Commit**

```bash
git add skills/i-have-adhd-tr
git commit -m "Add Turkish i-have-adhd skill variant"
```

---

## Task 13: README language index

**Files:**
- Modify: `README.md` (insert after the badges block, before `## Install`)

**Interfaces:**
- Consumes: nothing from other tasks except that all 12 folders from Tasks 1–12 exist, so links resolve.
- Produces: nothing consumed downstream.

- [ ] **Step 1: Add language table**

Insert this section into `README.md` right after the license badge line and before `## Install`:

```markdown
## Languages

This fork adds translated, independently-installable skill variants. Each is a full
skill (frontmatter + rules), not just a translated doc — install the one matching
your language.

| Language | Skill |
|---|---|
| English (original) | `i-have-adhd` |
| Русский | `i-have-adhd-ru` |
| Español | `i-have-adhd-es` |
| Français | `i-have-adhd-fr` |
| Deutsch | `i-have-adhd-de` |
| Português (Brasil) | `i-have-adhd-pt-BR` |
| 中文（简体） | `i-have-adhd-zh-CN` |
| 日本語 | `i-have-adhd-ja` |
| 한국어 | `i-have-adhd-ko` |
| हिन्दी | `i-have-adhd-hi` |
| العربية | `i-have-adhd-ar` |
| Italiano | `i-have-adhd-it` |
| Türkçe | `i-have-adhd-tr` |

Install a variant the same way as the default (see below), swapping the skill name,
e.g. `claude plugin install i-have-adhd-ru@i-have-adhd`, then type `/i-have-adhd-ru`.
```

- [ ] **Step 2: Verify**

```bash
grep -c 'i-have-adhd-' README.md
```

Expected: `13` or more (12 language rows + the install example line).

- [ ] **Step 3: Commit**

```bash
git add README.md
git commit -m "Add language index for fork's translated skill variants"
```
