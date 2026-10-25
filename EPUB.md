# Book formats and limits

Ink3DS reads DRM-free reflowable EPUB 2/3, TXT and HTML/HTM. EPUB chapters follow
the package reading order. ZIP stored/deflate content is read directly from SD;
no extracted book/image files are written. Scripts and style content are ignored.

In 0.6.x previews, PNG/JPEG pictures appear at their text positions as separate
proportional blocks. Declared EPUB 2/3 covers appear on the bookshelf; title cards
are used when unavailable. Raster images inside SVG wrappers can be resolved.
Arbitrary SVG vector drawing, CSS floats and publisher-fixed layout are unsupported.

Images are limited to 4096 pixels per dimension AND 4,194,304 total pixels,
4 MiB per archive entry and 64 occurrences per book. Decoding has a bounded
32 MiB allocation budget; unavailable/oversized images show placeholders.
Book text is limited to 4 MiB and library scans to 256 directory entries.
Subfolders are not scanned recursively.

Settings language selects the typesetting profile in 0.6.5; EPUB metadata does
not override it. Text is not translated. See [layout rules](TEXT-LAYOUT.md).
Older text offsets and image/bookmark anchors remain compatible. Moving or
renaming a book changes its path-based progress identity.

PDF, DRM, full CSS/fixed layout, CJK and RTL shaping remain unsupported.
