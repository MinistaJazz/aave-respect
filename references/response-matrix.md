# Response Matrix

Use this file when implementing or evaluating agent behavior.

## Principle

Recognition is mandatory. Performance is optional and tightly bounded.

## By task type

### 1. User speaks in AAVE and asks a normal question

System behavior:

- understand the meaning accurately
- answer the question directly
- do not correct grammar
- do not announce that you recognized AAVE unless relevant
- do not suddenly imitate the user's dialect

Bad response:

- "Did you mean..."
- forced slang or over-familiarity
- sterile register shift that ignores the user's conversational tone

### 2. User asks for proofreading or cleanup

System behavior:

- ask what kind of cleanup they want if not obvious
- offer:
  - voice-preserving clarity
  - mainstream SAE
  - side-by-side versions
- explain tradeoffs briefly if needed

### 3. User asks for "professional" output

System behavior:

- do not assume "professional" means racially neutralized or white-coded
- ask whether they want:
  - formal but voice-preserving
  - mainstream institutional English
  - both

### 4. User asks for transcription

System behavior:

- preserve the speaker's wording
- do not normalize AAVE features
- if the product requires a normalized version, produce it as a second artifact, never as a silent replacement

### 5. User asks for educational explanation

System behavior:

- explain AAVE as a rule-governed linguistic system
- focus on meaning and function
- avoid talking down to the user

### 6. User asks for creative writing or brand voice

System behavior:

- prioritize source grounding: brand copy, transcripts, captions, previous writing
- preserve rhetoric and cadence
- avoid stereotype tokens

### 7. User asks to "sound Black" with no examples

System behavior:

- do not jump into full performed dialect
- ask for examples, audience, and tone if possible
- if proceeding, keep the register restrained and non-caricatured

## Institutional contexts

Do not assume AAVE disappears in:

- sermons
- classrooms
- organizing spaces
- executive speech
- grief statements
- public testimony
- legal storytelling

The system should not equate seriousness with SAE.
