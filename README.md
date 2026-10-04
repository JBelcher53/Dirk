# DIRK

An NBA statistic that identifies the exact moment a game becomes mathematically decided and measures the clock time remaining at that point. It is computed per game and aggregated to the season level for teams and players.

Research paper: "Daggers and DIRK: Decisive Shots in NBA Games."

Built during a summer 2026 research fellowship at Williams College with Prof. Aaron Williams. Presented at the Williams College Summer Science Poster Session in August 2026.

## Results

- Predicts 2025-26 regular season win totals with R² = 0.924, compared with R² = 0.920 for raw point differential.
- Cross-validated over three postseasons (2023-24 through 2025-26): the team with the highest DIRK reached or won the Finals each year.
- Teams known for dramatic comebacks consistently underperform their predicted DIRK in the playoffs.
- Applied to a case study on the Jaylen Brown trade, and checked at the player level against an independent dataset from the faculty advisor.

## Data and pipeline

- Source: NBA play-by-play and box score data via the NBA API. Historical play-by-play (1996-97 onward) comes from the public `shufinskiy/nba_data` archive.
- Stack: Python, SQL, DuckDB.
- 2025-26 lineup data covers 1,321 games (1,230 regular season, 6 play-in, 85 playoff). Lineups are reconstructed with `pbpstats`, with a box-score fallback for period starters.
- Validation: five players per team on the floor at all times, minutes reconciled against official box scores, and team floor time equal to 5 × game length. 1,320 of 1,321 games pass cleanly. The one exception traces to an error in the live box score.

## Code and data

The research code and data are maintained in the project repository with Prof. Williams. This page is a summary of the project.

## Author

Justin Belcher Jr., Williams College
