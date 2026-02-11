# SQL-analysis-E-commerce
##### This project performs an analysis of the Olist Brazilian E-commerce dataset using SQL and Python to drive business intelligence. By evaluating key metrics such as Gross Merchandise Value (GMV),RFM and Average Order Value (AOV). Conclusion & Strategic Recommendations: The analysis reveals that 80% of platform revenue is concentrated in the top 20% of categories (e.g., Health & Beauty, Bed & Bath), yet growth is hindered by significant logistics friction, with delivery delays (Atraso) identified as the primary driver of negative 1-2 star reviews. To enhance Customer Satisfaction and GMV, the company should implement Single-Seller Cross-selling Bundles that pair high-traffic "anchor" products with high-margin accessories, ensuring synchronized shipping. Additionally, optimizing regional fulfillment in high-density hubs is essential to reduce Order Delay Rates and improve overall operational efficiency.
##### Analyze the results of an A/B test conducted on a website to determine whether a new landing page leads to a higher conversion rate compared to the old page. The analysis helps in making a data-driven decision on whether to implement the new design.

# 📌Sample report
### dashboard overview
<img width="1621" height="907" alt="image" src="https://github.com/user-attachments/assets/c34c6acd-7930-454f-be22-e3fd0452fed0" />

#### Sales & Market Presence (Commercial Metrics)
##### Olist is currently in a robust Growth Stage, demonstrating significant upward momentum between 2017 and 2018. By leveraging a diverse catalog of approximately 33,000 unique SKUs, the platform achieved a total revenue of $13.59 million with 113,000 products sold, reflecting healthy inventory turnover. This growth is primarily driven by three core categories: Bed_bath_table, Health_beauty, and Sports_leisure, indicating the platform's strong market position in lifestyle and personal care sectors.
#### Customer Satisfaction & Review Analysis
##### Regarding Customer Satisfaction, the platform maintains a solid Average Rating of 4.10/5.00, though this indicates room for improvement as the business enters its "Maturity" phase. While the foundation of the platform's reputation is built on approximately 57,000 positive 5-star reviews, there is a significant volume of roughly 15,000 "Bad Reviews" (1-2 stars). Text analysis of these negative comments identifies two primary pain points: "Delivery Delay" remains the leading cause of dissatisfaction, where long-tail shipping lateness severely impacts retention despite an overall 12-day average lead time; additionally, "Product Mismatch/Quality" issues—where received goods differ from descriptions or images—highlight critical risks in seller compliance and quality control (QC) that must be addressed to protect long-term Customer Lifetime Value (CLV).

### delivery performance
<img width="1621" height="914" alt="image" src="https://github.com/user-attachments/assets/78e3dc85-b5f0-4b55-9455-f91d9abaf477" />

#### Fulfillment Metrics
##### In terms of logistics and operational efficiency, the platform achieves a Total Lead Time of 11.98 days on average, underpinned by an exceptional Internal Efficiency where the Avg. Processing Time is only 0.52 days. While the platform maintains a strong Reliability record with a 92.13% On-Time Delivery Rate, there remains a 7.87% Late Delivery Rate that requires attention. Notably, a significant gap of 11.88 days exists in Expectation Management (Estimate vs. Actual delivery)

### product detail
<img width="1859" height="1037" alt="image" src="https://github.com/user-attachments/assets/935c53e6-2cdc-4136-899e-80c46ecb2827" />

#### Sales Channels
##### The category analysis reveals that high-rating products are concentrated in standardized segments such as CDs/DVDs/Musicals (4.7), Fashion Children's Clothes (4.5), and various Book categories, suggesting that these items meet or exceed customer expectations with lower logistical risks. 
##### Concurrently, the sales distribution by origin indicates a heavy reliance on Direct Traffic across almost all product categories, which highlights strong brand loyalty and direct user engagement. However, the minimal contribution from channels like Paid Search or Social Media reveals a conservative acquisition strategy, pointing to a significant opportunity to drive future growth through more aggressive external marketing and diversified traffic sources.

# 🛠️ Analysis Methodology
The project showcases advanced SQL techniques applied to real-world business scenarios:
1. Traffic Source & Conversion Optimization
Performance Metrics: Calculated CVR (Conversion Rate) across different marketing channels (e.g., gsearch, bsearch) and campaign types (nonbrand vs. brand).
Bid Optimization: Analyzed conversion data by device type (mobile vs. desktop) to inform strategic bidding decisions.

2. Website Measurement & Funnel Analysis
Landing Page Performance: Compared bounce rates between the original homepage and new custom landing pages.
Conversion Funnels: Built multi-step funnels to identify where users drop off in the journey from home -> products -> cart -> shipping -> billing -> thank_you.

3. Product & User Loyalty Analysis
Product Pathing: Analyzed which products users view most frequently after reaching the /products page.
Cross-Selling: Measured the impact of adding a second product to the cart on overall Average Order Value (AOV).
Repeat Business: Used Self-Joins and Time-Series functions to track user retention and identify the time elapsed between a customer's first and second purchase.

4. Multiple tests were performed to evaluate the difference in conversion rates:
- Z-Test for Proportions: Null Hypothesis ($H_0$): Since p > 0.05, we fail to reject the null hypothesis.
- F-Test (Robustness Check):U sed to compare the variances of the two groups. The result confirmed variance homogeneity, ensuring the groups were comparable.
- Chi-Squared Test of Independence: Tested the relationship between the page version and conversion outcome Result: The p = 0.213 suggests that the conversion is independent of the page version.
- Confidence Interval AnalysisPooled Confidence Interval:Calculated the 95% CI for the difference in conversion rates hat{d} = P_{new} - P_{old}. Result: [-0.0039, 0.0008]. The interval includes zero and is entirely below our Minimum Detectable Effect (MDE) of 0.0035.

# 📝 Conclusion
- Channel Shift: Recommended reallocating budget from low-converting search terms to high-performing nonbrand desktop traffic.
- UX Improvement: Identified specific steps in the billing process with high friction, leading to recommendations for UI/UX redesign.
- Inventory Strategy: Highlighted specific products with high "view-to-purchase" ratios for featured placement.
-  Statistically Insignificant: Both Z-test and Chi-Squared test p-values, indicate no significant difference between the two pages. suggesting the new page might even perform worse than the old one.

  # 📊Recommendations & Improvements
1. Refine Delivery Estimates: With an 11.88-day gap between estimated and actual delivery, the platform is "under-promising and over-delivering" too excessively, or vice versa in late cases. Implement a dynamic ETA (Estimated Time of Arrival) algorithm that factors in regional courier performance to tighten this window. When orders delay, proactively offer discount vouchers or loyalty points to these customers before they churn to protect Customer Lifetime Value (CLV), can help reduce bad-review rate.
2. Sellers Compliance Program: To address "Product Mismatch," implement a mandatory SKU verification process for high-volume sellers. Use the high-performing categories (like Books and CDs) as a benchmark for standardized listing templates to ensure customer expectations align with reality.
3. Since Direct Traffic is already strong, focus on increasing Purchase Frequency. Implement a "Member-Get-Member" (MGM) referral system. Incentivize your loyal "Health & Beauty" customers to act as micro-influencers within their own circles.
4. Check if the traffic is bouncing because the landing page is slow? Or is the "Product Mismatch" issue mentioned in reviews scaring them off? Perform A/B testing specifically on the checkout flow to ensure external traffic isn't hitting a technical bottleneck.

# 💻 Tech Stack
- Tool: Jupyter Notebook / MySQL Workbench
- Language: SQL (MySQL Dialect), Python 3.x
- Libraries: Pandas, NumPy, SciPy, Statsmodels, Math
