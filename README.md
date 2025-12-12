# 🏆 Premier League Stats Dashboard (1970–2018)

A complete **Power BI analytics project** based on Premier League data covering **1970–2018**.  
This dashboard uses **Power BI**, **DAX measures**, **calculated columns**, and **Power Query** to explore team performance, clean sheets, goals, and discipline statistics.

---

# 📁 Dataset Information

- Matches data (Results, Goals For, Goals Against)
- Player information (Nationality, Age)
- Goals data (Scorers, Count)
- Cards data (Yellow/Red cards)
- Clean sheet data by club

**Format:** CSV (Cleaned & transformed in Power Query)

---

# 📊 Dashboard Features

### ✔ Wins & Losses by Club  
### ✔ Clean Sheets by Club  
### ✔ Goals Scored by Club  
### ✔ Goals by Nationality  
### ✔ Red Cards by Club  
### ✔ Interactive Slicers  
### ✔ Year Filtering (1970–2018)  
### ✔ Modern Professional UI with KPIs  

---

# 🛠 Tools & Technologies Used

| Technology | Purpose |
|-----------|----------|
| **Power BI Desktop** | Main BI Tool |
| **DAX** | Calculations & Measures |
| **Power Query** | Data Cleaning |
| **Star Schema Data Model** | Efficient querying |
| **CSV Dataset** | Raw Input |

---

# ⚙️ DAX Measures (Used in Dashboard)

### 🟢 Total Wins
```DAX
Total Wins = 
CALCULATE(
    COUNTROWS(Matches),
    Matches[Result] = "Win"
)
---

### 🟢 Total losses
```DAX
Total Losses =
CALCULATE(
    COUNTROWS(Matches),
    Matches[Result] = "Loss"
)
---
### 🟢 Total Goals
Total Goals = SUM(Goals[Goals_Scored])

