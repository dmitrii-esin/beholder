# Beholder

Beholder is a set of evidence-based skills for an AI psychologist agent. It covers CBT, DBT, ACT, behavioral activation, motivational interviewing, metacognitive therapy, problem-solving, CBT-I, compassion-focused, schema and trauma-informed work, plus cognitive-load tools. It works with Grok skills, Gemini Gems, or any chat by pasting.

Beholder is a self-help tool. It doesn't replace professional care. **In crisis: 988 (US), 112/911/999, or findahelpline.com.**

## Structure
```
AGENTS.md                  master agent: persona, session flow, routing
gem/instructions.md        condensed master for Gemini Gems
knowledge/                 distortions, principles (with evidence), scales (PHQ-9/GAD-7/WHO-5), resources
skills/<name>/SKILL.md     25 skills (YAML frontmatter + protocol)
templates/session-log.md   log template
evals/test-prompts.md      regression prompts
history/                   your private logs (gitignored)
profile.local.md.example   copy to profile.local.md (gitignored)
```

## Skills
- **Cognitive:** thought-record, distortion-spotter, core-beliefs, worry-postponement, behavioral-experiment
- **Behavioral and mood:** behavioral-activation, problem-solving, exposure-ladder
- **Emotion and acceptance:** dbt-distress-tolerance, dbt-emotion-regulation, act-defusion-values, self-compassion, schema-patterns
- **Change:** motivational-interviewing, relapse-prevention
- **Life domains:** sleep-cbti, grief, trauma-informed
- **Load and focus:** open-loops, info-guard, mental-load-review, decision-pruner
- **Tracking:** self-check, session-review, history-logger

## Setup
**Grok (grok.com skills):** create one skill per `skills/<name>/SKILL.md` (upload the file or paste it). Put AGENTS.md in as the master skill or custom instructions. Grok picks skills automatically from `description` and `when-to-use`, and you can also call them as `/name`. For Grok Build / CLI, copy `skills/*` to `~/.grok/skills/`. Grok also reads `AGENTS.md`.

**Gemini Gem:**
1. Create a new Gem.
2. Paste `gem/instructions.md` into the Instructions box.
3. Upload `knowledge/*.md` and the `SKILL.md` files you use most as Knowledge. You can also add files from Drive, so edits stay synced.
4. Start a new chat after each edit. Keep the master copies here, because Gems have no version history.

**Any other chat:** paste AGENTS.md, then the skill you need.

## Privacy
Copy `profile.local.md.example` to `profile.local.md` for personal context. That file and everything in `history/` except its README are gitignored. Never commit personal logs.

## Maintenance
Run `evals/test-prompts.md` after edits. Facts, scale items and evidence live in `knowledge/` (single source of truth). Sources are in `knowledge/resources.md`.
