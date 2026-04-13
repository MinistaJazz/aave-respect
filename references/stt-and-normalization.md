# STT And Normalization

Use this file when the product includes speech-to-text, captions, transcript cleanup, or post-processing.

## Default rule

The transcript should reflect what the speaker said, not what an SAE-biased cleanup layer thinks they should have said.

## The cost of getting this wrong

In 2015, a speaker's statement "I'm fitna be admitted" was transcribed as "I'm fit to be admitted." Fitna (a variant of finna/fixing to) denotes immediate future intention. "Fit to be" implies qualification or state. The transcription error fundamentally altered the speaker's meaning in a legal context. This is not an edge case. This is the norm when AAVE speakers enter systems built on SAE assumptions.

## Product guidance

- keep raw transcript and normalized transcript as separate artifacts when both are needed
- do not silently replace raw transcript with normalized output
- expose confidence where ambiguity is real instead of "correcting" toward SAE
- preserve user-visible wording in legal, journalistic, historical, or evidentiary contexts

## Post-processing hazards

### Aspect loss

Do not normalize:

- habitual `be`
- stressed `BIN`
- completive `done`
- imminent `finna`
- intensified habitual `stay`

### Copula repair

Do not auto-insert `is/are` in transcript mode.

### Negative cleanup

Do not convert negative concord into SAE.

### Lexical normalization

Do not rewrite:

- `finna` to `going to`
- `gon` to `going to`
- `nah` to `no`
- `ain't` to `isn't/hasn't/didn't` — ain't is a full negation system in AAVE, not informal SAE

unless the product explicitly requests a second normalized artifact.

### Camouflaged forms (highest risk for silent correction)

These look like errors to SAE-biased systems but are grammatically distinct AAVE constructions:

- `I had went` — preterite had (narrative framing), not a tense error. Do not "correct" to "I went"
- `she come telling me` — indignant come (marks uninvited action), not physical movement. Do not "correct" to "she came and told me"
- `I ain't go` — systematic past negation, not missing conjugation. Do not "correct" to "I didn't go"
- `don't let that come out your mouth` — distinct construction, not a missing preposition. Do not insert "of"

These are the forms most likely to be silently normalized because they pass through as "close enough" to SAE. They are not close enough. They carry different meaning.

### Cadence erasure

Do not let punctuation or readability cleanup:

- collapse repetition
- delete pause markers that carry argument structure
- iron out call-and-response texture

## Safer output pattern

When normalization is required:

1. return `verbatim transcript`
2. return `normalized version`
3. label them clearly
4. never substitute one for the other without disclosure
