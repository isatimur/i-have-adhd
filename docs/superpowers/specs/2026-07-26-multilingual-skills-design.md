# Multilingual i-have-adhd skills

## Goal

Turn this fork (`isatimur/i-have-adhd`) into a multilingual version of the skill: each
supported language gets its own installable Claude Code skill, not just a translated doc.

## Scope

Add 12 language variants alongside the existing English skill:

Russian (ru), Spanish (es), French (fr), German (de), Portuguese/Brazil (pt-BR),
Chinese Simplified (zh-CN), Japanese (ja), Korean (ko), Hindi (hi), Arabic (ar),
Italian (it), Turkish (tr).

Out of scope: translating README/INSTALL prose beyond a language-index table, and
translating the `.codex-plugin`/`.agents` marketplace descriptions (those stay English —
metadata about the plugin catalog, not the skill's behavior).

## Structure

For each language `<lang>`:

- New folder `skills/i-have-adhd-<lang>/SKILL.md`
- Frontmatter (`name`, `description`) translated so Claude Code's skill matcher can
  trigger it from a same-language request, mirroring the English description's intent
  (when to invoke / when not to).
- Body: the 10 core rules + override rules + pre-send check, translated faithfully.
  Rule numbering and structure stay identical to the English original so the two stay
  easy to diff/compare.
- `agents/openai.yaml` per folder, translated the same way as the existing one, for
  Codex compatibility.

## Plugin registration

Claude Code and Codex plugin configs (`.claude-plugin/plugin.json`,
`.claude-plugin/marketplace.json`, `.codex-plugin/plugin.json`, `.agents/plugins/marketplace.json`)
bundle the whole `skills/` directory under one plugin — no per-skill registration
required, so these files are untouched. This was confirmed by inspecting how the
existing single skill is wired up (no marketplace entry beyond the top-level plugin).

## README changes

Add a short language table near the top of `README.md` linking to each skill folder,
noting these are fork-only additions (not upstreamed to `ayghri/i-have-adhd`).

## Execution plan

Translation is mechanical/parallelizable: one subagent per language, given the English
SKILL.md verbatim and told to produce a faithful translation preserving structure,
rule count, and meaning (not a paraphrase or "localization" that changes the rules).
Agents run concurrently since languages are independent of each other.

## Risks / non-goals

- Translation quality is not natively verified by a Russian/Arabic/etc. speaker on the
  team — best effort by the model, flagged as such.
- Not proposing this back to upstream `ayghri/i-have-adhd`; this lives only on the
  `isatimur` fork per the user's request ("have our own fork").
