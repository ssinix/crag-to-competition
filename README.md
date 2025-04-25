# DSA 210 Term Project Proposal: Climbing Performance Analysis

<h3 align="center"> From Crag to Competition: Does Outdoor Sport Climbing Translate to Competitive Success?</h3>

<div align="center">
    <img src="data/crag-to-comp-thumbnail.jpg" alt="Before Inversion" width="500">
</div>

## Motivation
Climbing is a rapidly growing sport, with distinct communities in outdoor sport climbing and indoor competitive climbing (e.g., bouldering and lead climbing). As a climber myself and an avid follower of International Federation of Sport Climbing (IFSC) competitions, I've often wondered how performance in outdoor sport climbing correlates with success in formal competitions, such as those organized by IFSC. This project aims to explore whether skills and achievements in outdoor sport climbing, as logged by climbers on platforms like 8a.nu, translate to competitive performance in IFSC boulder and lead climbing events.

# Data Collection and Analysis Process

## [IFSC Competition Data](https://www.ifsc-climbing.org/)

Using Python with `requests` and `BeautifulSoup`, I scraped competition results from the IFSC website, collecting the following fields:

- **name**: Climber's name  
- **country**: Climber's country  
- **gender**: Climber's gender  
- **boulder_points**: Points in boulder discipline  
- **lead_points**: Points in lead discipline  
- **combined_points**: Points in combined discipline  

---

## [8a.nu Profile Data](https://www.8a.nu/)

The data collection from 8a.nu was completed in two steps:

### Profile Finding (`1.2_8anu_profile_finder.ipynb`)

- Used **Selenium** for web automation to search for IFSC climbers on 8a.nu  
- Employed **fuzzy string matching** to find the most relevant profiles based on name similarity  
- Addressed challenges of name standardization across platforms  

### Profile Scraping (`1.3_8anu_profile_scraper.ipynb`)

Used **Selenium** and **BeautifulSoup** to extract key performance metrics:

- **Highest Grade Climbed**: The most difficult route completed (converted to a linear scale)  
- **8c+ and Above Ascent Count**: Total number of ascents at grade 8c+ or higher  
- **Average Grade**: Weighted average of the first 5 unique grades to avoid skewing by numerous lower-grade ascents  

---

## Data Merging

In the final data collection step (`1.4_merge_data.ipynb`), I merged IFSC and 8a.nu data to create a comprehensive dataset with all collected metrics:

- IFSC competition metrics (boulder, lead, and combined points)  
- Outdoor climbing performance metrics (highest grade, count of 8c+ routes, average grade of first five ascents)  

---

## Analysis Process

The analysis was conducted in two main steps:

### Exploratory Data Analysis (`2.1_EDA.ipynb`)

- Explored relationships between outdoor climbing metrics and competition performance  
- Analyzed distributions and correlations between variables  
- Created visualizations to identify patterns and insights  

### Hypothesis Testing (`2.2_hypothesis_testing.ipynb`)

Conducted statistical tests to evaluate the hypotheses:
- **Outdoor vs. Competition Performance:**
   Do climbers with stronger outdoor climbing metrics—such as higher maximum grade or having a 8c+ ascent—also perform better in competitions?
   *Separate hypothesis tests will be conducted for each competition discipline: bouldering, lead, and combined.*

- **Interdisciplinary Competition Correlation:**
   Is there a statistically significant correlation between performance in different IFSC competition disciplines (e.g., do high lead scores correlate with high boulder scores)?
- **Outdoor Performance Correlation:**
    Within outdoor climbing, is there a meaningful correlation between the metrics (e.g., do higher average grades correlate with higher best grade climbed)?



