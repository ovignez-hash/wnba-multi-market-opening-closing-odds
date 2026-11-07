# WNBA Opening & Closing Odds — free 20-game sample

`WNBA_Opening_Closing_Odds_2018-2026_SAMPLE.csv` holds 20 games of the full product: the same 137 columns and the same
format, the rows copied byte for byte from the full file. Read it with
`pd.read_csv("WNBA_Opening_Closing_Odds_2018-2026_SAMPLE.csv", sep=";", encoding="utf-8-sig")`.

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

Below, unchanged, the README shipped with the full product (2,034 games).

---

# WNBA Multi-Market — Opening & Closing Odds (2018–2026)

One row per game. 2,034 WNBA games from 18 May 2018 to 29 July 2026: regular season, playoffs and the
Commissioner's Cup finals. No preseason, no All-Star games. The 2026 season stops on 29 July 2026.

For each game, when the source has them: the opening line, the closing prices of seven sportsbooks on the moneyline,
the spread and the total, and the public betting split on each of the three markets.

| | |
|---|---|
| Games | 2,034 |
| Seasons | 2018 to 2026 (2026 through 29 July) |
| Sportsbooks, closing prices | Betcris · Heritage · BetOnline · Bovada · BetAnything · William Hill · Everygame |
| Opening line | `Opener`, the first line published for the game |
| Markets | Moneyline · Spread · Total |
| Public betting split | % of bets on each side, on all three markets |
| Prices | 89,964, each in American and decimal odds |
| Columns | 137 |
| File | `WNBA_Opening_Closing_Odds_2018-2026.csv` — UTF-8 with BOM, semicolon-separated, dot as decimal mark |

```python
import pandas as pd
df = pd.read_csv("WNBA_Opening_Closing_Odds_2018-2026.csv", sep=";", encoding="utf-8-sig")
```

## Games

| Season | Games | |
|---|---:|---|
| 2018 | 215 | the 5 games of 1 July 2018 are missing at the source; Las Vegas at Washington, 3 August 2018, was never played (forfeit) |
| 2019 | 220 | every game of the season |
| 2020 | 138 | the bubble season; 9 games are missing at the source |
| 2021 | 210 | every game of the season, first Commissioner's Cup final |
| 2022 | 240 | every game of the season |
| 2023 | 261 | every game of the season |
| 2024 | 263 | every game of the season |
| 2025 | 278 | first 44-game season; 33 Las Vegas Aces games are left out (see *Known limitations*) |
| 2026 | 209 | through 29 July 2026; Toronto at Phoenix, 19 May 2026, is left out (see *Known limitations*) |

"Every game of the season" means the regular season, the Commissioner's Cup final and the playoffs, checked team by
team against the number of games each franchise played. Fifteen franchises: the Golden State Valkyries from 2025,
the Portland Fire and the Toronto Tempo from 2026.

## Columns

**Game — 17 columns**

| Column | Content |
|---|---|
| `Season` | the year, 2018 to 2026 |
| `Date` | `YYYY-MM-DD`, US Eastern date |
| `Day` | `Mon` to `Sun` |
| `Time` | scheduled tip-off, US Eastern time, 24-hour clock (`19:30`) |
| `Away_Team`, `Home_Team` | full franchise names |
| `Away_Score`, `Home_Score` | final score, overtime included |
| `Winner` | `Home` or `Away` |
| `Total_Points` | home plus away points |
| `Margin` | `Home_Score` minus `Away_Score`: positive when the home team wins |
| `ML_Away_Bet%`, `ML_Home_Bet%` | public betting split on the moneyline: % of bets on each team |
| `Spread_Away_Bet%`, `Spread_Home_Bet%` | the same on the spread |
| `Total_Over_Bet%`, `Total_Under_Bet%` | the same on the total |

**Odds — 15 columns per source**, for the 8 sources `Opener`, `Betcris`, `Heritage`, `BetOnline`, `Bovada`,
`BetAnything`, `WilliamHill`, `Everygame`. The columns are grouped by market: the moneyline of the 8 sources, then
their spreads, then their totals.

```
{Src}_ML_Away_US        {Src}_ML_Away_Dec        {Src}_ML_Home_US        {Src}_ML_Home_Dec
{Src}_Spread_Away_Line  {Src}_Spread_Away_US     {Src}_Spread_Away_Dec
{Src}_Spread_Home_Line  {Src}_Spread_Home_US     {Src}_Spread_Home_Dec
{Src}_Total_Line        {Src}_Total_Over_US      {Src}_Total_Over_Dec    {Src}_Total_Under_US    {Src}_Total_Under_Dec
```

### How to read it

**`Opener` is the opening line**, the first line published for the game, with its prices. **The seven books carry
their closing prices**, the last ones before tip-off. There is no opening price per book and nothing in between.

**Prices are American odds, as integers** — `-150`, and `130` for +130; even money is `100` — with the decimal price
beside each one, to two decimals.

**From 23 June 2026 the source shows decimal prices.** On those 84 games the decimal column is the price
as published and the American column is converted from it, rounded to the whole number: on a heavy favorite it can be
a few points away from the American price the book quoted (`1.33` gives `-303`). Before 23 June 2026 it is the other way
round: the American price is as published, the decimal one converted.

**The spread line is each team's handicap.** `Spread_Home_Line` at `-6.5` means the home team gives 6.5 points; the
away line is the opposite. A pick'em is written `0`.

**The total line is in points**, the same for the over and the under.

**The public betting split** is the share of bets on each side, as published with the odds. The two sides of a market
add up to 100.

**An empty cell means no price**, never zero and never estimated. A market is either complete for a source — both
sides, with the line — or empty.

## How the prices were checked

Every price was read again from the source pages for this edition. Prices that cannot exist, or that contradict the
rest of the market, were left out rather than corrected: 212 markets (one source's moneyline, spread or
total on one game) out of 45,194.

| Left out | Markets |
|---|---:|
| Closing price far from the other books on the same game: moneyline more than 15 points of probability from their median, spread 4 points or more, total 6 points or more | 93 |
| Moneyline and spread name different favorites: the moneyline gives one team at least 53% (margin removed) while the same source's spread makes the other team favorite by a point or more. Both markets left out | 70 |
| Total line outside 120–200 points | 21 |
| Spread lines of the two teams not opposite | 10 |
| One side of the market missing | 6 |
| Prices that cannot exist: both sides plus money, or a margin outside 1.5–25% on the moneyline, 0–15% on spreads and totals | 5 |
| Placeholder prices (±10000 and beyond) | 5 |
| Over and under quoted on different lines | 2 |

Most of the totals left out are 2023 Heritage and Bovada totals far below the other books: in-game numbers, not
closing lines. 3 public betting splits recorded 0% / 0% are left empty.

Also checked across the whole file: `Total_Points`, `Winner` and `Margin` agree with the score on every row; every
American price matches its decimal price; every remaining moneyline has a margin between 1.5% and 25%; the spread
lines of the two teams are opposite; every game is unique. Every game was also matched to an independent schedule:
same teams and same final score on all 2,034, same home and away sides on all but one game of the 2020 bubble.

## Coverage

Games with a price, source by source:

| Source | Moneyline | Spread | Total |
|---|---:|---:|---:|
| Opener (opening line) | 1,970 (96.9%) | 1,991 (97.9%) | 2,025 (99.6%) |
| Betcris | 1,658 (81.5%) | 1,707 (83.9%) | 1,709 (84.0%) |
| Heritage | 2,020 (99.3%) | 2,019 (99.3%) | 1,962 (96.5%) |
| BetOnline | 2,001 (98.4%) | 2,024 (99.5%) | 2,027 (99.7%) |
| Bovada | 2,007 (98.7%) | 2,009 (98.8%) | 1,971 (96.9%) |
| BetAnything | 1,212 (59.6%) | 1,291 (63.5%) | 1,291 (63.5%) |
| William Hill | 2,009 (98.8%) | 2,002 (98.4%) | 2,004 (98.5%) |
| Everygame | 2,020 (99.3%) | 2,027 (99.7%) | 2,026 (99.6%) |

Moneyline coverage, season by season (% of the season's games):

| Source | 2018 | 2019 | 2020 | 2021 | 2022 | 2023 | 2024 | 2025 | 2026 |
|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|
| Opener | 93% | 96% | 96% | 95% | 99% | 98% | 96% | 99% | 99% |
| Betcris | 99% | 98% | 96% | 48% | 6% | 92% | 99% | 99% | 99% |
| Heritage | 100% | 100% | 95% | 99% | 100% | 100% | 100% | 100% | 100% |
| BetOnline | 94% | 97% | 97% | 98% | 100% | 98% | 100% | 100% | 100% |
| Bovada | 93% | 100% | 97% | 99% | 100% | 99% | 100% | 100% | 100% |
| BetAnything | 0% | 0% | 0% | 3% | 100% | 89% | 97% | 96% | 100% |
| William Hill | 100% | 99% | 88% | 98% | 100% | 100% | 100% | 100% | 100% |
| Everygame | 100% | 99% | 99% | 99% | 99% | 99% | 99% | 100% | 100% |

- **Betcris is missing from 12 August 2021 to 21 August 2022** (316 games in a row): the source has
  no Betcris price on them. It is present on more than 90% of the games of every other season.
- **BetAnything starts in September 2021** (spreads and totals from 7 September, the moneyline from 6 October 2021).
- On 963 games all seven books have a closing moneyline; the median game has six.
- Three games have no closing moneyline at all: 30 June 2018 (Phoenix at Washington), 17 July 2019 (Atlanta at
  Chicago) and 26 July 2020 (Connecticut at Minnesota).
- Public betting split: moneyline on 1,879 games, spread and total on 1,979.

## What changed since the first edition

- **BookMaker and Ozoon are gone.** On this source they repeat Betcris and Bovada: the same prices on every game,
  except one BookMaker spread and two Ozoon spreads in May 2018. Betcris and Bovada stay.
- **The 84 games from 23 June to 29 July 2026 now have their prices.** The first edition carried their lines only.
- **26 games are back**: 2 playoff games of 2 September 2018, 2 games of July 2019, 2 games of 2020, 2 of 2022 and
  18 of 2025, including Chicago at Indiana on 17 May 2025. Each one was matched to an independent schedule: same teams,
  same final score.
- **Pick'em and half-point spreads now carry their line**: `0` on every pick'em, `0.5` / `-0.5` on 15 spreads; the
  first edition left the line empty.
- **17 to 22 June 2026**: the moneylines of these 20 games are read again with the order of the books on the source
  on those days.
- **17 July 2019**: Seattle at Minnesota has its spread and total back; Atlanta at Chicago, which has no price at the
  source, no longer carries the spread and total of another game.
- **Five moneyline betting splits fixed** (99% / 1%, not 99% / 100%).
- **Dates are `YYYY-MM-DD`** as documented, tip-off times on a 24-hour clock, and the first game has its time.
- **Prices that cannot exist are left out**, as described above.

## Known limitations

Stated up front rather than discovered later.

- **The 2026 season stops on 29 July 2026.** The rest of the season is not in this edition.
- **Games missing at the source**: the 5 games of 1 July 2018 and 9 games of the 2020 bubble (25 July, opening day:
  3; 31 August: 2; 7 September: 1; 13 September: 3).
- **Games damaged at the source**: 33 Las Vegas Aces games of 2025, whose Aces row is overwritten on the source page
  (no team, no score, no moneyline or spread price), and Toronto at Phoenix on 19 May 2026, whose score is wrong on
  the source page. They are left out rather than guessed.
- **One opening line, no opening price per book.** The seven books carry closing prices only.
- **Full game only**: no halves, no quarters, no team totals, no player props, no live odds.
- **The 2020 season was played in a single bubble venue**: home and away are the league's designation.
- **Times are US Eastern time** as published, not time-zone-aware timestamps.

## License

Single commercial user. Use the data as you wish, including the models, predictions and products you sell.
Redistribution and resale of the files, or of the raw data in another format, are not permitted.

*Olivier Sports Data — From Chicken Area 🐔 · collected by hand, page by page*
