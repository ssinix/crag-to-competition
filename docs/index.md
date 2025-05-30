# Does Outdoor Sport Climbing Translate to Competitive Success?

## Motivation

Climbing is a rapidly growing sport, with distinct communities in outdoor sport climbing and indoor competitive climbing (e.g., bouldering and lead climbing). As a climber myself and an avid follower of International Federation of Sport Climbing (IFSC) competitions, I've often wondered how performance in outdoor sport climbing correlates with success in formal competitions, such as those organized by IFSC. This project aims to explore whether skills and achievements in outdoor sport climbing, as logged by climbers on platforms like 8a.nu, translate to competitive performance in IFSC boulder and lead climbing events.

## Data Collection

### Data Sources

<div align="center">
    <img src="https://upload.wikimedia.org/wikipedia/en/d/d9/International_Federation_of_Sport_Climbing_Logo.svg" alt="IFSC Logo" width="200" style="margin: 0 20px;">
    <img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQzMcmVlfxZqlNu8Ul--qUAFPRxg6sKW93xww&s" alt="8a.nu Logo" width="200" style="margin: 0 20px;">
</div>

This project combines data from two primary sources: the International Federation of Sport Climbing (IFSC) for competition performance metrics, and 8a.nu for outdoor climbing achievements.

### Data Collection Process

The data collection process consisted of four main steps:

1. **Scraping IFSC Rankings**: Extracted climber information from the IFSC athlete rankings page using Python (`requests`, `BeautifulSoup`), collecting names, countries, gender, and points across boulder, lead, and combined disciplines.

2. **Finding IFSC Climbers on 8a.nu**: Used fuzzy string matching techniques to identify IFSC competitors' profiles on the 8a.nu platform, accounting for variations in name formatting and spelling.

3. **Scraping 8a.nu Profiles**: Employed Selenium to scrape outdoor climbing data from matched profiles, extracting highest grade climbed, count of 8c+ ascents, and average grade of first 5 unique ascents.

4. **Data Merging**: Combined IFSC competition data with 8a.nu outdoor climbing metrics, resulting in a final dataset of **551 climbers** with both competition and outdoor climbing performance data.

<div align="center">
    <img src="https://i.ytimg.com/vi/o-mvzn_QjAQ/hq720.jpg?sqp=-oaymwEhCK4FEIIDSFryq4qpAxMIARUAAAAAGAElAADIQj0AgKJD&rs=AOn4CLBaxSam--CADcyJDUBMQII2jui5hw" alt="Brooke Rabotou" width="200" style="margin: 0 20px;">
</div>

## Analysis

### Exploratory Data Analysis

The exploratory phase involved comprehensive analysis of the combined dataset to understand the relationships between outdoor and competition climbing performance. Key activities included:

- Analyzing distributions and correlations between outdoor climbing metrics and competition performance
- Segmenting data by climbing discipline due to varying athlete participation patterns
- Examining performance patterns across different regions and gender categories  
- Creating visualizations including scatter plots, correlation heatmaps, and pairplots to identify underlying relationships in the data

### Hypothesis Testing

Statistical analysis was conducted across five key research hypotheses:

1. **8c+ Benchmark vs Competition Performance**: Two-sample t-tests demonstrated that climbers with 8c+ ascents significantly outperform those without across all disciplines, with the strongest effects observed in lead and combined formats.

2. **Highest Outdoor Grade vs Competition Performance**: Pearson correlation tests revealed statistically significant moderate positive correlations for bouldering and combined disciplines, but no significant correlation for lead climbing specifically.

3. **Average Outdoor Grade vs Competition Performance**: Significant but modest correlations were found across all disciplines, with the strongest relationship appearing in bouldering competition performance.

4. **Inter-discipline Competition Correlations**: Strong correlations between all IFSC disciplines indicated substantial overlap in required skillsets across different competition formats.

5. **Outdoor Metrics Correlations**: Strong correlation between highest grade achieved and average grade demonstrated consistency in outdoor climbing performance across athletes.

## Machine Learning

Predictive models were developed to forecast competition performance using outdoor climbing metrics as features. Two primary approaches were implemented:

**Model Performance Comparison:**
- **Baseline RMSE**: 879.60 (mean prediction)
- **Linear Regression**: ~450 RMSE (representing 7% of target range)
- **XGBoost**: 297.63 RMSE with 10-fold cross-validation (4.6% of target range)

The XGBoost model significantly outperformed linear regression across all validation methods, demonstrating the value of ensemble methods for this prediction task. However, the limited explanatory power (6-11% of variance explained) suggests that outdoor climbing performance, while statistically significant, represents only one component of competitive climbing success.

**Key Findings:**
- Outdoor climbing metrics show limited but significant correlation with competition performance
- The 8c+ achievement threshold serves as a strong indicator of competition success across all disciplines
- Strong inter-discipline correlations within IFSC competitions suggest effective skill transfer between different competitive formats