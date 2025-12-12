# ⚽ Premier League Power BI Dashboard
A complete analytics dashboard built in **Power BI** to visualize Premier League match statistics, team performance, and season-based KPIs.

---

## 📊 Features
- Total Wins / Draws / Losses
- Goals For / Goals Against
- Goal Difference (GD)
- Total Points (Win = 3, Draw = 1)
- Clean Sheet Count
- Match Result Classification
- Home vs Away Performance
- Season Summary Trends

---

## 🧱 DAX Calculated Columns

### ✔️ Match Result
```DAX
Result =
IF(
    Matches[Goals_For] > Matches[Goals_Against], 
    "Win",
    IF(
        Matches[Goals_For] < Matches[Goals_Against], 
        "Loss", 
        "Draw"
    )
)
---
```
### abc  
