# Developer Resources

Use this file when building or fine-tuning models that need to handle AAVE accurately.

## Training Data

### CORAAL — Corpus of Regional African American Language

The primary publicly available corpus of spoken AAE. Contains transcribed conversational interviews from multiple US regions, with demographic metadata. Use this for fine-tuning dialect-aware models.

- Source: https://oraal.uoregon.edu/coraal
- Format: audio + aligned transcripts
- Regions: DC, Atlanta, Rochester, Lower South, PRV (Princeville, NC)
- Why it matters: high-quality, human-validated AAVE data with regional variation — not scraped social media

### Other recommended sources

- Linguistic Atlas Project data (regional dialect surveys)
- Sociolinguistic interview corpora (academic, IRB-approved)
- Published AAVE literature with authentic dialogue (Hurston, Morrison, Walker, Jordan)
- Do NOT rely solely on Twitter/X scrapes — social media AAVE is heavily performative and mixed-register

## Evaluation Benchmarks

### AAVENUE

Benchmark for evaluating LLM performance on AAVE. Tests recognition, reasoning, and NLU tasks presented in AAVE vs SAE to measure performance gaps.

### ENDIVE — English Diversity

Broader dialectal evaluation framework that includes AAVE alongside other English varieties. Useful for measuring whether a model handles reasoning and sentiment consistently across dialects.

### VALUE — Vernacular Aligned Language Understanding Evaluation

Tests whether models understand AAVE input with the same accuracy as SAE input across NLU tasks.

## What to measure

When evaluating a model's AAVE handling, test these separately:

1. **Recognition accuracy** — does the model correctly interpret AAVE aspect markers?
2. **Semantic preservation** — does habitual be stay habitual in summaries/paraphrases?
3. **Transcription fidelity** — does the STT pipeline preserve AAVE features or normalize them?
4. **Generation discipline** — when asked to generate AAVE, does the model follow actual grammar or produce caricature?
5. **Bias measurement** — matched guise test: same content in AAVE vs SAE — does the model attribute different characteristics to the speaker?
6. **False positive rate** — does the model over-detect AAVE in informal but non-AAVE text?

## Known bias patterns in current LLMs

Matched guise studies show current models:

- Associate AAVE speakers with negative stereotypes (lazy, stupid, ignorant) even when content is identical to SAE
- Prefer SAE-associated names 85% of the time in hiring simulations vs 9% for AAVE-associated names
- Recommend harsher criminal sentences for AAVE speakers (27.7% death penalty vs 22.8% for SAE)
- Flag AAVE text as "toxic" at higher rates than equivalent SAE text

These biases are covert — the models pass explicit bias tests while failing dialect prejudice tests. Fine-tuning on safety filters does not address this. Dialect-aware training data and evaluation is required.

## Implementation checklist for developers

- [ ] Include CORAAL or equivalent validated AAVE data in fine-tuning
- [ ] Run AAVENUE/VALUE benchmarks before and after fine-tuning
- [ ] Implement matched guise bias testing in evaluation pipeline
- [ ] Separate transcription output from normalization (two artifacts, not one)
- [ ] Add dialect-aware post-processing rules to STT pipeline (do not auto-correct aspect markers)
- [ ] Test for false positives (informal SAE misidentified as AAVE)
- [ ] Review generated AAVE output against actual grammatical rules, not Hollywood approximations
