# 🏀 WNBA Opening & Closing Odds — 7 Books + the Opening Line (2018–2026)

**Free sample: 20 games, from the first game of the file, 18 May 2018, to its last day, 29 July 2026** — 8 Finals
games, 4 Commissioner's Cup finals and 8 regular-season games.

Most WNBA odds files give you one closing number per game. The full dataset puts **the opening line and the closing
prices of seven sportsbooks side by side, game by game**: Betcris, Heritage, BetOnline, Bovada, BetAnything,
William Hill and Everygame. Moneyline, spread and total, in American and decimal odds, plus **the public betting
split** on each market.

→ **[Get the full dataset](https://sportsdataolivier.gumroad.com/l/rnlhra?utm_source=github&utm_medium=readme&utm_campaign=wnba_oc&utm_content=hero)** — 2,034 games, 18 May 2018 to 29 July 2026 · also on [Whop](https://whop.com/oliviersportsdata/wnba-opening-closing-odds-7-books-opening-line-2018-2026/?utm_source=github&utm_medium=readme&utm_campaign=wnba_oc&utm_content=whop_hero)

This repository holds the sample (`sample/`) and the *Verify before you buy* notebook (`WNBA_Verify_Before_You_Buy.ipynb`, results shown). The sample is cut from the full file: the same 137 columns, the rows copied byte for byte.

---

## One game, every market

2025 Finals, Game 4 — Aces at Mercury, final 97–86, the Aces' title. Each book's closing prices, next to the
opening line:

| Source | Aces ML | Mercury ML | Mercury spread | Total |
|---|---:|---:|---:|---:|
| Opening line | -130 | +110 | +2 | 164.5 |
| Betcris | -128 | +109 | +1.5 | 162 |
| Heritage | -130 | +110 | +2 | 164 |
| BetOnline | -125 | +105 | +2 | 164 |
| Bovada | -125 | +105 | +1.5 | 163.5 |
| BetAnything | -125 | +105 | +2 | 164 |
| William Hill | -125 | +100 | +1.5 | 164.5 |
| Everygame | -125 | +105 | +2 | 164 |

Public betting split: 55% of the moneyline bets on the Aces, 78% of the total bets on the over.

---

## What's in this sample

| | |
|---|---|
| Games | 20 — two or three per season, 2018 to 2026 |
| Prices | 822, each in American and decimal odds |
| Sources | the opening line + 7 sportsbooks |
| Columns | 137 |
| File | `WNBA_Opening_Closing_Odds_2018-2026_SAMPLE.csv` (semicolon-separated, UTF-8 with BOM), plus the README of the full product |

| Date | Game | Why it is here | Final, away–home | Books with a closing ML |
|---|---|---|---|---:|
| 18 May 2018 | Wings @ Mercury | first game of the file | 78–86 | 5 |
| 12 Sep 2018 | Storm @ Mystics | 2018 Finals, Game 3: Seattle's title | 98–82 | 6 |
| 20 Jun 2019 | Mystics @ Aces | regular season | 95–72 | 6 |
| 10 Oct 2019 | Sun @ Mystics | 2019 Finals, Game 5: Washington's title | 78–89 | 6 |
| 26 Jul 2020 | Sky @ Aces | 2020 bubble, opening weekend: three books, no opening moneyline or spread | 88–86 | 3 |
| 6 Oct 2020 | Aces @ Storm | 2020 Finals, Game 3: Seattle's title | 59–92 | 6 |
| 12 Aug 2021 | Sun @ Storm | first Commissioner's Cup final; first game of the Betcris gap | 57–79 | 5 |
| 17 Oct 2021 | Mercury @ Sky | 2021 Finals, Game 4: Chicago's title | 74–80 | 4 |
| 6 May 2022 | Sparks @ Sky | opening night of 2022 | 98–91 OT | 6 |
| 18 Sep 2022 | Aces @ Sun | 2022 Finals, Game 4: Las Vegas's title | 78–71 | 7 |
| 15 Aug 2023 | Liberty @ Aces | 2023 Commissioner's Cup final | 82–63 | 5 |
| 18 Oct 2023 | Aces @ Liberty | 2023 Finals, Game 4: Las Vegas's title | 70–69 | 6 |
| 25 Jun 2024 | Lynx @ Liberty | 2024 Commissioner's Cup final | 94–89 | 4 |
| 20 Oct 2024 | Lynx @ Liberty | 2024 Finals, Game 5: New York's title, in overtime | 62–67 OT | 7 |
| 17 May 2025 | Sky @ Fever | one of the 26 games restored in this edition | 58–93 | 7 |
| 1 Jul 2025 | Fever @ Lynx | 2025 Commissioner's Cup final | 74–59 | 7 |
| 10 Oct 2025 | Aces @ Mercury | 2025 Finals, Game 4: Las Vegas's title | 97–86 | 7 |
| 8 May 2026 | Mystics @ Tempo | Toronto Tempo, 2026 expansion: first game in the file | 68–65 | 7 |
| 20 Jun 2026 | Sky @ Wings | 17–22 June 2026: moneylines read with that week's order of the books | 92–93 | 7 |
| 29 Jul 2026 | Dream @ Wings | last day of the file; decimal prices at the source | 82–81 | 7 |

*Books*: out of 7, the books with a closing moneyline on that game.

---

## Columns

| Block | Columns | Content |
|---|---:|---|
| Game | 17 | `Season`, `Date` (US Eastern), `Day`, `Time` (tip-off, US Eastern, 24-hour), teams, final score, `Winner`, `Total_Points`, `Margin` (home minus away), the public betting split on the three markets |
| Each of the 8 sources | 15 | moneyline of both teams; spread line and price of both teams; total line, over and under — every price in American and decimal odds |

`Betcris_ML_Home_US` · `Betcris_ML_Home_Dec` · `Opener_Spread_Home_Line` · `Bovada_Total_Line` · `ML_Home_Bet%` —
William Hill's columns start with `WilliamHill_`.

**`Opener` is the opening line**, the first line published for the game; **the seven books carry their closing
prices**. Prices are American odds as integers (`-150`, and `130` for +130) with the decimal price beside each one.
**The spread line is each team's handicap**: `-6.5` gives 6.5 points, `0` is a pick'em. From 23 June 2026 the source
shows decimal prices: on those games the American price is converted from the decimal one. An empty cell means no
price, never zero.

```python
import pandas as pd

df = pd.read_csv("WNBA_Opening_Closing_Odds_2018-2026_SAMPLE.csv", sep=";", encoding="utf-8-sig")

def prob(us):                          # American odds -> implied probability
    return -us / (-us + 100) if us < 0 else 100 / (us + 100)

# Betcris closing probability of the home team, margin removed
home, away = df["Betcris_ML_Home_US"].map(prob), df["Betcris_ML_Away_US"].map(prob)
df["betcris_home"] = home / (home + away)

# how far Betcris closed from the opening line, home spread
df["spread_move"] = df["Betcris_Spread_Home_Line"] - df["Opener_Spread_Home_Line"]
```

---

## Said plainly

- **The 2026 season stops on 29 July 2026.** The rest of that season is not in the file.
- **One opening line, closing prices for the seven books**: no opening price per book, nothing in between. No
  halves, quarters, team totals, player props or live odds. No preseason, no All-Star games.
- **Betcris has no price from 12 August 2021 to 21 August 2022. BetAnything starts in September 2021.**
- **Games left out rather than guessed**: the 5 games of 1 July 2018 and 9 games of the 2020 bubble, missing at the
  source; 33 Las Vegas Aces games of 2025, whose Aces row is overwritten on the source pages; 1 game of May 2026 with a
  wrong score at the source.
- **212 markets whose prices cannot exist or contradict the market were left out, never corrected.** The rules and
  the counts are in the README.

---

## Verify before you buy

The figures of the listing and of its README — games per season and team by team, prices, coverage of every book
season by season, the betting splits, the games on the listing's images — recomputed from the full file and printed
PASS or FAIL: [on Kaggle](https://www.kaggle.com/code/oliviersportsdata/wnba-multi-market-opening-closing-odds) · [on GitHub](https://github.com/ovignez-hash/wnba-multi-market-opening-closing-odds/blob/main/WNBA_Verify_Before_You_Buy.ipynb) (results shown).

---

## The full dataset

| | Sample | Full |
|---|---|---|
| Games | 20 | 2,034 |
| Seasons | 2018 to 2026 | 2018 to 2026, through 29 July 2026 |
| Prices | 822 | 89,964 |
| Columns | 137 | 137 |
| Files | 1 CSV + README | 1 CSV + README |

→ **[Get the full dataset on Gumroad](https://sportsdataolivier.gumroad.com/l/rnlhra?utm_source=github&utm_medium=readme&utm_campaign=wnba_oc&utm_content=footer)** · also on [Whop](https://whop.com/oliviersportsdata/wnba-opening-closing-odds-7-books-opening-line-2018-2026/?utm_source=github&utm_medium=readme&utm_campaign=wnba_oc&utm_content=whop_footer)

---

## License

- **Sample**: free to explore and evaluate.
- **Full dataset**: Single commercial user. Use the data as you wish, including the models, predictions and products
  you sell. Redistribution and resale of the files, or of the raw data in another format, are not permitted.

A question before buying: contact@oliviersportsdata.com

---

*Olivier Sports Data — From Chicken Area 🐔*
