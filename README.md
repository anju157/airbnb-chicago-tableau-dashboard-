
# 🏡 Chicago Airbnb Analysis – Tableau Dashboard Portfolio

This project analyzes Airbnb listings in Chicago using interactive Tableau dashboards. With rich visualizations and advanced Tableau features like LOD expressions, set actions, and parameters, it enables a deep dive into trends around pricing, property types, host performance, and guest preferences.

---

## 📊 Dashboards Included

### 1. **Customer Interface**
- Symbol map with interactive filters for price, beds, baths, guest count
- Top N listings based on user-chosen metric (price, review score, etc.)
- Navigation buttons and calculator for estimating stay cost

### 2. **Property Analysis**
- Heatmaps, scatter plots, and star symbol charts
- Property distribution by neighborhood and type
- Review score comparison using LOD

### 3. **Price Analysis**
- KPI cards based on dynamic price threshold
- Donut chart of room types
- Highlight table showing price vs. availability status

### 4. **Host Analysis**
- Host rankings by listing count, rating, price
- Superhost status, response rate, tenure
- KPI panel for host performance and comparison

---

## 🧠 Key Calculated Fields

<details>
<summary><strong>Estimated Stay Cost</strong></summary>

<br>
 
[Price] * [Number of Guests] * [Max Nights]

</details>

</details> <details> <summary><strong>Availability Category</strong></summary>

IF [Availability_365] < 100 THEN "Rarely Available"
ELSEIF [Availability_365] < 250 THEN "Moderately Available"
ELSE "Highly Available"
END
</details> <details> <summary><strong>Host Tenure</strong></summary>

DATEDIFF('year', [Host Since], TODAY())
</details> <details> <summary><strong>Top N Listings Filter</strong></summary>

RANK_UNIQUE([Selected Metric]) <= [Top N Listings]
</details> <details> <summary><strong>Review Score Category</strong></summary>

IF [Review Scores Rating] >= 4.7 THEN "High Rated"
ELSEIF [Review Scores Rating] >= 4 THEN "Moderate Rated"
ELSE "Low Rated"
END
</details>
   
   --
   
🎛️ Parameters Used

Parameter	Function
- Top N Listings	Ranks listings based on selected metric
- Target Price Threshold	Filters KPIs and charts to stay within budget
- Min Bathrooms	Filters listings with min number of bathrooms
- Min Bedrooms	Filters listings with min number of bedrooms
- Number of Guests	Used in stay cost calculator
- Max Nights	Used in stay cost calculator
- Selected Metric	Toggles between Avg Price, Reviews, Revenue, etc.
- Availability Category	Classifies listings as Rarely/Moderately/Highly Available





---

[download Tableau Workfile](https://drive.google.com/file/d/1UKfojy1C99OpixPax_QmrVNK-YwK8Jl0/view?usp=sharing)
