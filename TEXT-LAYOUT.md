# Text layout in 0.6.5

The **Settings language controls both the interface and book typesetting**.
Select the language you are reading. This is a global choice: EPUB metadata
does not override it and books are not translated. Language changes reflow the
open book, retaining text-byte positions, bookmarks and image-slice anchors.
The preferences/progress formats and normalized book bytes remain unchanged.

| Language | Patterns | Minimum letters left/right | Additional tailoring |
|---|---|---|---|
| English | US English, Kuiken | 2 / 3 | English quotation marks |
| Čeština | Sojka Czech/Slovak 2021 | 2 / 2 | Bind a/i/k/o/s/u/v/z; repeat compound hyphens; low quotes |
| Español | CervanTeX | 2 / 2 | Shared punctuation/no-break safeguards |
| Français | French TeX | 2 / 2 | Keep punctuation : ; ! ? and closing guillemets with preceding text |
| Polski | Polish TeX | 2 / 2 | Bind a/i/o/u/w/z; repeat compound hyphens |
| Русский | Lebedev | 2 / 2 | Bind а/в/и/к/о/с/у; low/guillemet quotes |
| Deutsch | Reformed German, 2024 | 2 / 2 | Low quotes and »…« guillemets |
| Italiano | Beccari | 2 / 2 | Shared punctuation/no-break safeguards |
| Português | Portuguese TeX, 2024 | 2 / 3 | Repeat compound hyphens |

Shared rules avoid ordinary space breaks after opening brackets/quotes and
before closing punctuation. French punctuation spacing is preserved from the
book, not inserted automatically. Letters retain the selected font.

## Patterns, conditional breaks and exact positions

- Liang/TeX patterns and upstream exception lists are compiled read-only.
  No dictionary download, SD access or runtime dictionary allocation is needed.
  Inputs, licenses, hashes and pinned commits: assets/hyphenation/sources.json.
  The generated trie occupies about 1.3 MiB.
- Soft hyphen U+00AD is invisible unless used at a break. Author-provided hints
  take precedence over automatic patterns within that word.
- Inserted/repeated hyphens are display-only; they never become book bytes or
  change saved offset identities.
- NBSP U+00A0, narrow NBSP U+202F and word joiner U+2060 protect corresponding
  break positions. ZWSP U+200B offers a break without a hyphen.
- Supported combining groups remain attached to their base. Supported decomposed
  accents compose for pattern matching without rewriting the source.
- Real compound hyphens may wrap after the hyphen. Czech, Polish and Portuguese
  repeat it at the continuation start; an automatic hyphen never repeats.

## Limits

This is **not full UAX #14/#29 conformance or a guarantee of perfect linguistic
hyphenation**. Patterns have exceptions and regional differences: English uses
US patterns, German uses reformed spelling; Portuguese UI terminology is Brazilian.

Unsupported/mixed-script words and words exceeding 96 codepoints skip automatic
patterns. Unbreakable groups wider than the 356-pixel reading area still use an
emergency character/combining-group break without inventing a hyphen; this can
override nonbreaking constraints. Font coverage still limits unknown glyphs.
Full grapheme/emoji-ZWJ segmentation, CJK, RTL, automatic quotation conversion,
contextual spacing, publisher CSS and PDF are outside this release.

For compatibility with existing offsets, the markup parser still normalizes
the named HTML entity `&nbsp;` to an ordinary space. Actual Unicode NBSP and
numeric `&#160;` retain their no-break behavior. Parser normalization is unchanged
in this release; the reader applies its safeguards to the normalized text.

