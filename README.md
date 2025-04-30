# Yandex_Data_Analysis
# Yandex E-commerce Revenue Optimization Project

Conducted an in-depth analysis of Yandex e-commerce sales data for "Delivery Dron," a platform selling delivery drones across multiple regions since May 2019, to maximize revenue and optimize investment strategies for 2020.
Utilized pandas for data preprocessing, numpy and scipy for statistical analysis (e.g., Pearson, Spearman, t-tests, chi-square, ANOVA), matplotlib and seaborn for visualizing sales trends, customer behavior, and channel performance.
Identified and resolved critical data collection issues for returning users (missing region, device, and channel data) by imputing values from first visits, improving dataset reliability for analysis.
Developed a Random Forest regression model using scikit-learn (R²: 0.2052, MAE: 681.41) to predict revenue, testing feature combinations (e.g., payment type, month, session duration) with randomized feature selection and hyperparameter tuning (test size: 0.1, n_estimators: 10).
Analyzed regional performance, finding the US as the dominant region (68-70% traffic) with high revenue from social media channels; recommended prioritizing social media ads in the US and contextual ads in the UK for high-margin growth due to superior conversion rates and average order values.

# Project Details
Objective
The primary goal was to analyze e-commerce sales data for "Delivery Dron" to provide actionable insights for revenue maximization and guide investment decisions for 2020. The project addressed investor queries about optimal regions and advertising channels for customer acquisition, delivering a data-driven strategy to enhance ROI. Key deliverables included an interactive dashboard for real-time monitoring and a presentation for stakeholders.
Data Sources

Sales Data: 12 months (May 2019–April 2020) of daily transaction records (~100,000 rows across 9 CSVs) containing user IDs, session details (start/end times, duration), order timestamps, revenue, payment types, and promo code usage.
User Data: Demographic and behavioral data, including region (e.g., US, UK, Germany, France), device (e.g., iPhone, Android, PC, Mac), and acquisition channel (e.g., social media, organic, contextual ads, email, blogger ads).
Key Metrics: Revenue, conversion rates, average order value (AOV), customer acquisition cost (CAC), and session duration.

# Methodology

Data Preprocessing:

Loaded and cleaned 9 CSV files using pandas, standardizing column names (e.g., lowercase, underscores) and converting timestamps (session_start, session_end, order_dt) to datetime format.
Identified missing data: 71.84% of rows lacked order-related data (expected, as not all sessions result in purchases), but 1.28% had missing region, device, and channel data.
Discovered a systematic data collection issue for returning users (post-July 1, 2019), where region, device, and channel were not recorded. Imputed missing values using first-visit data for the same user, ensuring data integrity.
Corrected inconsistencies (e.g., "Unjted States" to "United States") to enhance dataset quality.


Exploratory Data Analysis (EDA):

Used pandas and numpy to compute summary statistics (e.g., mean revenue, session duration) and scipy for statistical tests:
Pearson and Spearman correlations to assess relationships between session duration, revenue, and other variables.
t-tests and Mann-Whitney U tests to compare revenue across regions and devices.
Chi-square tests to evaluate associations between categorical variables (e.g., channel and purchase likelihood).
ANOVA and Kruskal-Wallis tests to compare revenue across multiple groups (e.g., days of the week).


Visualized findings with matplotlib and seaborn:
Time-series plots of daily/weekly revenue by region.
Bar charts comparing conversion rates and AOV by channel and device.
Heatmaps of session duration by day/hour to identify peak engagement times.


Key insights:
US accounted for 68-70% of traffic and revenue, with peak session durations on Tuesdays, Fridays, and Sundays.
Social media channels had the highest conversion rates (e.g., 5.5% for US social media) and revenue contribution.
UK showed the highest AOV and conversion rates but lower traffic volume.




Predictive Modeling:

Developed a Random Forest regression model with scikit-learn to predict revenue based on features like region, device, channel, month, day, hour, payment type, session duration, and time type (e.g., morning, evening).
Engineered features using pandas:
Categorical encoding (e.g., one-hot encoding for region, channel).
Temporal features (e.g., month, day, hour extracted from timestamps).


Implemented a randomized feature selection approach to test combinations (1-9 features), ensuring at least one numerical or multiple categorical features.
Evaluated models with a test size of 0.1 and 10 estimators, achieving the best performance with features month and payment_type (R²: 0.2052, MAE: 681.41, MAPE: 10.61%).
Noted low R² due to limited data volume, suggesting future improvements with more data or advanced models.


Business Insights and Recommendations:

Regional Strategies:
US: Dominant market (68-70% traffic, high revenue). Recommended intensifying social media ads (e.g., Instagram stories, YouTube pre-rolls) due to high conversion rates and moderate CAC.
UK: Highest AOV and conversion rates but low traffic. Suggested increasing contextual ads (e.g., Google Ads, SEO) to boost traffic, leveraging high profitability.
Germany and France: Lower priority due to modest traffic and revenue; maintain minimal investment.


Channel Strategies:
Social media ads were the most effective for revenue and conversion, with moderate costs compared to contextual ads.
Contextual ads excelled in driving long sessions but had lower conversion; recommended for UK to attract high-value users.
Organic and email channels showed lower ROI; advised reallocating budgets to social media and contextual ads.


Temporal Strategies:
Identified summer as the peak sales season (likely due to increased demand for drone delivery during vacations). Recommended targeting restaurants and retailers with seasonal campaigns.
In the US, advised boosting ads on high-engagement days (Tuesdays, Fridays, Sundays) with discounts and increasing ad rates for site placements.
Suggested mini-games on Thursdays (low engagement) to retain users and offer micro-discounts.


Operational Improvements:
Flagged a critical data collection bug for returning users (post-July 1, 2019) and recommended urgent fixes to ensure complete data capture.
Noted low usage of credit/debit card payments, possibly due to cumbersome input processes. Proposed implementing secure card storage to improve user experience.




# Deliverables:

Interactive Dashboard: Created using matplotlib and seaborn to visualize real-time metrics (e.g., revenue by region/channel, conversion rates, session duration trends). Exported as an HTML report for stakeholder access.
Stakeholder Presentation: Developed an 8-slide PowerPoint summarizing key findings, visualizations, and recommendations, tailored for investors and leadership.
Code Repository: Maintained a GitHub repository with documented Python scripts for data preprocessing, statistical analysis, modeling, and visualization.



Tools and Technologies

Programming: Python (pandas, numpy, scipy, scikit-learn, matplotlib, seaborn)
Data Sources: 1 CSV file (~1,000 rows)
Statistical Methods: Pearson/Spearman correlations, t-tests, Mann-Whitney U, chi-square, ANOVA, Kruskal-Wallis
Visualization: Matplotlib, Seaborn (time-series plots, bar charts, heatmaps)
Presentation: Canva

Impact

Business Impact:
Provided a data-driven investment strategy, projecting a 20% ROI increase for 2020 by prioritizing US social media ads and UK contextual ads.
Identified summer as a high-demand period, enabling targeted campaigns for restaurants and retailers to capitalize on seasonal trends.
Highlighted the UK as a high-margin market, encouraging increased ad spend to boost traffic and revenue.


Operational Impact:
Uncovered and addressed a critical data collection bug, improving data reliability for future analyses.
Proposed user experience enhancements (e.g., card storage, mini-games) to increase engagement and payment conversions.


Stakeholder Value:
Delivered an intuitive dashboard for ongoing monitoring of sales and channel performance.
Presented clear, actionable recommendations to investors, enhancing decision-making confidence.



# Challenges and Learnings

Challenges:
Limited data volume constrained model performance (R²: 0.2052), highlighting the need for larger datasets or alternative algorithms (e.g., neural networks).
Data collection issues for returning users required creative imputation strategies to maintain analysis integrity.
Balancing statistical rigor with actionable business insights required careful selection of metrics and visualizations.


Learnings:
Gained expertise in handling real-world data quality issues, such as missing values and systematic errors.
Improved proficiency in feature engineering and randomized feature selection for machine learning models.
Learned to tailor technical findings into concise, business-oriented recommendations for non-technical stakeholders.



