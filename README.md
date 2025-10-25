# French Football ELO Ranking Project (1997–2025)

![video](/Bart_Chart_Race_Elo/elo.gif "Animated elo bar chart")


This project builds an **ELO-based ranking system** for French football (Ligue 1, Ligue 2, and National) over the last **30 years (1997–2025)**, using a dataset of around **30,000 matches**.

It includes:
- Complete **data scraping and cleaning**
- **ELO rating computation** for all teams
- A **perpetual ranking system** (points-based)
- Multiple **data visualizations**, including **animated bar chart races**

---

## Objective

To design a **new performance metric** that captures team form and historical strength, which can later be used for **feature engineering** in football match outcome prediction models.

---

## Update Workflow (Each New Version)

Every time new data is added, follow this process:

1. **Scrape match data**  
   → `scrapping_data.ipynb`

2. **Concatenate matchdays**  
   → `concatenate_results.ipynb`

3. **Update the perpetual ranking**  
   → `create_rankings.ipynb`

4. **Update ELO ratings**  
   → `Elo.ipynb`

5. **Update ELO ranking with match logs**  
   → `Elo_create_ranking.ipynb`

**After completing these steps**, you can directly:
- Generate **bar chart race animations**
- Plot **ELO evolution charts**

---

## Project File Overview (in the folder "programmes")

| File | Description |
|------|--------------|
| `scrapping_data.ipynb` | Web scraper for collecting French football match data. |
| `concatenate_results.ipynb` | Merges all matchday files into one dataset. |
| `create_rankings.ipynb` | Builds and updates the perpetual point-based rankings. |
| `Elo.ipynb` | Calculates and updates ELO ratings for each team after every match. |
| `Elo_create_ranking.ipynb` | Generates ELO-based rankings using game logs. |
| `plotting_Elo_evolution.ipynb` | Plots and visualizes ELO rating changes through time. |
| `bar_chart_race_elo.ipynb` | Creates animated bar chart races for ELO rankings. |
| `resizing_logos.ipynb` | Resizes and formats team logos for animations. |
| `teams.ipynb` | Lists all clubs and identifiers for each season. |
| `classement_global.csv` | Combined dataset containing all matches and rankings. |

---

## ELO Rating System

The ELO rating is calculated using a customized version of the standard formula:

$$
E_{new} = E_{old} + K \times (S - E)
$$

Where:

| Symbol | Meaning |
|:--------|:---------|
| $E_{old}$ | Current ELO rating |
| $S$ | Actual result (1 = win, 0.5 = draw, 0 = loss) |
| $E$ | Expected result, computed as: $E = \frac{1}{1 + 10^{(E_{opponent} - E_{team}) / 400}}$ |
| $K$ | Sensitivity coefficient depending on competition level |

**Adjustments and extensions:**
- Different **K values** depending on the division (L1, L2, National)
- **Reset to 1200** after long inactivity or special cases (e.g., COVID season)
- **Penalty of -100 ELO points** applied to teams that are no longer in the rankings. 

---

## Perpetual Ranking System

The perpetual ranking is based on a custom point system that considers division level:

| Division | Win | Draw | Loss |
|:----------|:---:|:----:|:----:|
| Ligue 1 | 9 | 3 | 0 |
| Ligue 2 | 6 | 2 | 0 |
| National | 3 | 1 | 0 |

This ranking rewards consistency and long-term performance across different leagues.

---

## Visualizations

### **Bar Chart Race**

- Built using the **`bar_chart_race`** Python library.  
- The library was **modified** to include **club logos** next to each bar for improved visuals.  
- The result is an animated `.gif` or `.mp4` showing team ranking evolution over time.

**Example:**
```markdown
![Animated ELO Bar Chart](Bar%20Chart%20Race%20Elo/elo.gif "Animated ELO Bar Chart")
