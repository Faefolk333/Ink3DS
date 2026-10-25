# 0.6.5 (preview)

- Settings language now selects the translated UI and book typesetting profile for EN/CS/ES/FR/PL/RU/DE/IT/PT. Switching reflows the book while retaining exact text-byte positions, bookmarks and inline-image slices.
- Add licensed Liang/TeX patterns, upstream exceptions, per-language minima, conditional soft hyphens, nonbreaking spaces/joiners, punctuation/quotation groups and Czech/Polish/Russian one-letter word bindings. Repeat real compound hyphens in Czech/Polish/Portuguese continuation lines.
- Keep generated hyphens virtual: book text and existing progress/preferences formats are unchanged. Patterns are compiled read-only, requiring no SD dictionary I/O or dictionary allocation on language changes.
- Add independent pattern-reference comparisons for all nine profiles and every exception, actual draw-call/layout/anchor regressions, and native ARM stack budgeting for the matcher. Update all nine real-book host previews. Preserve existing decoder, HOME/backlight, font and book-opening fixes.
- Document regional choices and emergency fallback in TEXT-LAYOUT.md. Full Unicode typography, automatic language detection, CJK/RTL and PDF remain deferred.

# 0.6.4 (preview)

- Accept tall or wide PNG/JPEG sources up to 4096 pixels per dimension while retaining the existing 4,194,304-pixel ceiling, 32 MiB decoder budget, 4 MiB ZIP-entry limit and bounded output textures. The original Verne 1600×2400 cover now decodes without modifying the EPUB.
- Replace the misleading 2048-pixel placeholder text with a format/size/memory explanation in all nine languages.
- Add large RGB/RGBA/JPEG, dimension/pixel rejection, repeated decoder cleanup and texture-cache regressions. Clarify current wrapping limits: common space-based wrapping, no dictionary hyphenation or complete language-specific typesetting. Reader layout itself is unchanged.

# 0.6.3 (preview)

- Add a nine-language gallery pairing actual public-domain EPUB text with the corresponding translated UI, a combined overview, individual previews, source credits and reproducible capture tools. This is a documentation/media update; the 0.6.3 CIA/3DSX are unchanged.
- Add German (Deutsch), Italian (Italiano) and Portuguese (Português, Brazilian terminology) UI translations, including dialogs, progress messages and parser errors.
- Compose decomposed Portuguese cedillas/tildes (and Spanish tildes) into their normal Latin-1 letters while mapping inline-image offsets through normalization.
- Keep all existing language IDs and the saved preference format unchanged; append the three new options to the language control. English remains the default.
- Validate all 111 keys in nine catalogs, printf placeholders, UI labels, atlas coverage, per-language settings round trips and DE/IT/PT text decoding (UTF-8, decomposed accents, UTF-16, declared Windows-1252 EPUB).
- Retain EPUB pictures/covers, saved reading positions and the book-opening/punctuation fixes. No dictionary hyphenation or complex-script support is added.

# 0.6.2 (preview)

- Keep explicitly mapped question marks in the selected font. Their glyph index also serves as the atlas replacement index; this no longer incorrectly triggers a larger fallback face.
- Draw and measure actual fallback glyphs in the selected face's pixel scale and on a shared baseline, including combining marks and Bionic Reading passes.
- Add real-atlas punctuation and native draw-call regressions, covering direct/table/scan maps, unmapped entries and mixed-font scale/baseline consistency.
- Withdraw the broken 0.6.0 release and its tag/QR. Keep functioning releases and the book-opening fix from 0.6.1.

# 0.6.1 (preview)

- Fix an immediate book-opening crash affecting every format: the new document metadata exceeded libctru's 32 KiB main stack. Allocate the next document on the heap with checked allocation and clean failure paths, preserving the current book until loading and layout succeed.
- Add native ARM stack-usage regression checks to release packaging, including the book-opening call chain. Host-only tests could not catch the console's stack limit.
- Keep inline EPUB images, covers, six UI languages, existing Title ID, and stable 0.5.1 unchanged.

# 0.6.0 (withdrawn: book-opening crash)

- PNG/JPEG EPUB images placed directly in reading flow; proportional image blocks.
- Real bookshelf covers from EPUB 3 cover-image, EPUB 2 cover metadata or cover guide.
- Raster images referenced by SVG wrappers; safe placeholders for unavailable images.
- Six UI languages: EN/CS/ES/FR/PL/RU, editable checked catalogs and extended fonts.
- Glyph fallback, combining-mark-safe breaks, explicit Windows-1251 HTML/XML decoding.
- Image-aware reading/bookmark anchors; old text offsets and data paths preserved.
- Bounded raster decoding and staged GPU uploads; no new SD extraction/cache writes.
- Separate preview release. 0.5.1 assets and stable release are retained.
- PDF and CJK/RTL remain deferred.

# 0.5.1

- Added embedded Droid Serif and Literata Regular, with Czech glyph coverage.
- Eight font choices; font switching keeps the existing text-offset anchor.
- Included font sources, licenses and conversion notices in the project and executable.
- Added regression tests for all font choices, reflow and embedded license data.
- Kept the same Title ID, data paths and HOME/backlight handling.

# 0.5.0

- Initial Ink3DS publication with clean repository history.
- Supplied book icon with app name below; author in startup and metadata.
- Removed HOME TRACE overlay and trace instrumentation.
- Retained hardware-confirmed HOME handover fix, including short-lived LCD sessions and lower-screen wake before handover.
- Stable installation Title ID and compatible preferences/progress formats.
- New app-owned data directory: /Ink3DS/.
