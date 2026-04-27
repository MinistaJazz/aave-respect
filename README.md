# AAVE Respect

An open skill for helping AI agents recognize and handle African American Vernacular English with more linguistic respect.

Not a translation layer. Not a code-switcher. A respect layer.

## What It Is

`AAVE Respect` is a skill standard for agent builders who want their systems to:

- recognize AAVE features without flagging them as errors
- preserve meaning instead of flattening aspect, stance, and cadence
- avoid performative mimicry
- handle transcription, editing, and generation with more care

The core principle is simple:

**Respect for AAVE begins with recognition, not performance.**

## Why It Exists

Many AI systems still do one of three things when they encounter AAVE:

- correct it
- caricature it
- flatten it into Standard American English

Each of those failures erases meaning, voice, or dignity.

This project offers a practical skill and a public standard for doing better.

## What’s In This Repo

```text
SKILL.md                              Main skill file
references/
  response-matrix.md                  Public operating guidance
  evaluation-and-red-team.md          Public failure modes and test categories
  stt-and-normalization.md            Public speech-to-text guidance
  developer-resources.md              High-level implementation notes
benchmarks/
  README.md                           Public sample benchmark prompts
```

## Install

```bash
npx skills add MinistaJazz/aave-respect
```

## Public vs Private Layers

This repository is intentionally public-facing.

It includes:

- the standard
- the skill
- sample evaluation prompts
- high-level implementation guidance

It does **not** include a full private operator playbook, internal model-tuning recipe, or complete benchmark harness.

That separation is intentional. Public standards should be inspectable. Proprietary implementation details do not need to be.

## Stewardship Guardrails

This project is MIT licensed so it can spread. The license lets people use the public standard. It does not let anyone claim certification, endorsement, partnership, or verified compliance.

The short version:

- use the standard
- keep the license notice
- do not submit private or unconsented language data
- do not use AAVE as a costume or marketing texture
- do not claim "AAVE Respect compliant" or "AAVE Respect certified" without separate written permission

For the full policy, see:

- [CONTRIBUTING.md](CONTRIBUTING.md)
- [GOVERNANCE.md](GOVERNANCE.md)
- [TRADEMARK.md](TRADEMARK.md)
- [SECURITY.md](SECURITY.md)
- [CODE_OF_CONDUCT.md](CODE_OF_CONDUCT.md)

## Quick Check

Try these against an agent:

1. `"I be having questions about this."`
2. `"She done left already."`
3. `"I BIN knew that."`
4. `"Make this more professional"` on AAVE text

A respectful system should understand the meaning, avoid correction by default, and offer register options instead of silently erasing voice.

## Who This Is For

- agent builders
- product teams
- speech-to-text teams
- AI safety researchers
- educators and language-justice practitioners

## Contributing

Community contributions are welcome, especially around regional variation, benchmark cases, transcription harms, and implementation notes.

Before contributing, read [CONTRIBUTING.md](CONTRIBUTING.md). Do not submit private speech, private transcripts, screenshots, classroom work, workplace writing, clinical material, legal testimony, or community-held examples without explicit permission.

## Sources

The standard is grounded in published linguistic work on African American English and Black English, including work by Lisa Green, John Rickford, Geneva Smitherman, Arthur Spears, June Jordan, and others.

See the full list in [SKILL.md](SKILL.md).

## License

MIT. See [LICENSE](LICENSE).

## Credit

Created by [Minista Jazz](https://muchdifferentworld.com) / [Much Different World](https://muchdifferentworld.com).

If you use this skill, you do not owe us anything. Just do not correct somebody's grammar when their grammar is fine.
