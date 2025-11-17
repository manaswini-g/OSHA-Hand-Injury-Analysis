
# OSHA Hand Injury Analysis (Data Whiz 2025 Hackathon)

> An end-to-end analysis of OSHA Severe Injury Reports to identify the "how," "when," and "where" of hand injuries in the US manufacturing industry. This project combines Geospatial, Time Series, and advanced NLP (Topic Modeling) to provide actionable safety recommendations.

![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white)
![scikit-learn](https://img.shields.io/badge/scikit--learn-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white)
![Folium](https://img.shields.io/badge/Folium-31A134?style=for-the-badge&logo=Folium&logoColor=white)

---



###  Project Objective

This project was developed for the **Data Whiz 2025 Hackathon (Safety Excellence Problem Statement)**. The goal was to analyze a private dataset of OSHA Severe Injury Reports to discover deep insights into **how** hand-related injuries occur in the manufacturing industry and to visualize these findings for stakeholders.

### Key Insights & Recommendations 

This multi-faceted analysis uncovered clear, actionable patterns. The NLP analysis, in particular, moved beyond *what* happened (an injury) to *how* it happened (the narrative).

1.  **NLP - How Injuries Happen:**
    * **Topic Modeling (LDA)** successfully clustered thousands of injury narratives into **5 distinct topics**:
        1.  **Maintenance-Related Amputations** (e.g., on pipes, valves)
        2.  **Pinch-Point Injuries** (e.g., lifting steel, "caught")
        3.  **Machine Amputations** (e.g., index/middle fingers)
        4.  **Roller & Conveyor Injuries** (most common)
        5.  **Falls** (leading to arm/hand fractures)
    * **Action Verb Analysis** confirms most injuries are active, not passive. The most common verbs are **"amputate," "cut," "pull," and "remove,"** suggesting injuries often happen during high-risk maintenance or un-jamming procedures.

2.  **Time Series - When Injuries Happen:**
    * **Seasonal Surge:** Injuries consistently spike in the summer (Q2-Q3), peaking in July. This correlates with increased production quotas, new/seasonal workers, and heat-related fatigue.
    * **Recommendation:** Implement "Summer Safety" campaigns in May/June, increase mandatory hydration breaks, and provide extra training for new hires.

3.  **Geospatial - Where Injuries Happen:**
    * Heatmaps and cluster analysis show injury hotspots are concentrated in major manufacturing and industrial corridors, allowing for targeted regional safety campaigns.

---



### Analytical Approach & Visualizations

This project was broken into three main analytical components.


### 1. Natural Language Processing (NLP) 

The "Final Narrative" (incident description) field was analyzed using NLP to extract themes and actions. This directly answers the core problem statement.

#### Topic Modeling (LDA)
The LDA model identified 5 clear injury scenarios. Topics 3 and 4 were the most frequent, indicating machine-specific injuries are the primary concern.

* **Topic 1:** Maintenance-Related Amputations (Pipes, Valves)
* **Topic 2:** Pinch-Point Injuries (Lifting, Steel)
* **Topic 3:** Finger Amputations in Machinery (Index & Middle Fingers)
* **Topic 4:** Machine Roller & Conveyor Injuries
* **Topic 5:** Falls & Arm/Hand Fractures

#### Action Verb Analysis
Extracting the most common verbs from injury reports reveals *how* the injury occurred. The data shows injuries are linked to specific actions like "pulling," "removing," or "operating."

![Action Verb Bar Chart](Visualizations/action-verb-barchart.png)

#### Keyword & Co-Occurrence Analysis
TF-IDF and network graphs revealed the key objects and body parts.
* **Key Keywords:** `finger`, `hand`, `machine`, `caught`, `amputate`, `conveyor`, `roller`, `blade`.
* **Co-Occurrence:** The network graph shows a strong link between "finger" and "caught," and "machine" and "amputation."

![Co-occurrence Network](Visualizations/co-occurrence.png)

### 2. Time Series Analysis - The "When"

Analyzing the incident date revealed clear temporal patterns.

#### Trend and Seasonality
The plot shows a long-term trend (peaking 2020-2021) and a clear seasonal pattern.
![Time Series Plot](visualizations/time-series-plot.png,png)

#### Seasonal Heatmap
This heatmap confirms that injuries consistently peak in the summer months (June-August) and dip in the winter (December-February), likely due to holiday shutdowns.
![Seasonal Heatmap](visualizations/seasonal-heatmap.png.png)

### 3. Geospatial Analysis - The "Where"

Using latitude and longitude, I mapped the incidents to find geographic hotspots.

#### Injury Heatmap
The heatmap clearly visualizes the density of incidents, highlighting major industrial regions.

* **See a static preview below. For the full interactive map, [click here](interactive-visuals/Injury_Heatmap.html).**

![Geo Heatmap Screenshot](visualizations/geo-heatmap.png)

#### Injury Clusters
A cluster map groups nearby incidents to show distinct zones of high activity.

* **See a static preview below. For the full interactive map, [click here](interactive-visuals/Injury_Clusters.html).**

![Geo Cluster Screenshot](visualizations/geo-clusters.png)




---

###  Data Setup

The original dataset for this hackathon was provided privately for the competition and is too large to be hosted on GitHub.

To allow for full reproducibility, the final, cleaned dataset used by the analysis notebook has been uploaded on the **/data** folder.

---



---

###  Technologies Used

* **Data Analysis:** Python, Pandas, NumPy
* **NLP:** Scikit-learn (`TfidfVectorizer`, `LatentDirichletAllocation`), NLTK, spaCy
* **Geospatial Viz:** Folium (for interactive maps)
* **Other Viz:** Matplotlib, Seaborn, Plotly
* **Workspace:** Jupyter Notebook
