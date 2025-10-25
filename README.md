# French Football ELO Ranking Project (1997–2025)

![video](/Bart_Chart_Race_Elo/elo.gif "Animated elo bar chart")

This is a personal project that focuses on creating an **ELO ranking system** for French football over the last 30 years, covering approximately **30,000 matches** between 1997 and 2025.

We **collected, scraped, and cleaned** the data to build a complete and consistent dataset.  
From this dataset, we developed an **ELO-based ranking system** to evaluate team performance over time.  

Additionally, we implemented a **perpetual ranking system** with fixed points depending on the league level:

| League | Win | Draw | Loss |
|:-------|:---:|:----:|:----:|
| Ligue 1 | 9 | 3 | 0 |
| Ligue 2 | 6 | 2 | 0 |
| National | 3 | 1 | 0 |

---

## Objective

The main goal of this project is to create a **new performance metric** that can later be used for **feature engineering** in predictive sports models (e.g., match outcome prediction).

---

## Project Structure

- **Bar Chart Race** → Folder containing an animated visualization of the perpetual ranking.  
- **Bar Chart Race Elo** → Folder containing an animated visualization of the ELO ranking.  
- **Data Visualization** → Folder to visualize the perpetual ranking.  
- **Elo** → Folder containing the individual ELO ratings for each team.  
- **Logos** → Contains all team logos.  
- **Programs** → All Python scripts used for scraping, cleaning, and computing rankings.  
- **Results** → All scraped match data (~30,000 matches).  
- **Teams** → Files listing the teams for each season.  

---

## Most Important Folder

The most critical folder is **Programs**, which contains all the Python scripts that power the data processing, ELO computation, and visualization workflows.

---

## Summary

- 30,000+ matches analyzed  
- 3 leagues tracked (Ligue 1, Ligue 2, National)  
- ELO and perpetual rankings developed  
- Visual animations of team evolution over time  
- Clean and reusable dataset for predictive modeling


