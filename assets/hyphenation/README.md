# Hyphenation component data and notices

This directory contains separately licensed third-party hyphenation data.
The application source is not distributed here.

sources.json records the original input hashes, exact upstream commit
locations and language minima. The .tex/.pat input files are unmodified.
Czech/Slovak patterns are the MIT-licensed Sojka 2021 set. Spanish, French,
German and the chosen Polish/Italian options use MIT; Portuguese uses
BSD-3-Clause; English retains Kuiken’s permissive notice. Russian data
uses LPPL 1.3c (under its 1.2-or-later permission). Full notices follow
in NOTICES.txt and LPPL-1.3c.txt.

ink3ds-pattern-data.txt is the Ink3DS-specific derived representation,
maintained by Faefolk333. It contains only data tables, including the
Russian-derived data, alongside the unchanged original inputs. Changes
are described in that file. Upstream authors do not endorse Ink3DS.
The embedded historic notice refers to include/hyphen_data.h; that data
is supplied here as ink3ds-pattern-data.txt.

Complete upstream projects: https://github.com/hyphenation/tex-hyphen,
https://github.com/ondrejsojka/cshyphen and https://ctan.org/pkg/ruhyphen.
