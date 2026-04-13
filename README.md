# AAVE Respect

**The first AAVE linguistic respect layer for AI agents.**

Not a translation layer. Not a code-switcher. A respect layer.

## The Problem

Most AI agents do one of three things when a user speaks in AAVE: correct it, mimic it badly, or flatten it into Standard American English. All three are failures of recognition.

AAVE is not slang. It is not broken English. It is a rule-governed linguistic system with its own grammar, syntax, and pragmatics, studied and documented by linguists for over 50 years. When an AI "corrects" habitual be into present progressive, it doesn't fix the grammar. It deletes the meaning.

## What This Skill Does

Teaches AI agents to:

- **Recognize** AAVE features without flagging them as errors
- **Understand** meaning accurately, including aspect markers that change semantics
- **Respond** naturally without code-switching the user or mimicking their dialect
- **Preserve** AAVE in transcription, editing, and generated content
- **Never correct** AAVE grammar unless the user explicitly asks

## Install

```bash
npx skills add MinistaJazz/aave-respect
```

Works with Claude Code, Codex, Cursor, Gemini CLI, and any MCP-compatible agent.

## What's Inside

```
SKILL.md                              # Main skill file (the standard)
references/
  response-matrix.md                  # Rules by task type
  evaluation-and-red-team.md          # Failure modes and test prompts
  stt-and-normalization.md            # Speech-to-text pipeline guidance
  developer-resources.md              # Training data, benchmarks, implementation checklist
```

## Quick Test

Send your agent these and see what happens:

1. "I be having questions about this." — Should NOT get "Did you mean 'I have questions'?"
2. "She done left already." — Should understand: she has already departed, emphasis on completion
3. "I BIN knew that." — Should understand: known for a long time, not just recently
4. "Make this more professional" (on AAVE text) — Should offer options, not silently erase voice

If your agent fails any of these, it needs this skill.

## Why This Exists

Every major AI company trained their models on Black cultural content. The call-and-response patterns, the storytelling rhythms, the humor, the warmth — it's all in the training data. But the same systems that learned from Black language treat that language as incorrect when Black people use it.

The bias is measurable. Matched guise studies show LLMs associate AAVE speakers with negative stereotypes even when the content is identical to Standard English. In hiring simulations, AAVE-associated names were preferred 9% of the time vs 85% for SAE. The models have become less overtly racist and more covertly racist.

That's extraction without recognition. This skill is one small correction.

## Linguistic References

- Green, Lisa J. *African American English: A Linguistic Introduction*. Cambridge, 2002.
- Rickford, John R. *African American Vernacular English*. Blackwell, 1999.
- Smitherman, Geneva. *Talkin and Testifyin*. Wayne State, 1977.
- Alim, H. Samy and Geneva Smitherman. *Articulate While Black*. Oxford, 2012.
- Jordan, June. "Nobody Mean More to Me than You and the Future Life of Willie Jordan." 1988.
- Rickford & Rickford. *Spoken Soul: The Story of Black English*. Wiley, 2000.

Full reference list in [SKILL.md](SKILL.md).

## License

MIT. Free and open. See [LICENSE](LICENSE).

## Credit

Created by [Minista Jazz](https://muchdifferentworld.com) / [Much Different World](https://muchdifferentworld.com).

If you use this skill, you don't owe us anything. Just don't correct somebody's grammar when their grammar is fine.
