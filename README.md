# FIFA World Cup Performance Dashboard

An interactive Power BI report analyzing 256 matches across four FIFA World Cup tournaments (2002–2014), built to answer three questions: what does the overall tournament picture look like, which countries performed best, and how did goals tell the story.

## Why this dataset

World Cup match data is small and clean enough to model end-to-end — cleaning, DAX, and design — in a single project, while still raising real analytical questions: does home advantage hold up across tournaments hosted in different countries? Are finals actually more cautious than earlier rounds? The answers aren't obvious from the raw rows, which is what makes it worth building a dashboard instead of just reading the CSV.

## Key findings

| Finding | What the data shows |
|---|---|
| Home advantage is real and consistent | Home teams won ~43% of matches across all four tournaments, despite each one being hosted in a different country |
| Finals are the most cautious stage | Average goals per match are lowest in the Final and highest in the Third Place match — teams play tighter when the stakes are highest |
| Scoring dipped, then rebounded | Average goals per match fell to their lowest point in 2010 before climbing sharply by 2014 |
| Germany leads all-time wins | Germany tops total wins across this period despite hosting only one of the four tournaments |
| Away scoring caught up by 2014 | Home goals consistently outpaced away goals from 2002–2010, but away-team scoring overtook home-team scoring for the first time in 2014 |

## Report structure

The report is four pages, each answering one question:

| Page | Question it answers | What's on it |
|---|---|---|
| **Tournament Overview** | What does the overall picture look like? | KPI cards, goals-by-year trend, matches by stage |
| **Country Performance** | Which countries performed best? | Top countries by wins, match results by year, year slicer |
| **Goals Analysis** | How did goals tell the story? | Average goals by stage, home vs away goals by year |
| **Summary** | All of the above, at a glance | KPI row, year slicer, and the four strongest visuals composed into one interactive view |

## Approach

**Data modeling** — Cleaned and structured the raw match data in Power Query, then built custom DAX measures for win rate, home/away win percentage, and average goals by stage rather than relying on default aggregations.

**Design decisions, not just defaults** — Every visual uses a consistent white-card, soft-shadow, single-accent-color treatment instead of Power BI's default styling. The summary page isn't a fifth arbitrary page — it's a deliberate composition of the strongest visual from each of the other three, built so the dashboard's main story can be read in one screen.

**Known limitation, stated rather than hidden** — Country win totals are calculated from home-team appearances; a fully accurate per-country win count would require unpivoting home/away teams into a single dimension table. This was a deliberate scope decision for a four-tournament dataset, not an oversight — noted here rather than left for a reviewer to catch.

## Tools

- **Power BI Desktop** — data modeling, DAX, report design
- **Power Query** — data cleaning and transformation
- **DAX** — custom measures for win rate, home/away splits, and stage-level scoring

## Project structure

```
├── World Cup Dashboard.pbix          # Full Power BI report (all 4 pages)
├── data/
│   └── WorldCupMatches.csv           # Source dataset
├── screenshots/
│   ├── 01-tournament-overview.png
│   ├── 02-country-performance.png
│   ├── 03-goals-analysis.png
│   └── 04-summary.png
├── LICENSE
└── README.md
```

