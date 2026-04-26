# Power_bi_Dashboard_project

# 🏏 IPL Analysis Dashboard (2008–2025) | Power BI

An end-to-end interactive Power BI dashboard analysing **17 seasons of IPL data (2008–2025)**, covering team performance, player achievements, season statistics, and points table — all in one place.

---

## 📊 Dashboard Overview

This dashboard was built to answer key business and analytical questions about IPL seasons using real match data. It allows users to dynamically filter by season and instantly see updated stats across all visuals.

---

## ✨ Key Features

- **Season-wise Filtering** — Slicer to select any IPL season from 2008 to 2025
- **Season Winner & Runner-Up** — Displays champion and runner-up team with logo for each season
- **Orange Cap & Purple Cap** — Top run-scorer and top wicket-taker with player image and team
- **Points Table** — Full league stage standings with Played, Won, Lost, Tied, NR and Total Points
- **15+ KPI Cards** — Total Matches, Total Teams, Total Venues, Centuries, Half Centuries, Total Fours, Total Sixes
- **Most Fours & Most Sixes** — Top player for boundaries with image and team badge
- **Custom UI Design** — Cricket-themed icons, team logos, player images, and professional color theme

---

## 🗂️ Dataset Used

| Table | Description |
|---|---|
| `ipl_matches_data` | Match-level data for all IPL seasons (2008–2025) |
| `teams_data` | Team names, short codes, and logo image URLs |

---

## 🛠️ Tools & Technologies

| Tool | Usage |
|---|---|
| **Power BI Desktop** | Dashboard building and report design |
| **Power Query** | Data cleaning and transformation |
| **DAX (Data Analysis Expressions)** | Custom measures and KPI calculations |
| **GitHub** | Version control and project hosting |

---

## 📐 DAX Measures Created

```dax
-- Total Matches in a Season
TotalMatches = COUNTROWS(ipl_matches_data)

-- League Stage Wins
LeagueStageWins = CALCULATE(COUNTROWS(ipl_matches_data), ipl_matches_data[stage] = "League")

-- Most Fours by Top Player
MostFoursByTopPlayer = MAXX(TOPN(1, SUMMARIZE(...), [Total Fours], DESC), [Total Fours])

-- Season Winner
SeasonWinner = CALCULATE(SELECTEDVALUE(ipl_matches_data[match_winner]), ...)

-- Points Table - Total Points
TotalPoints = [Won] * 2 + [Tie]
```

---

## 📸 Dashboard Preview

> *Open the `.pbix` file in Power BI Desktop to view the full interactive dashboard.*

---

## 🚀 How to Use

1. Download the `.pbix` file from this repository
2. Open it in **Power BI Desktop** (free download from Microsoft)
3. Use the **Season slicer** on the dashboard to filter by any IPL year
4. All KPIs, charts and tables update automatically based on the selected season

---

## 📁 Repository Structure

```
Power_bi_Dashboard_project/
│
├── IPL Analysis 2008-2025.pbix    ← Main Power BI Dashboard file
└── README.md                      ← Project documentation (this file)
```

---

## 👤 Author

**Arpit Kandpal**
- LinkedIn: [linkedin.com/in/arpit-kandpal](https://www.linkedin.com/in/arpit-kandpal)
- GitHub: [github.com/lukadoncic842](https://github.com/lukadoncic842)

---

## 📌 Note

This project was built as part of my Data Analyst portfolio to demonstrate skills in **Power BI, DAX, data modelling, and dashboard design** using real-world IPL cricket data.
