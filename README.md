# AirBNB New York Revenue Analysis     <font size=2>v2.0</font>
  <code style="color:#4a304f"><font color= #d689e6>bootcamp project</font></code>

This capstone project for the Télos bootcamp addressed the challenge of increasing AirBNB revenue in New York City despite its many platform restrictions. We synthesized our accumulated learning to develop a solution, which we presented to our sponsor, ThoughtWorks, demonstrating our technical capabilities and progress.

### 💁‍♀️ Team

- [Gabrielle Rosa](https://github.com/gabxrosa)
- [Nayara Ramos](https://github.com/nay-ramos)

---

### 🗃️ Dataset

><font size=2>>>> [NY Airbnb open data - Kaggle.com](https://www.kaggle.com/datasets/dgomonov/new-york-city-airbnb-open-data) by  Dgomonov  **and** [NY Airbnb listing details - Inside Airbnb](https://insideairbnb.com/get-the-data/) by Inside Airbnb</font>


>

---

### ❓❓ The question:

1. What are the main factors (accommodation characteristics and host profile) that drive revenue from Airbnb listings in New York, and how can these insights be translated into effective strategies to increase the platform's revenue in the city?


---

###  ⚙️ Methodology:
  1. Data Consolidation
  2. Data Selection
  3. Database normalization
  4. Understanding and cleaning the data
  5. Preparing dataframe for PowerBI


---

### 🔨 Tools

<img width=150 title="Databricks" alt="Databricks" src="https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Flogos-world.net%2Fwp-content%2Fuploads%2F2024%2F01%2FDatabricks-Logo.jpg&f=1&nofb=1&ipt=1bbae2ef5109af0db178c7b5f304ccea32bf5c8081ac43a065ca1e34cf8de7b4"> <img width=198 title="PowerBI" alt="PowerBI" src="https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Fdatascientest.com%2Fes%2Ffiles%2F2020%2F10%2Fpower-bi-logo-1.jpg&f=1&nofb=1&ipt=099003c0f01745db97361ebe56ede7ec363ea05c5cf7a77759c528d984242c15">


#### PySpark [Databricks] (ETL process and handling large-scale data manipulation)
- Data Consolidation & Cleaning: Unified two primary datasets from Kaggle and Inside Airbnb. Performed joins, handled inconsistent formats (e.g., scientific notation), and replaced "N/A" values with nulls.
- Data Wrangling: Extensive null analysis, strategic filtering, and outlier removal (using IQR method) for price data to ensure data quality.
- Data Modeling & Feature Engineering: Split the unified dataset into four logical tables (rooms, hosts, reviews, amenities).
- Advanced Parsing with PySpark: The amenities column, originally a complex string formatted as a list, was parsed using PySpark functions (regexp_replace, split, explode). It was transformed into a structured format and pivoted to create boolean columns for the most relevant amenities.

#### Power BI (data modeling, visualization and building an interactive dashboard)
- Data Model: Established relationships between the imported tables (rooms, hosts, reviews, amenities) to create a robust star schema.
- DAX Calculations: Created key calculated columns for segmentation (e.g., Stay Duration Type) and advanced measures (e.g., Median Est Annual Income PER HOST).
- Interactive Dashboard: Developed a comprehensive report with various visuals (maps, bar charts, matrices, KPIs) and slicers to explore hypotheses and uncover insights dynamically.

---
### 📊 Dashboard
<img width="1421" height="811" alt="image" src="https://github.com/user-attachments/assets/f9b992d9-09ba-4658-9628-6d164cdc12d3" />

We have structured the analysis into four distinct dashboards, each designed to explore a specific facet of the business:

- General Overview: Provides a high-level summary of New York's overall market performance.
- Listings Analysis: Breaks down revenue performance by accommodation type and neighborhood.
- Host Analysis: Highlights the critical influence of host profiles and behaviors on revenue generation.
- Opportunity Analysis: Focused on identifying specific, actionable opportunities for revenue growth by location and market niche.
---

### 💡 Key Insights
The analysis focused on the **high-performance segment** (listings with high estimated occupancy and high future demand).

| Insight Area | Key Finding | Supporting Evidence |
| :--- | :--- | :--- |
| **📍 Location** | Perceived location is a primary revenue driver. | Strong positive correlation between neighborhood's average **location review score** and historical occupancy rate, especially for short-term stays. |
| **💰 Pricing & Stay Duration** | Short-term stays (<30 days) are the most profitable segment despite regulations. | Short-term rentals generated **$131M** vs **$110M** for long-term stays, despite being minority in volume. |
| **🏆 Host Status** | **Superhost status** commands a significant price premium. | Superhosts charge higher daily rates and achieve higher **median revenue** in high-performance segment where occupancy is already high. |
| **📈 Host Portfolio** | Portfolio size drives total revenue more than status alone. | Some Non-Superhosts with extensive portfolios outperform Superhosts in total revenue through volume, despite lower per-listing prices. |
| **🔄 Host Lifecycle** | Host revenue performance is non-linear. | Average host revenue peaks at **3-5 years** of experience, then stagnates or declines. |
| **🛋️ Amenities** | Minimal direct impact on pricing premium. | No clear correlation between specific amenities and significant price increases. Value tied to location and structural factors. |
| **⚡ Host Responsiveness** | Limited impact for high-performers. | High response/acceptance rates don't translate to significant gains beyond Superhost eligibility requirements. |

