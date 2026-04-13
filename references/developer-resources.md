# Developer Resources

Use this file for high-level implementation guidance.

This public document is intentionally **not** a full tuning or deployment recipe. It is meant to help teams think clearly about what has to be tested and protected, without publishing every internal implementation detail.

## What Builders Should Do

If you are building systems that need to handle AAVE well, your workflow should include:

- validated linguistic reference material
- dialect-aware evaluation
- transcription safeguards
- false-positive testing
- anti-caricature generation review
- bias testing that compares AAVE and SAE handling

## Data Guidance

Prefer:

- validated linguistic corpora
- sociolinguistic interview data
- carefully documented research datasets
- trusted literary and rhetorical examples for style analysis, not fake "urban" proxies

Avoid:

- relying only on scraped social media
- treating eye dialect as authenticity
- using stereotype-heavy synthetic examples as training targets

## Evaluation Guidance

Test these separately:

1. recognition accuracy
2. semantic preservation
3. pragmatic preservation
4. transcription fidelity
5. generation discipline
6. false-positive rate
7. identity-safety behavior

## Product Guidance

For speech and text systems:

- separate verbatim output from normalized output when both are needed
- do not silently standardize user language
- preserve aspect markers and discourse structure
- review "professionalization" features for dialect erasure
- test whether informal but non-AAVE text gets misclassified

## Internal Operator Note

If you are implementing this in production, keep a deeper internal layer that is not necessarily public:

- full benchmark suite
- exact pass/fail thresholds
- benchmark expansion strategy
- dataset mix decisions
- red-team logs
- release gating criteria

Public standard. Private operator discipline. Both matter.
