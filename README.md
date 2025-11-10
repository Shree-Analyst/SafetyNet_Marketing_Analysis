# Project Background
Founded in 2016, Safety Net is a health insurance provider serving thousands of customers in the US. It launched new marketing campaigns in 2019 with customers able to sign up to one of 4 insurance plans. It recently hired a new data team and aims to use analytics to determine next year's marketing budget allocation.

The data team's focus is on building a dynamic dashboard to allow the marketing team to self-serve insights, and on **analysing marketing campaign performance to improve resource allocation** aimed at meeting the following goals:
- Increase brand awareness
- Generate new signups.

ERD of the dataset can be found [here](https://github.com/Shree-Analyst/Health_Insurance_Analysis/blob/main/ERD.png).

# Executive Summary

For each campaign, we evaluate the following **North Star Metrics:**

- **Click-Through-Rate (CTR)** - % of people who click on a link after seeing a campaign.
- **Signup Rate**  - % of people who sign up to a plan after clicking on a link.
- **Cost per Signup (CPS)** - amount in US$ it takes to convert a customer.

### Tableau Dashboard

![Dashboard](https://github.com/Shree-Analyst/Health_Insurance_Analysis/blob/main/Visualisations/Dashboard.png)

Safety Net's overall **CTR was 9.39%, Signup Rate 1.92%, and CPS $3.68**, all of which were in line with industry trends.

There were statistically significant differences in campaign performance: **Health For All & Compare Health Coverage generated signups & increased brand awareness** as they had high CTR & Signup Rates (25% & 8.2%; 14% & 3% respectively). On the other hand, **Golden Years Security and #InsureYourHealth failed to generate signups or increase brand awareness** as they had low CTR & Signup Rates (1% & 0.4%; 8% & 0.4% respectively). We recommend to **reallocate budget** from these poorly performing campaigns to the best-performing ones to **boost overall CTR by 17% and Signup Rate by 13%**.

**Customer Testimonials drove a peak (early 2021) and a sharp fall (mid-2022) in monthly signups for the Compare Health Coverage campaign at a low CPS of $1.8**. We recommend to **extend this campaign type to other high-performing campaigns:** Health For All, #CoverageMatters, and #HealthyLiving to efficiently generate economical signups.

# Insights Deep Dive
### Significant Differences in Campaign Performance & Resource Use Effectiveness:

![Campaign Cost Scatterplot](https://github.com/Shree-Analyst/Health_Insurance_Analysis/blob/main/Visualisations/Scatter%205%20-%20Cost%20(presentation).png)

We can **separate campaigns into 4 performance categories** based on CTR & Signup Rates:
1. High CTR & High Signup Rate to **increase awareness & generate signups** - **Health For All was the outright best-performing campaign** at CTR 25% & Signup Rate 8.2%. Compare Health Coverage followed with CTR 14% & Signup Rate 3%. **Combined, these campaigns cost $14k**.
2. Low CTR but High Signup Rate to **generate signups** - #CoverageMatters (2.8%), #HealthyLiving (2.8%), and Tailored Health Plans (1.2%) generated signups despite low CTR (10%, 10%, 7% respectively). Combined, these campaigns cost $14k.
3. Low Signup Rate but High CTR to **increase awareness** - Benefit Updates (22%), Summer Wellness Tips (18%), Affordable Plans (13%), and Preventive Care News (12%) increased awareness despite low Signup Rate (0.1% - 0.5%). Combined, these campaigns cost $17k.
4. Low CTR & Low Signup Rate to **neither increase awareness nor generate signups** - **Golden Years Security was the outright worst-performing campaign** at CTR 1% & Signup Rate 0.4%. #InsureYourHealth was next with CTR 8% & Signup Rate 0.4%. **Combined, these campaigns cost $11k** indicating ineffective results despite high budget allocation.

**4 campaigns** (Health For All, Compare Health Coverage, #CoverageMatters, and #HealthyLiving) generate **83% of all signups**. Marketing budget does not seem to be allocated based on performance.

### Campaign Types Can Drive Trends in Campaign Category Performance:

<div style="display: flex; justify-content: center; align-items: center; gap: 10px;">
  <img src="https://github.com/Shree-Analyst/Health_Insurance_Analysis/blob/main/Visualisations/Signups-Category%20Line%20-%20CHC%20Highlighted%20(presentation).png" alt="CHC Highlighted Line" width="49%">
  <img src="https://github.com/Shree-Analyst/Health_Insurance_Analysis/blob/main/Visualisations/CHC%20Time%20Series%20(presentation).png" alt="CHC Type Line" width="49%">
</div>

**Most campaigns showed a similar trend** in terms of new monthly signups:
- Sharp rise with a **peak in April 2020**, driven by the onset of the Covid-19 pandemic
- **Steady decline since then until 2023**, falling to pre-pandemic levels.

**Exceptionally, the Compare Health Coverage campaign peaked in early-2021 and fell sharply in mid-2022. Customer Testimonials drove this trend**: new monthly signups from this type of campaign for Compare Health Coverage also peaked in early-2021 and fell sharply in mid-2022. Overall, Customer Testimonials had a **high CTR (31%) and a high Signup Rate (3.5%)**. Despite $10k overall spend on Compare Health Coverage, Customer Testimonials converted customers at a **low CPS of $1.8. This indicates a significant return on investment**.

Other campaign categories were linked to specific campaign types (eg., #CoverageMatters category with Product Promotion type campaigns) which requires further investigation with the marketing team to surface insights on category-type pairs.

### Segmentation & Plan Performance

- **2 states make up over half of customers**: **New Jersey** accounts for 50% of customers. 8.2k out of 16.4k customers were from New Jersey. A further 1.3k were from neighbouring **New York**, indicating that 58% of customers hail from these states alone.
- **Underperformance of platinum & bronze plans.** Only 12 customers signed up to the platinmum plan, at a high CPS of $491, indicating poor performance. Similarly, the bronze plan also generated few signups (591) at a high CPS of $24.

# Recommendations:

Based on the insights and findings above, we would recommend the marketing team to consider the following: 

- $11k allocated to poorly performing Golden Years Security & #InsureYourHealth campaigns neither increases awareness nor generates signups. **Reallocating these resources to Health For All & Compare Health Coverage can boost CTR by 17% and Signup Rate by 13%.**
- Customer Testimonials have a high CTR, high Signup Rate, and low CPS, specifically for Compare Health Coverage. **Expand Customer Testimonials to Health For All, #CoverageMatters, and #Healthy Living** to efficiently generate more economical signups.
- Work with the marketing team to **evaluate further campaign-type links such as Compare Health Coverage-Customer Testimonials and #CoverageMatters-Product Promotion** to surface insights on attractive copies that increase awareness & generate signups.
- Re-evaluate product offering due to High CPS & few signups to Platinum & Bronze plans. **Consider eliminating the platinum plan** & making improvements to the bronze plan.

# Caveats & Next Steps:
Find a copy of the entire presentation used to share findings [here](https://github.com/Shree-Analyst/Health_Insurance_Analysis/blob/main/Presentation.pdf).

To improve analysis, we recommend the following:
- **Address Data Quality Issues:** Family Coverage Plan had no data on clicks. 49 (0.3%) customer signups were not linked to any campaign. Combining data from separate tables creates nulls in new dimensions. Work with data engineering team to address these issues.
- **Add Dimensions to Improve Analysis:** Adding campaign start & end dates allows establishing a link of campaign performance with spend over time. Adding First Touch allows linking signups to marketing channel performance. Adding customer claims helps to explore links between campaign types and claim amount with categories. Work with marketing team to determine ideal dimensions.
- **Explore Dashboard for Self-Serve Insights:**
Uncover specific insights & visualise trends using Tableau dashboard [here](link).
