# Anki Hanzi Colorizer Flashcard

An Anki flashcard template for learning Chinese (Mandarin) that color-codes hanzi characters and pinyin by tone, making it easier to memorize tones visually.

## How it works

Each hanzi character and its corresponding pinyin vowel are highlighted in the same color based on tone:

| Tone   | Color     | Example vowel |
|--------|-----------|---------------|
| 1st    | Red       | ā, ē, ī, ō, ū |
| 2nd    | Green     | á, é, í, ó, ú |
| 3rd    | Blue      | ǎ, ě, ǐ, ǒ, ǔ |
| 4th    | Violet    | à, è, ì, ò, ù |
| Neutral| Light grey| (no diacritic) |

The script parses the pinyin field to detect toned vowels, maps each syllable to its corresponding hanzi character, and injects colored `<span>` elements for both. The target word is also highlighted inside the example sentence.

## Card fields

| Field     | Description                                      |
|-----------|--------------------------------------------------|
| `hanzi`   | The Chinese word (e.g. `目标`)                   |
| `pinyin`  | Pinyin with tone diacritics (e.g. `mùbiāo`)     |
| `meaning` | English translation (e.g. `goal`)               |
| `example` | An example sentence containing the hanzi word   |

## Files

```
anki/
  card.html   — Anki card template (front + back) with {{ field }} placeholders
  script.js   — Colorization logic (IIFE, safe for Anki's web context)
  style.css   — Card styling
index.html    — Local test harness with hardcoded sample data
```

## Usage

### In Anki

1. Open the Anki card template editor.
2. Paste the contents of [anki/card.html](anki/card.html) into the card template (front + back combined, or split as needed).
3. Add the contents of [anki/style.css](anki/style.css) to the **Styling** section.
4. Add the contents of [anki/script.js](anki/script.js) at the bottom of the card template inside a `<script>` tag.

### Local preview

Open [index.html](index.html) in a browser. It loads the real CSS and JS against hardcoded sample data (`目标` / `mùbiāo` / `goal`) so you can iterate on the template without needing Anki.
