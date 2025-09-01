**Experiment 1: EDA in IPL Dataset**

**Aim:**

To perform Exploratory Data Analysis (EDA) on the IPL matches dataset and derive insights about matches per season, winning teams, toss decisions, and top venues.

**Algorithm / Procedure:**

**1.Import Libraries**
  Import pandas for data handling.
  Import matplotlib and seaborn for visualization.
**2.Load Dataset**
  Use pd.read_csv() to load the IPL matches dataset.
  Check dataset shape using .shape.
  View first 5 rows using .head().
**3.Matches per Season (Univariate Analysis)**
  Group data by season and count matches.
  Plot a bar chart to visualize growth/decline in matches.
**4.Top Winning Teams (Univariate Analysis)**
  Use value_counts() on the winner column.
  Plot top 5 winning teams in a bar chart.
**5.Toss Decisions (Univariate Analysis)**
  Count toss decision preferences (bat vs field).
  Plot results using a bar chart.
**6.Top Venues (Univariate Analysis)**
  Count matches per venue.
  Display top 5 venues with a horizontal bar chart.
**7.Draw Insights**
  Observe patterns in toss decisions.
  Identify teams with consistent winning trends.
  
  **Program**
  ```
  import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns
# Step 2: Load the dataset
matches = pd.read_csv(r"/matches.csv")
# Step 3: Basic info about dataset
print("Dataset Shape:", matches.shape) 
print(matches.head())

season_counts = matches['season'].value_counts().sort_index()
print("\nMatches per season:\n", season_counts)
# Plot matches per season
plt.figure(figsize=(8,4))
sns.barplot(x=season_counts.index, y=season_counts.values, palette="viridis")
plt.title("Number of Matches per Season")
plt.xlabel("Season")
plt.ylabel("Matches")
plt.show()

team_wins = matches['winner'].value_counts()
print("\nTop Winning Teams:\n", team_wins.head(5))
plt.figure(figsize=(8,4))
sns.barplot(x=team_wins.head(5).index, y=team_wins.head(5).values, palette="magma")
plt.title("Top 5 Winning Teams")
plt.xlabel("Team")
plt.ylabel("Wins")
plt.show()

toss_decision = matches['toss_decision'].value_counts()
print("\nToss Decisions:\n", toss_decision)
plt.figure(figsize=(6,4))
sns.barplot(x=toss_decision.index, y=toss_decision.values, palette="Set2")
plt.title("Toss Decisions (Bat or Field)")
plt.show()

venue_counts = matches['venue'].value_counts().head(5)
print("\nTop Venues:\n", venue_counts)
plt.figure(figsize=(8,4))
sns.barplot(y=venue_counts.index, x=venue_counts.values, palette="coolwarm")
plt.title("Top 5 Venues by Matches Hosted")
plt.xlabel("Matches Hosted")
plt.ylabel("Venue")
plt.show()
```

  **Output**
  
<img width="775" height="786" alt="image" src="https://github.com/user-attachments/assets/02c414d7-c792-4817-8453-a37436cf6068" />

<img width="1619" height="547" alt="image" src="https://github.com/user-attachments/assets/25546b5d-146b-452b-8940-036b2a36439a" />

<img width="890" height="533" alt="image" src="https://github.com/user-attachments/assets/60f4eaca-2713-4028-a0aa-ac833ab27221" />

<img width="1637" height="780" alt="image" src="https://github.com/user-attachments/assets/c2570020-feff-4d45-9c32-b8ff0cca1c94" />

<img width="1601" height="735" alt="image" src="https://github.com/user-attachments/assets/d65f83f5-89a2-4d4a-9140-c0edc07ba63c" />

<img width="1690" height="783" alt="image" src="https://github.com/user-attachments/assets/5896e90d-304b-486a-9e65-16cac199b5a1" />


 **Result**
 
  This experiment is executed successfully Highlight the stadiums hosting maximum matches.
