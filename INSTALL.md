# Install i-have-adhd

A Claude Code plugin. One skill inside.

## TL;DR

### Claude Code

```bash
git clone https://github.com/ayghri/i-have-adhd ./i-have-adhd
claude plugin marketplace add ./i-have-adhd
claude plugin install i-have-adhd@i-have-adhd
```

Open Claude Code, type `/i-have-adhd`.

To disable: `claude plugin disable i-have-adhd` (or `/plugin disable i-have-adhd` from within Claude Code). Re-enable later with `enable` instead of `disable`.

### Codex

```bash
codex plugin marketplace add ayghri/i-have-adhd --ref main
codex plugin add i-have-adhd@i-have-adhd
```

In Codex, type `$i-have-adhd` to request the output style explicitly.

### Antigravity (`agy`)

```bash
git clone https://github.com/ayghri/i-have-adhd ./i-have-adhd
agy plugin install ./i-have-adhd
```

In Antigravity, type `/skills` to verify that `i-have-adhd` is loaded. The skill is automatically loaded and applied based on prompt context.

To disable: `agy plugin disable i-have-adhd`.

## Verify

### Claude Code

```bash
claude plugin list
```

Look for `i-have-adhd  (enabled)`.

### Codex

```bash
codex plugin list
```

Look for `i-have-adhd` in the configured `i-have-adhd` marketplace.

### Antigravity (`agy`)

```bash
agy plugin list
```

Look for `i-have-adhd` in the list of installed plugins.

## Update

### Claude Code

```bash
cd ./i-have-adhd && git pull
```

The marketplace re-reads the local checkout. Next Claude Code session picks up changes.

### Codex

```bash
codex plugin marketplace upgrade i-have-adhd
codex plugin remove i-have-adhd
codex plugin add i-have-adhd@i-have-adhd
```

### Antigravity (`agy`)

```bash
agy plugin uninstall i-have-adhd
agy plugin install /path/to/local/plugin
```

## Uninstall

### Claude Code

```bash
claude plugin uninstall i-have-adhd
claude plugin marketplace remove i-have-adhd
```

### Codex

```bash
codex plugin remove i-have-adhd
codex plugin marketplace remove i-have-adhd
```

### Antigravity (`agy`)

```bash
agy plugin uninstall i-have-adhd
```

## Always-on (optional)

To skip invoking the skill and apply the rules from message one:

### Claude Code

Add to `~/.claude/CLAUDE.md`:

```markdown
## Output style

Always follow the rules in the `i-have-adhd` skill: action-first, numbered steps, no preamble, no closers, state restated each turn.
```

### Antigravity (`agy`)

Add to `~/.gemini/GEMINI.md`:

```markdown
## Output style

Always follow the rules in the `i-have-adhd` skill: action-first, numbered steps, no preamble, no closers, state restated each turn.
```

## Troubleshooting

**`/i-have-adhd` not in autocomplete.** Restart Claude Code. The plugin index is read at startup.

**`claude plugin marketplace add` fails.** Point at the repo root, not at `.claude-plugin/`. The path must contain `.claude-plugin/marketplace.json`.

**Skill activates but model still preambles.** Open a new session. Old context may carry. If it still drifts, tighten the rule wording in `skills/i-have-adhd/SKILL.md`, then re-invoke.

**Want different rules.** Edit `skills/i-have-adhd/SKILL.md`. Re-invoke `/i-have-adhd` (or restart) and the new rules apply.
