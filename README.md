# Comprehensive SEO Performance Dashboard with Google Looker Studio

![Looker Studio](https://img.shields.io/badge/Looker_Studio-FEBD11?style=for-the-badge&logo=looker&logoColor=white)
![Google Search Console](https://img.shields.io/badge/Google_Search_Console-4581F4?style=for-the-badge&logo=google&logoColor=white)
![SEO](https://img.shields.io/badge/SEO_Analytics-1DA1F2?style=for-the-badge&logo=googleanalytics&logoColor=white)
![Data Visualization](https://img.shields.io/badge/Data_Visualization-D94E93?style=for-the-badge&logo=d3dotjs&logoColor=white)

An interactive and multi-page Looker Studio dashboard designed to transform raw Google Search Console (GSC) data into actionable business intelligence. This report provides a 360-degree view of a website's organic search health, enabling stakeholders to make data-driven decisions to improve SEO performance.

---

## 🚀 Live Demo & Preview

A live, interactive version of the dashboard is available for you to explore.

**➡️ [View the Live Interactive Dashboard Here](YOUR_LIVE_DASHBOARD_LINK)**

_Note: The live dashboard uses a sample dataset. The data is for demonstration purposes only._

Below is a short video walkthrough showcasing the dashboard's features and interactivity.

**(Recommended: Embed a GIF of your screen recording here. You can drag and drop it into the GitHub editor)**
![Dashboard Preview](PATH_TO_YOUR_VIDEO_OR_GIF.gif)

---

## ✨ Key Features

This dashboard is designed to provide insights at both a macro and micro level.

*   **Holistic Performance Overview:** At-a-glance KPIs (Impressions, Clicks, CTR, Avg. Position) with month-over-month comparison to quickly assess performance.
*   **Advanced Keyword Segmentation:**
    *   **Brand vs. Generic:** Automatically categorizes keywords to analyze brand equity and non-branded reach.
    *   **Short Tail vs. Long Tail:** Segregates keywords by length to evaluate performance across different stages of user intent.
*   **Deep Page-Level Analysis:** Identifies which pages are ranking on the 1st, 2nd, or 3rd+ pages of Google and tracks keyword movement (improved, declined, new).
*   **Comprehensive Data Blending:** Combines GSC's "Site Impression" and "URL Impression" data to link specific keywords to the exact pages they rank for, overcoming a common GSC limitation.
*   **Interactive Filters:** Global controls for Date Range, Country, Device Category, and more, allowing for deep-dive analysis on the fly.
*   **Visually Engaging Design:** Utilizes a clean, modern UI/UX with intuitive charts and graphs for clear data storytelling.

---

## 🛠️ Technical Implementation

This project demonstrates proficiency in data modeling and visualization within the Looker Studio environment.

*   **Data Source:** Google Search Console Connector.
*   **Data Blending:**
    *   A left join was performed on the GSC "URL Impression" (pages) and "Site Impression" (keywords) tables.
    *   **Join Key:** A custom key was created by concatenating `Landing Page` and `Date` to ensure accurate mapping between pages and the keywords driving their impressions.
*   **Custom Dimensions & Logic:**
    *   **Keyword Type (Brand vs. Generic):** A `CASE` statement was implemented to classify keywords based on a predefined list of brand terms.
        ```sql
        -- Example Logic
        CASE
          WHEN REGEXP_MATCH(Query, '(?i)(your-brand-keyword-1|your-brand-keyword-2)') THEN 'Branded'
          ELSE 'Generic'
        END
        ```
    *   **Keyword Length (Short vs. Long Tail):** A `CASE` statement using `REGEXP_REPLACE` to count the number of words in a query.
        ```sql
        -- Example Logic
        CASE
          WHEN LENGTH(REGEXP_REPLACE(Query, r'[^ ]', '')) + 1 <= 2 THEN 'Short Tail (1-2 words)'
          ELSE 'Long Tail (3+ words)'
        END
        ```
    *   **SERP Page Buckets:** `CASE` statements were used to group keywords by their average position into Top 3, Top 10, Top 20, and other ranking buckets.
*   **Calculated Metrics:** Created custom fields for month-over-month (MoM) comparisons for all key metrics to track growth and identify trends.

---

## 📄 Dashboard Structure (Page-by-Page)

The dashboard is organized into logical sections for intuitive navigation.

#### 1. Organic Overview
The main landing page providing a high-level summary of SEO performance.
*   **KPI Scorecards:** Impressions, Clicks, CTR, Average Position (with MoM % change).
*   **Performance Over Time:** Line graph illustrating click trends against the previous period.
*   **Device Performance:** Donut chart breaking down performance by Desktop, Mobile, and Tablet.
*   **Country Performance:** Geomap visualizing impressions and clicks by country.
*   **Top Pages & Queries:** Tables showing the top-performing content and keywords.

#### 2. Brand vs. Generic Analysis
Dedicated pages to analyze the impact of brand recognition on search performance.
*   **Overview Page:** Side-by-side comparison of KPIs for branded vs. generic keywords.
*   **Line Area Graph:** Visualizes the trend of branded vs. generic clicks and impressions over time.
*   **Brand & Generic Sub-pages:** Deep-dive tables showing specific keywords and their performance metrics for each category.

#### 3. Keyword Analysis (Short vs. Long Tail)
Focuses on user intent by analyzing the length of search queries.
*   **Overview Page:** Compares the aggregate performance of short-tail vs. long-tail keywords.
*   **Line Area Graph:** Tracks the performance trends of both keyword types.
*   **Short & Long Tail Sub-pages:** Detailed tables for granular analysis of keywords within each group.

#### 4. Page Rankings
Provides a SERP-centric view of performance.
*   **Overview Page:** KPI scorecards for keywords ranking in the Top 3, Top 10, and Top 20 positions.
*   **Performance by Rank:** A line graph showing the trend of keywords in each ranking bucket.
*   **Keyword Movement Tables:** Detailed lists of "Improved Keywords," "Declined Keywords," and "New Keywords" with their position changes.
*   **SERP Sub-pages:** Filtered views showing only the keywords and pages ranking on Page 1, Page 2, etc.

#### 5. Time Analysis
A focused view on performance over different timeframes.
*   **Total Performance Over Time:** A combo chart (bar + line) showing impressions and clicks monthly.
*   **Time Analysis Table:** A detailed monthly breakdown of all key SEO metrics.

---

## 💡 Skills Demonstrated

*   **Data Visualization:** Dashboard Design (UI/UX), Data Storytelling, Chart & Graph Selection.
*   **BI Tools:** Google Looker Studio (Expert Level).
*   **Data Modeling:** Data Blending, Custom Dimensions (CASE Statements), Calculated Fields.
*   **SEO Analytics:** KPI Analysis, Keyword Segmentation, SERP Performance Tracking, Branded vs. Non-Branded Analysis, User Intent Analysis.
*   **Project Management:** Requirement gathering, dashboard structuring, and delivering a finished, user-friendly analytics tool.

---

## 📬 Contact

Feel free to connect with me for collaborations or inquiries.

*   **Upwork:** [Your Upwork Profile Link]
*   **LinkedIn:** [Your LinkedIn Profile Link]
*   **Email:** your.email@example.com
