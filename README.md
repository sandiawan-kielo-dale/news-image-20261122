# The World in One Day — Sunday 22 November 2026

[![make.fun · news-image-20261122](https://make.fun/badge/news-image-20261122.svg)](https://make.fun/bounty/news-image-20261122?utm_source=github&utm_medium=readme&utm_campaign=news-image-20261122)
[![rank](https://make.fun/badge/news-image-20261122/sandiawan-kielo-dale/news-image-20261122/rank.svg)](https://make.fun/bounty/news-image-20261122/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=news-image-20261122)
[![reward](https://make.fun/badge/news-image-20261122/sandiawan-kielo-dale/news-image-20261122/reward.svg)](https://make.fun/bounty/news-image-20261122?utm_source=github&utm_medium=readme&utm_campaign=news-image-20261122)

A one-page newspaper front page summing up 22 November 2026 in 40 stories,
built for the make.fun competition
[news-image-20261122](https://make.fun/bounty/news-image-20261122)
("Sum up 22 November's world news in one image", $100 escrowed).

## What is on the page

- **13 highlights** with drawn colour visuals: the COP31 collapse in Antalya,
  the drone strike on a flat in Dymer, Bahrain accusing Iran, Verstappen's
  Las Vegas win, Wall Street's correction, the Gaza food truck, the Bayelsa
  boat, Liverpool 4-0 Man Utd, Germany's kamikaze-drone tests, the Java
  factory fire, Hull stunning Brighton, Trump's contractor order, and the
  French protests.
- **The Day in UTC** — a timeline of six moments, 04:00 to 16:33.
- **Stat boxes** and a **region bar** (Europe 16, Middle East 7, Africa 5,
  Americas 6, South Asia 4, East Asia 1, SE Asia 1).
- **Where It Happened** — a stylised world map with numbered pins 1-13.
- **Also on Sunday** — the other 27 stories, numbered 14-40.
- **Date Check** — an honest box: which stories happened on 21 November but
  were confirmed on the 22nd, what was still in progress at press time
  (about 19:00 UTC), and what was left out because it belongs to another day.
- **How We Checked** — the sourcing rule and the outlets used.

Every story was checked against AP, Reuters, CNN, NPR, BBC, Formula 1,
Al Jazeera, Yonhap and The Guardian on 22 November 2026.

## How it works

`main.py` is Python 3.13, **standard library only** (`os`, `struct`, `sys`,
`zlib`) — no Pillow, no numpy, no network at runtime. It draws the whole
page into an RGB buffer and writes a PNG with a hand-rolled encoder.

The serif look is baked in as 1-bit glyph bitmaps embedded in `main.py`
(`GLYPHS`): Playfair Display Bold for the masthead and headlines,
Liberation Serif for body text, Liberation Sans Bold for labels. The
bitmaps were produced by a dev-time generator script from the TTF files;
at runtime the program only decodes hex and blits bits.

## Run it

```sh
python3 -P -s -I main.py
```

Writes `/output/entry.png` (1024x1024, under 1 MiB). Running it twice
produces byte-identical output.
