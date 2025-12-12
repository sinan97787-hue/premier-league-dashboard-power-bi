# ⚽ Premier League Power BI Dashboard
A complete analytics dashboard built in **Power BI** to visualize Premier League match statistics, team performance, and season-based KPIs.

---
## **Dashboard Preview**

<img width="1368" height="777" alt="Screenshot (29)" src="https://github.com/user-attachments/assets/116edbab-fe4a-43ec-96d6-4ac027b0e34b" />


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
### **Clean Sheet** 
```DAX
Clean_Sheet =
IF(Matches[Goals_Against] = 0, 1, 0)

```
### **Goal Difference**
```DAX 
Goal_Difference =
Matches[Goals_For] - Matches[Goals_Against]
```
### **Goal Scored**
```DAX
Goals_Scored =
SUM(Matches[Goals_For])
```
### **Total Points**
```DAX
Total_Points =
SUMX(Matches,
    SWITCH(Matches[Result],
        "Win", 3,
        "Draw", 1,
        "Loss", 0
    )
)
```
### **Goal conceded**
```DAX
Goals_Conceded =
SUM(Matches[Goals_Against])
```
## **Power query steps**

- Import Matches and Teams tables from CSV.

- Transform columns: date formatting, text cleanup, numeric conversion.

- Merge tables if needed for team-related info.

- Create calculated columns and measures using DAX.

## **Author**

- Muhammed Sinan
- email:sinan97787@gmail.com
- connect with me on linkedIn :https://www.linkedin.com/in/sinan-p/


