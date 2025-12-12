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

---
### 🟢 Total Goals by Country
Goals by Country = 
CALCULATE(
    SUM(Goals[Goals_Scored]),
    ALLEXCEPT(Players, Players[Nationality])
)

---
### 🟢 Total Red Cards
Total Red Cards =
CALCULATE(
    COUNTROWS(Cards),
    Cards[Card_Type] = "Red"
)

---
### 🟢 Total Clean Sheet 
Clean Sheets =
CALCULATE(
    COUNTROWS(Matches),
    Matches[Clean_Sheet] = 1
)

---
### 🟢 Total Goal Percentage 
Goal % = 
DIVIDE(
    [Total Goals],
    CALCULATE(SUM(Goals[Goals_Scored]), ALL(Clubs)),
    0
)
---

## 🧱 DAX Calculated Columns

### ✔️ Match Result
```DAX
Result = 
IF(Matches[Goals_For] > Matches[Goals_Against], "Win",
    IF(Matches[Goals_For] < Matches[Goals_Against], "Loss", "Draw"))

---
### Clean sheet Flag
Clean_Sheet =
IF(Matches[Goals_Against] = 0, 1, 0)

---
## 🔧 Power Query Steps

- Removed duplicate rows  
- Cleaned null and inconsistent values  
- Reformatted date columns  
- Standardized club names  
- Extracted **Year** and **Month**  
- Split **Name** and **Country** columns  
- Filtered dataset to **1970–2018**  
- Loaded fact & dimension tables  

---

## 🧬 Data Model (Star Schema)

### 📦 Dimension Tables
- **Clubs**
- **Players**
- **Nationality**

### 📦 Fact Tables
- **Matches**
- **Goals**
- **Cards**

### 🔗 Relationships
- **Clubs → Matches**  
- **Players → Goals**  
- **Players → Cards**

---

## 📊 Visualizations Used

| Visualization        | Purpose                 |
|----------------------|--------------------------|
| **Bar Chart**        | Wins vs Losses           |
| **TreeMap**          | Clean Sheets             |
| **Pie Chart**        | Goals by Club            |
| **Table**            | Red Cards                |
| **KPI Cards**        | Wins, Losses, Goals      |
| **Slicers**          | Year, Country, Club      |
| **Decomposition Tree** | Goals by Nationality  |

## 📷 Dashboard Preview

![Premier League Dashboard](Images/dashboard.png)

## 🚀 How to Use

1. Download the **.pbix** file  
2. Open it in **Power BI Desktop**  
3. Explore all visuals and slicers  
4. Modify data or visuals if needed  

---

## ⭐ Key Insights

- Manchester United & Man City lead in clean sheets  
- England produces the most goal scorers  
- Leicester City records the highest red cards  
- Tottenham, Liverpool & Man City show strong scoring performance  

---


---

## 🤝 Contributions

Contributions, improvements, and suggestions are always welcome.

---

## 📬 Contact

**Muhammed Sinan**  
📧 Email: sinan97787@gmail.com  
🔗 LinkedIn: https://www.linkedin.com/in/sinan-sinan/







