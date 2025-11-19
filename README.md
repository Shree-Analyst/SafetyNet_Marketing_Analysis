# Project Background
Founded in 2016, Safety Net is a health insurance provider serving thousands of customers in the US. It launched new marketing campaigns in 2019 with customers able to sign up to one of 4 insurance plans. It recently hired a new data team and aims to use analytics to determine next year's marketing budget allocation.

The data team's focus is on building a dynamic dashboard to allow the marketing team to self-serve insights, and on **analysing marketing campaign performance to improve resource allocation** aimed at meeting the following goals:
- Increase brand awareness
- Generate new signups.

For each campaign, we evaluate the following **North Star Metrics:**

- **Click-Through-Rate (CTR)** - % of people who click on a link after seeing a campaign.
- **Signup Rate**  - % of people who sign up to a plan after clicking on a link.
- **Cost per Signup (CPS)** - amount in US$ it takes to convert a customer.

ERD of the dataset can be found [here](https://raw.githubusercontent.com/Shree-Analyst/SafetyNet_Marketing_Analysis/main/ERD.png).

# Executive Summary

![Dashboard](https://raw.githubusercontent.com/Shree-Analyst/SafetyNet_Marketing_Analysis/edit/Visualisations/Dashboard%20Top.png)

Safety Net's **CTR was 9.39%, Signup Rate 1.92%, and CPS $3.68**, falling in line with industry benchmarks.

### Insights & Recommendations

- **4 campaigns generated 83% of all signups**: Health For All, Compare Health Coverage, #HealthyLiving, and #CoverageMatters.
- **CTR & Signup Rate split campaigns into 4 performance categories**, based on contribution to increasing brand awareness & generating signups.
- **One-fifth of marketing budget ($11k) was spent on 2 underperforming campaigns** - #InsureYourHealth and Golden Years Security, indicating a core inefficiency of resource allocation.
- **Campaign signup surges linked to campaign types** - Customer Testimonial type campaigns are linked to a surge in monthly signups from Compare Health Coverage campaign.

We recommend Safety Net's Marketing Team to reallocate resources and adjust its marketing strategy based on campaign performance. This would **boost CTR by 17%, Signup Rate by 13%**, and lead to stronger efficiency gains.

# Insights Deep Dive
## Insight 1: High vs Low Performing Campaigns

![Campaign Cost Scatterplot](https://raw.githubusercontent.com/Shree-Analyst/SafetyNet_Marketing_Analysis/main/Visualisations/Scatter%205%20-%20Cost%20(presentation).png)

We can **separate campaigns into 4 performance categories** based on CTR & Signup Rates:
1. High CTR & High Signup Rate to **increase awareness & generate signups** - **Health For All was the outright best-performing campaign** at CTR 25% & Signup Rate 8.2%. Compare Health Coverage followed with CTR 14% & Signup Rate 3%. **Combined, these campaigns cost $14k**.
2. Low CTR & High Signup Rate to **generate signups** - #CoverageMatters (2.8%), #HealthyLiving (2.8%), and Tailored Health Plans (1.2%) generated signups despite low CTR (10%, 10%, 7% respectively). Combined, these campaigns cost $14k.
3. Low Signup Rate & High CTR to **increase awareness** - Benefit Updates (22%), Summer Wellness Tips (18%), Affordable Plans (13%), and Preventive Care News (12%) increased awareness despite low Signup Rate (ranging from 0.1% to 0.5%). Combined, these campaigns cost $17k.
4. Low CTR & Low Signup Rate to **neither increase awareness nor generate signups** - **Golden Years Security was the outright worst-performing campaign** at CTR 1% & Signup Rate 0.4%. #InsureYourHealth was next with CTR 8% & Signup Rate 0.4%. **Combined, these campaigns cost $11k** indicating ineffective results despite high budget allocation. **Marketing budget does not seem to be allocated based on performance.**

Additionally, **4 campaigns from categories 1 & 2 generate 83% of all signups** - Health For All, Compare Health Coverage, #CoverageMatters, and #HealthyLiving.

## Insight 2: Customer Testimonial Surge Drives Compare Health Coverage Signups

<div style="display: flex; justify-content: center; align-items: center; gap: 10px;">
  <img src="https://raw.githubusercontent.com/Shree-Analyst/SafetyNet_Marketing_Analysis/main/Visualisations/Signups-Category%20Line%20-%20CHC%20Highlighted%20(presentation).png" alt="CHC Highlighted Line" width="49%">
  <img src="https://raw.githubusercontent.com/Shree-Analyst/SafetyNet_Marketing_Analysis/main/Visualisations/CHC%20Time%20Series%20(presentation).png" alt="CHC Type Line" width="49%">
</div>

**Most campaigns showed a similar trend** in terms of new monthly signups:
- Sharp rise with a **peak in April 2020**, driven by the onset of the Covid-19 pandemic
- **Steady decline since then until 2023**, falling to pre-pandemic levels.

**Exceptionally, the Compare Health Coverage campaign peaked in early-2021 and fell sharply in mid-2022 driven by Customer Testimonial type campaigns**. Overall, Customer Testimonials had a **high CTR (31%) and a high Signup Rate (3.5%)**. Customers also converted at a a **low CPS of $1.8, indicating a significant return on investment** despite high spend on Compare Health Coverage ($10k).

Other campaign categories were linked to specific campaign types (eg., #CoverageMatters category with Product Promotion type campaigns) which requires further investigation with the marketing team to surface insights on category-type pairs.

## Insight 3: Segmentation

- **2 states make up over half of customers**: **New Jersey** accounts for 50% of customers. 8.2k out of 16.4k customers were from New Jersey. A further 1.3k were from neighbouring **New York**, indicating that 58% of customers hail from these states alone.

## Insight 4: Plan Performance

- **Underperformance of platinum & bronze plans.** Only 12 customers signed up to the platinmum plan, at a high CPS of $491, indicating poor performance. Similarly, the bronze plan also generated few signups (591) at a high CPS of $24.

# Recommendations:

Our insights enable the marketing team to improve resource allocation and adjust marketing strategy for efficiency gains. Based on our findings, we would recommend the following: 

#### Reallocate budget from underperformers:
- $11k allocated to poorly performing Golden Years Security & #InsureYourHealth campaigns neither increases awareness nor generates signups. **Reallocating these resources to Health For All & Compare Health Coverage can boost CTR by 17% and Signup Rate by 13%.**
#### Expand Customer Testimonials to high-performing campaigns:
- With a high CTR, high Signup Rate, and low CPS, specifically for Compare Health Coverage, expanding Customer Testimonials to Health For All, #CoverageMatters, and #Healthy Living will **generate new, economical signups**.
#### Identify campaign-type paris:
- Work with the marketing team to evaluate further campaign-type links such as Compare Health Coverage-Customer Testimonials and #CoverageMatters-Product Promotion to **surface insights on attractive copies that increase awareness & generate signups**.
#### Re-evaluate offering:
- We recommend the product team to examine product offering due to poor performance (high CPS & few signups) of Platinum & Bronze plans. **Consider eliminating the platinum plan** & making improvements to the bronze plan.

# Caveats & Next Steps:

To improve analysis, we recommend the following:
- **Address Data Quality Issues:** Family Coverage Plan had no data on clicks. 49 (0.3%) customer signups were not linked to any campaign. Combining data from separate tables creates nulls in new dimensions. Work with data engineering team to address these issues.
- **Add Dimensions to Improve Analysis:** Adding campaign start & end dates allows establishing a link of campaign performance with spend over time. Adding First Touch allows linking signups to marketing channel performance. Adding customer claims helps to explore links between campaign types and claim amount with categories. Work with marketing team to determine ideal dimensions.
- **Explore Dashboard for Self-Serve Insights:**
Uncover specific insights & visualise trends using Tableau dashboard [here](https://public.tableau.com/app/profile/shreeraj.salunke/viz/SafetyNetDashboard/Dashboard).

# Appendix
Find a copy of the entire presentation used to share findings [here](https://raw.githubusercontent.com/Shree-Analyst/SafetyNet_Marketing_Analysis/main/Presentation.pdf) and a live presentation demo [here](https://www.loom.com/share/7e2b31d1d441467885cd1067f38347a1).

Tools used: Excel, Tableau, Python, VSCode.
