# Font sources and conversions

These notices apply to the application’s embedded BCFNT subsets. Font licenses and original upstream locations are listed below.
0.6.0 expands the subset to extended Latin, combining marks and Cyrillic.
Where the selected family lacks a glyph, the reader uses embedded Noto Sans.
This is not a claim that all eight font choices natively contain every script.

## Droid Serif

Steve Matteson / Ascender; digitized data copyright 2007 Google Corporation.
Apache License 2.0. Both the upstream license and the conversion/attribution
notice are bundled and embedded in the executable.

Unmodified input from Android Open Source Project:
https://github.com/aosp-mirror/platform_frameworks_base/blob/df331873c8576e0ae34ae1ee3cc258beed373535/data/fonts/DroidSerif-Regular.ttf

SHA256: ae32140265dbe0dfde24b9abd222be9210a531888f014ff9b2326aba2d6fd777

The upstream data/fonts/NOTICE is preserved as droidserif-LICENSE.txt.
The generated droidserif.bcfnt is a subset/format conversion; see
droidserif-NOTICE.txt.

## Literata

Copyright 2017 The Literata Project Authors; SIL Open Font License 1.1.
The application uses upstream static Regular version 3.103, with OFL.
The BCFNT file is a 20-pixel subset/format conversion of this input.

https://github.com/googlefonts/literata/blob/0c2761b727a1b3a7cffd313c37f0f5163dfc7a63/fonts/ttf/Literata-Regular.ttf

SHA256: 0390890de9bb9d5862a6ba4125b82c61792ccc3d66b63e73eee75c1a16fcd208

## Existing fonts

Noto Sans, Noto Serif, Inter, EB Garamond and the renamed derivative
Ink3DS Baskerville have their copyright notices in the corresponding
OFL files. The system-font option uses the console's existing font and
does not redistribute a system font file.

The historic embedded Droid notice refers to the development project’s TTF files. Original upstream font locations are provided above; the public distribution contains notices rather than the private development project.
