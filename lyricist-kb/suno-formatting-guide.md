# Suno AI Formatting & Metatags Complete Guide

> Updated for Suno V4.5 / V5 / V5.5 (2026)

## Overview

Suno metatags are keywords enclosed in square brackets `[ ]` that you insert into your lyrics to control song structure, vocal delivery, instrumentation, mood, and production. They act as stage directions for the AI.

**Key principles:**
- Metatags go in the **Lyrics** field (not the Style field)
- Style/genre descriptors go in the **Style** field (plain text, comma-separated, NO brackets)
- Keep metatags short: 1-3 words works best
- Most impactful in the first 20-30 words and at section transitions
- V4.5+ supports up to 1,000 characters in the style prompt (older models ~200)

---

## 1. Structure Tags

These define the architecture of your song. Always use them — writing lyrics without structure tags is the most common beginner mistake.

### Primary Structure Tags

| Tag | Purpose | Notes |
|-----|---------|-------|
| `[Intro]` | Opening section | Can specify instrument: `[Intro: Acoustic Guitar]` |
| `[Verse]` | Narrative/story section | Number them: `[Verse 1]`, `[Verse 2]` |
| `[Verse 1]` | First verse | More specific than bare `[Verse]` |
| `[Pre-Chorus]` | Builds tension before chorus | Lifts energy, often shorter |
| `[Chorus]` | Main hook / climax | Where energy peaks |
| `[Post-Chorus]` | Comes after chorus | Sustains energy, often instrumental-heavy |
| `[Bridge]` | Contrasting section | Usually appears once, before final chorus |
| `[Outro]` | Closing section | Can specify fade: `[Outro: Fade Out]` |
| `[End]` | Hard stop | Forces the song to end cleanly |

### Extended Structure Tags

| Tag | Purpose |
|-----|---------|
| `[Instrumental]` | No vocals, instruments only |
| `[Instrumental Break]` | Short instrumental passage |
| `[Interlude]` | Transitional passage between sections |
| `[Break]` | Stripped-back moment (often drums or bass only) |
| `[Drop]` | EDM-style drop — full energy hit after buildup |
| `[Buildup]` | Rising tension leading to drop or chorus |
| `[Hook]` | Short, catchy melodic phrase |
| `[Refrain]` | Repeated phrase (shorter than chorus) |
| `[Solo]` | Instrumental solo section |
| `[Guitar Solo]` | Specific instrument solo |
| `[Piano Solo]` | Specific instrument solo |
| `[Saxophone Solo]` | Specific instrument solo |
| `[Breakdown]` | Deconstructed section, stripped elements |
| `[Coda]` | Final concluding passage |
| `[Vamp]` | Repeated groove/pattern |
| `[Tag]` | Repeated ending phrase |
| `[Transition]` | Smooth connection between sections |
| `[Silence]` | Brief pause / dead air |
| `[Fade Out]` | Gradual volume decrease to end |
| `[Fade In]` | Gradual volume increase to start |

### Numbered Sections

You can number any section to differentiate:
- `[Verse 1]`, `[Verse 2]`, `[Verse 3]`
- `[Chorus 1]`, `[Chorus 2]`
- `[Bridge 1]`, `[Bridge 2]`

---

## 2. Vocal Delivery Tags

These control HOW the vocals are performed. Place them before the section or inline with lyrics.

### Vocal Style Tags

| Tag | Effect |
|-----|--------|
| `[Whispered]` | Soft, intimate whisper |
| `[Spoken Word]` | Spoken, not sung |
| `[Spoken]` | Spoken delivery |
| `[Rap]` | Rap/rhythmic speech delivery |
| `[Rap Verse]` | Rap section |
| `[Freestyle Rap]` | Looser rap flow |
| `[Sung]` | Return to melodic singing |
| `[Belted]` | Powerful, high-volume singing |
| `[Falsetto]` | High, airy vocal register |
| `[Harmonized]` | Multiple vocal harmonies |
| `[Harmony]` | Harmonic vocal layer |
| `[Ad-lib]` | Improvised vocal interjections |
| `[Screamed]` | Screaming/shouting vocal |
| `[Growl]` | Metal/death growl vocal |
| `[Yelled]` | Shouted vocal |
| `[Chanted]` | Rhythmic chanting |
| `[Hummed]` | Humming melody |
| `[Vocalized]` | Non-word vocalizations (oohs, aahs) |
| `[Scat]` | Jazz scat singing |
| `[Crooned]` | Smooth, intimate crooning |
| `[Melismatic]` | Multiple notes per syllable |
| `[Staccato]` | Short, punchy vocal delivery |
| `[Legato]` | Smooth, connected vocal delivery |
| `[Call and Response]` | Back-and-forth vocal pattern |
| `[Duet]` | Two voices singing together |
| `[Choir]` | Full choir vocals |
| `[Gospel Choir]` | Gospel-style choir |
| `[A Cappella]` | Vocals only, no instruments |

### Vocal Character Tags

| Tag | Effect |
|-----|--------|
| `[Male Vocal]` | Male voice |
| `[Female Vocal]` | Female voice |
| `[Male Vocals]` | Male voice (alternate) |
| `[Female Vocals]` | Female voice (alternate) |
| `[Deep Male Voice]` | Low-register male |
| `[High Female Voice]` | High-register female |
| `[Child Voice]` | Young voice |
| `[Raspy Voice]` | Gritty, textured voice |
| `[Breathy Voice]` | Airy, intimate voice |
| `[Nasal Voice]` | Nasal tone quality |
| `[Operatic Voice]` | Classical opera style |
| `[Soulful Voice]` | Emotional, R&B-style |
| `[Robotic Voice]` | Vocoder/auto-tune effect |
| `[Distorted Voice]` | Processed, distorted vocal |
| `[Female Narrator]` | Female spoken narration |
| `[Male Narrator]` | Male spoken narration |
| `[Diva Solo]` | Powerful female solo |
| `[Primal Scream]` | Raw, emotional scream |

### Vocal Effect Tags

| Tag | Effect |
|-----|--------|
| `[Reverb]` | Reverberant/echoey vocal |
| `[Echo]` | Echoing vocal |
| `[Auto-Tune]` | Pitch-corrected/T-Pain effect |
| `[Vocoder]` | Robot/synth voice effect |
| `[Megaphone]` | Megaphone/lo-fi filter |
| `[Telephone Voice]` | Phone-quality filter |
| `[Radio Voice]` | AM radio filter |
| `[Underwater]` | Muffled, submerged effect |

---

## 3. Instrument Tags

Specify instruments within structure tags or as standalone directions.

### Usage Patterns

```
[Intro: Acoustic Guitar]
[Verse 1: Piano and Strings]
[Guitar Solo]
[Instrumental: Synth Pad]
```

### Common Instrument Tags

**Guitars:** Acoustic Guitar, Electric Guitar, Classical Guitar, Bass Guitar, 12-String Guitar, Slide Guitar, Distorted Guitar, Clean Guitar, Fingerpicked Guitar, Power Chords

**Keys:** Piano, Grand Piano, Electric Piano, Rhodes Piano, Wurlitzer, Organ, Hammond Organ, Church Organ, Synthesizer, Synth Pad, Analog Synth, Harpsichord, Clavinet, Accordion, Melodica

**Drums/Percussion:** Drums, Drum Machine, 808s, 808 Bass, TR-808, TR-909, Hi-Hats, Snare, Kick Drum, Congas, Bongos, Timpani, Djembe, Tabla, Tambourine, Shaker, Cowbell, Hand Claps, Finger Snaps

**Strings:** Violin, Viola, Cello, Double Bass, String Ensemble, Strings, Orchestral Strings, Pizzicato Strings, Harp, Banjo, Mandolin, Ukulele, Sitar

**Brass:** Trumpet, Trombone, French Horn, Tuba, Brass Section, Saxophone, Alto Sax, Tenor Sax, Soprano Sax, Flugelhorn

**Woodwinds:** Flute, Clarinet, Oboe, Bassoon, Pan Flute, Recorder, Piccolo, Harmonica

**Electronic:** Synth Bass, Sub Bass, Pad, Arpeggiator, Sequencer, Drum Pad, Sampler, Turntable, Scratch, Glitch

---

## 4. Mood & Energy Tags

These can go in either the Style field or as metatags in lyrics.

### In the Style Field (no brackets)

```
melancholic, dreamy, euphoric, aggressive, tender, haunting, triumphant
```

### As Metatags in Lyrics

```
[Mood: Uplifting]
[Mood: Dark]
[Mood: Nostalgic]
[Energy: High]
[Energy: Low]
[Intensity: Building]
[Feeling: Bittersweet]
```

### Common Mood Descriptors

**High Energy:** Energetic, Uplifting, Euphoric, Anthemic, Powerful, Triumphant, Explosive, Aggressive, Fierce, Intense, Hype, Party

**Low Energy:** Calm, Peaceful, Serene, Dreamy, Ethereal, Ambient, Meditative, Lullaby, Gentle, Soft, Tender

**Dark:** Dark, Brooding, Haunting, Ominous, Sinister, Gothic, Melancholic, Gloomy, Somber, Eerie, Dystopian

**Emotional:** Romantic, Passionate, Heartfelt, Bittersweet, Nostalgic, Wistful, Hopeful, Yearning, Longing, Sentimental

**Fun:** Playful, Quirky, Whimsical, Funky, Groovy, Bouncy, Cheeky, Sassy, Celebratory

---

## 5. Tempo & Dynamics Tags

### Tempo Control

**In the Style Field (recommended for global tempo):**
```
120 BPM, fast tempo, slow ballad, mid-tempo groove
```

**As Metatags (for dynamic changes within the song):**
```
[Slow]
[Fast]
[Tempo: 120 BPM]
[Accelerando]     — gradually speed up
[Ritardando]      — gradually slow down
[Half-Time]       — halve the tempo feel
[Double-Time]     — double the tempo feel
```

**Important:** After any tempo change tag, include a stabilizing tag like `[Tempo: 120 BPM]` to prevent tempo drift.

### Standard Genre Tempos

| Genre | Typical BPM |
|-------|-------------|
| Ballad | 60-72 |
| Lo-fi | 70-80 |
| R&B | 75-85 |
| Hip-Hop | 85-95 |
| Reggaeton | 90-100 |
| Pop | 110-125 |
| House | 120-128 |
| Rock | 120-140 |
| Techno | 130-140 |
| Trap | 130-150 (half-time feel) |
| Drum & Bass | 170-180 |

### Dynamic Tags

```
[Crescendo]        — gradually louder
[Decrescendo]      — gradually softer
[Pianissimo]       — very soft
[Fortissimo]       — very loud
[Soft]             — quiet section
[Loud]             — loud section
[Dynamic Build]    — building intensity
[Strip Back]       — reduce instrumentation
[Full Band]        — all instruments in
```

---

## 6. Sound Effect & Ambience Tags

```
[Applause]
[Crowd Cheering]
[Birds Chirping]
[Rain]
[Thunder]
[Wind]
[Ocean Waves]
[City Ambience]
[Vinyl Crackle]
[Tape Hiss]
[Static]
[Heartbeat]
[Footsteps]
[Door Slam]
[Glass Breaking]
[Record Scratch]
```

---

## 7. Production & Mix Tags

These go in the **Style field** (no brackets):

```
lo-fi, hi-fi, polished mix, raw recording, studio quality, live recording,
bedroom pop, overdriven, clean production, analog warmth, digital clarity,
heavily compressed, spacious mix, tight mix, wall of sound, minimalist,
reverb-heavy, dry mix, tape saturated, vinyl warmth
```

---

## 8. Style Prompt Best Practices

### The 5-Part Formula

Structure your style prompt as:
1. **Genre + Subgenre** — "indie shoegaze" not just "rock"
2. **Mood + Energy** — "melancholic, dreamy"
3. **Vocal Style** — "breathy female vocals, ethereal"
4. **Key Instruments** — "layered guitars, analog synth, shimmering reverb"
5. **Tempo/BPM** — "slow, 85 BPM"

### Example Style Prompts

**Synthwave:**
```
Retrowave synthwave, nostalgic, neon-lit, male vocals, analog synthesizers,
arpeggiated bass, gated reverb drums, 118 BPM
```

**Acoustic Folk:**
```
Indie folk, intimate, warm, female vocals, fingerpicked acoustic guitar,
soft harmonies, upright bass, brush drums, 95 BPM
```

**Trap:**
```
Dark trap, aggressive, hard-hitting, male rap vocals, 808 bass, hi-hat rolls,
distorted synth, cinematic strings, 140 BPM half-time
```

**Jazz:**
```
Smooth jazz, late-night, sultry, female vocals, piano trio, walking bass,
brush drums, tenor saxophone, 92 BPM
```

**Epic Orchestral:**
```
Cinematic orchestral, epic, triumphant, full orchestra, brass fanfare,
timpani, choir, soaring strings, 100 BPM
```

---

## 9. Complete Song Template Examples

### Pop Song

```
[Intro: Synth Pad]

[Verse 1]
Walking through the city lights alone
Every shadow looks like someone I used to know
The neon signs are spelling out your name
And nothing in this town feels quite the same

[Pre-Chorus]
But I keep on moving, I keep on breathing

[Chorus]
We were golden, we were fire
Now we're just smoke and broken wire
Every heartbeat calls your name
But nothing's ever gonna be the same

[Verse 2]
Your jacket's hanging on my door
A ghost of all the things we swore
The coffee shop still saves your seat
And strangers walk on our old street

[Pre-Chorus]
But I keep on moving, I keep on breathing

[Chorus]
We were golden, we were fire
Now we're just smoke and broken wire
Every heartbeat calls your name
But nothing's ever gonna be the same

[Bridge]
[Soft]
Maybe in another life
We get the timing right
Maybe in another world
I'm still your girl

[Chorus]
[Belted]
We were golden, we were FIRE
Now we're just smoke and broken wire
Every heartbeat calls your name
But nothing's ever gonna be the same

[Outro: Fade Out]
Golden... we were golden...
```

### Hip-Hop Track

```
[Intro: 808s]
Yeah... let's go

[Verse 1]
[Rap]
Started from the basement, concrete floors and paper dreams
Mama working double shifts, nothing's what it seems
Notebook full of verses, pen was my escape
Every line I wrote was building toward this fate

[Hook]
Rise up from the ashes, yeah we made it through the flames
Write my story in the stars, they'll never forget my name

[Verse 2]
[Rap]
Now the city knows the kid who used to ride the bus
Traded in the hand-me-downs, yeah they calling us
Self-made, self-paid, every dollar earned
Every lesson that the streets gave, every bridge I burned

[Hook]
Rise up from the ashes, yeah we made it through the flames
Write my story in the stars, they'll never forget my name

[Bridge]
[Spoken Word]
They said I'd never make it out
But look at me now
Standing on top of everything they doubted

[Hook]
Rise up from the ashes, yeah we made it through the flames
Write my story in the stars, they'll never forget my name

[Outro]
[Ad-lib]
Yeah... we made it... we really made it...
[Fade Out]
```

### Country Ballad

```
[Intro: Acoustic Guitar, Soft]

[Verse 1]
[Crooned]
Old dirt road and a setting sun
Two kids with nowhere left to run
Your daddy's truck and a tailgate view
That summer I fell in love with you

[Chorus]
[Full Band]
Boots on the dash and your hand in mine
Dancing in the headlights, running out of time
If I could go back, I'd stay right there
With the fireflies tangled in your hair

[Verse 2]
The years rolled by like tumbleweeds
I traded dreams for grown-up needs
But every August when the sun burns low
I'm back on that road from long ago

[Chorus]
Boots on the dash and your hand in mine
Dancing in the headlights, running out of time
If I could go back, I'd stay right there
With the fireflies tangled in your hair

[Bridge]
[Whispered]
I still hear your laugh on the evening breeze
I still feel your head on my shoulder

[Chorus]
[Belted]
Boots on the dash and your hand in mine
Dancing in the headlights, running out of time
If I could go back, I'd stay right there
With the fireflies tangled in your hair

[Outro: Pedal Steel Guitar, Fade Out]
```

---

## 10. Common Mistakes to Avoid

1. **No structure tags** — Always use `[Verse]`, `[Chorus]`, etc. Without them, Suno treats everything as one continuous block.

2. **Putting style info in lyrics** — Keep genre/mood/instrument descriptions in the Style field. The Lyrics field is for lyrics + metatags only.

3. **Using brackets in the Style field** — The Style field expects plain text. Brackets in the Style field are ignored or cause hallucinations.

4. **Being too vague** — "Pop song" is too generic. "Upbeat synth-pop, female vocals, 80s-inspired, 120 BPM" is specific.

5. **Overloading metatags** — Too many tags per section confuse the model. 1-2 tags per section is optimal.

6. **Ignoring tempo** — Always specify BPM or at least a tempo descriptor. It dramatically affects the feel.

7. **Too many words per section** — Suno works best with 4-8 lines per verse, 4-6 lines per chorus. Long sections get compressed.

8. **No contrast between sections** — Verses and choruses should feel different. Use dynamic tags to create contrast.

9. **Asterisks and markdown** — Do NOT use asterisks, bold, italic, or other markdown in lyrics. Only square brackets.

10. **Forgetting [End]** — Songs may trail off without a clear ending tag. Use `[Outro]` or `[End]` or `[Fade Out]`.

---

## 11. Advanced Techniques

### Layering Tags

Combine structure + vocal + dynamic tags:
```
[Chorus]
[Belted]
[Full Band]
```

### Inline Vocal Switches

Change delivery mid-section:
```
[Verse 1]
Walking through the rain [Whispered] alone again
[Sung] But tomorrow I'll be fine
```

### Contrast Building

Create dynamic contrast:
```
[Bridge]
[Soft]
[Acoustic Guitar Only]
Maybe we could start again...

[Final Chorus]
[Fortissimo]
[Full Band]
WE COULD START AGAIN!
```

### Using ALL CAPS

Writing lyrics in ALL CAPS tells Suno to emphasize those words with more intensity/volume.

### Parenthetical Background Vocals

Use parentheses for background/echo vocals:
```
I'm coming home (coming home)
Nothing's gonna stop me now (stop me now)
```

### Repetition for Emphasis

Repeat words for rhythmic effect:
```
Run, run, run from the fire
Higher, higher, higher
```

---

## Quick Reference Card

| Category | Where to Put It | Format |
|----------|----------------|--------|
| Genre/Style | Style field | Plain text, commas |
| Tempo/BPM | Style field | Plain text |
| Song structure | Lyrics field | `[Verse]`, `[Chorus]`, etc. |
| Vocal delivery | Lyrics field | `[Whispered]`, `[Belted]`, etc. |
| Instruments | Either | Style: plain text / Lyrics: `[Guitar Solo]` |
| Dynamics | Lyrics field | `[Soft]`, `[Loud]`, etc. |
| Mood | Style field | Plain text descriptors |
| Sound effects | Lyrics field | `[Rain]`, `[Applause]`, etc. |
