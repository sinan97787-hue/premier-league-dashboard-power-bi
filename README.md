# Premier League Stats Dashboard (1970–2018)

Interactive Power BI dashboard built from a Premier League player dataset covering seasons from 1970 to 2018.[file:2]  
The report highlights club and player performance including wins, losses, goals, clean sheets, red cards, and goals by nationality.[file:2][image:1]

## Author

- **Author:** Your Name  
- **Email:** your.email@example.com  
- **GitHub:** https://github.com/your-profile  

Update these details with your own information before publishing.

## Dataset

The project uses `data-of-PL-1970-2018.csv`, which contains one row per player with statistics such as appearances, wins, losses, goals, clean sheets, tackles, passes, duels, yellow cards, and red cards.[file:2]  
Key columns include `Name`, `Club`, `Position`, `Nationality`, `Age`, `Appearances`, `Wins`, `Losses`, `Goals`, `Clean sheets`, `Goals conceded`, `Passes`, `Assists`, `Yellow cards`, and `Red cards`.[file:2]

## Data Model: Calculated Columns

Add these calculated columns in Power BI (Table: `PL Data` or your table name):

```DAX
Win Rate (%) =
DIVIDE ( 'PL Data'[Wins], 'PL Data'[Appearances] ) * 100

Loss Rate (%) =
DIVIDE ( 'PL Data'[Losses], 'PL Data'[Appearances] ) * 100

Goals per 90 =
DIVIDE ( 'PL Data'[Goals], 'PL Data'[Appearances] ) * 90

Discipline Score =
'PL Data'[Yellow cards] + 3 * 'PL Data'[Red cards]

-- CORE TOTALS

Total Goals :=
SUM ( 'PL Data'[Goals] )

Total Wins :=
SUM ( 'PL Data'[Wins] )

Total Losses :=
SUM ( 'PL Data'[Losses] )

Total Appearances :=
SUM ( 'PL Data'[Appearances] )

Total Clean Sheets :=
SUM ( 'PL Data'[Clean sheets] )

Total Yellow Cards :=
SUM ( 'PL Data'[Yellow cards] )

Total Red Cards :=
SUM ( 'PL Data'[Red cards] )
