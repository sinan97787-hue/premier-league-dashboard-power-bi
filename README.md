# 🏆 Premier League Dashboard

A **Power BI Dashboard** showcasing Premier League football statistics, including wins, losses, goals, clean sheets, and player performances.  
This project demonstrates interactive analytics using Power BI with DAX calculations and Power Query transformations.

---

## 📊 Features

- Total Wins, Losses, and Draws for each team
- Goals scored and conceded analysis
- Clean sheet tracking
- Match results trends over seasons
- Interactive Power BI visuals (charts, tables, filters)

---

## 🧱 DAX Calculated Columns

### ✔️ Match Result
Calculates if a match is a **Win, Loss, or Draw** for a team:
```DAX
Result = 
IF(
    Matches[Goals_For] > Matches[Goals_Against], 
    "Win",
    IF(Matches[Goals_For] < Matches[Goals_Against], 
       "Loss", 
       "Draw"
    )
)

### ✔️ Clean Sheet Flag
Flags matches where the team conceded 0 goals:

```DAX
Clean_Sheet =
IF(Matches[Goals_Against] = 0, 1, 0)

 



