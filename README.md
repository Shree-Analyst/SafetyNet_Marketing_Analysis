# Project Background
Founded in 2016, Safety Net is a health insurance provider serving thousands of customers in the US. It launched new marketing campaign categories in 2019 with customers able to sign up to one of 4 insurance plans. It recently hired a new data team and aims to use analytics to determine next year's marketing budget allocation.

The data team's focus is on building a dynamic dashboard to allow the marketing team to self-serve insights, and on analysing marketing campaign performance to form recommendations regarding improving resource allocation to meet the following goals:
- Increase brand awareness
- Generate new signups.

ERD of the dataset can be found [here](link).

# Executive Summary

For each campaign, we evaluate the following **North Star Metrics:**

- **Click-Through-Rate (CTR)** - % of people who click on a link after a campaign seen.
- **Signup Rate**  - % of people who sign up to a plan after clicking on a link.
- **Cost per Signup (CPS)** - amount in US$ it takes to generate a new signup.

### Overview of Findings

Dashboard Screenshot

Safety Net's overall **CTR was 9.39%, Signup Rate was 1.92%, and CPS was $3.68**, all of which were in line with industry trends.

There were statistically significant differences in campaign performance: **Health For All & Compare Health Coverage generated signups & increased brand awareness** as they had high CTR & Signup Rates (25% & 8.2%; 14% & 3% respectively). On the other hand, **Golden Years Security and #InsureYourHealth failed to generate signups or increase brand awareness** as they had low CTR & Signup Rates (1% & 0.4%; 8% & 0.4% respectively). We recommend to **reallocate budget** from these poorly performing campaigns to the best-performing ones to **boost overall CTR by 17% and Signup Rate by 13%**.

The **Customer Testimonial campaign type drove a rise (early 2021) and a sharp fall (mid-2022) in new signups within the Compare Health Coverage campaign category at a low CPS of $1.8**. We recommend to **extend this campaign type to other high-performing campaigns** like Health For All, #CoverageMatters, and #HealthyLiving to **efficiently generate economical signups**.

# Insights Deep Dive
### Campaign Performance:

Campaign cost scatterplot

Health For All was our outright best performing campaign with a high CTR (25%) and a high Signup Rate (8.2%). Based on statistically significant differences in CTR & Signup Rates, we can separate campaigns into 4 performance  categories:
- Increase awareness & generate signups - Health For All & Compare Health Coverage had a high CTR (25% & 14% respectively) and a high Signup Rate (8.2% & 3% respectively).
- Generate Signups - #CoverageMatters, #HealthyLiving, and Tailored Health Plans had high Signup Rates (2.8%, 2.8%, 1.2% respectively) despite low CTR (10%, 10%, 7% respectively).
- Increase Awareness - Benefit Updates, Summer Wellness Tips, Affordable Plans, and Preventive Care News had high CTRs (22%, 18%, 13%, 12% respectively) despite low Signup Rates (0.1% - 0.5%).
- Neither increase awareness nor generate signups - #InsureYourHealth and Golden Years Security had low CTR (8% & 1% respectively) and low Signup Rate (0.4% each).

3 campaigns (Health For All, #CoverageMatters, and #HealthyLiving) generate 83% of all signups. Their total budget allocation was $13k, whereas $11k was allocated to the 2 wost performing campaigns (Golden Years Security & #InsureYourHealth). This suggests that the former 3 are effective in generating signups, whereas the latter 2 are ineffective despite high resource allocation.


### Signup Trends in Compare Health Coverage:

CHC highlighted graph | CHC type graph

Most campaigns showed a similar trend in terms of new monthly signups:
- Sharp rise with a peak in April 2020, driven by the onset of the Covid-19 pandemic
- Steady decline since then until 2023, falling to pre-pandemic levels.

The Compare Health Coverage campaign, by contrast, peaked in early-2021 with a sharp fall in mid-2022. This was driven by Customer Testimonial type campaigns. New monthly signups from this campaign type within Compare Health Coverage also peaked in early-2021 and fell sharply in mid-2022. Overall, this campaign type had a high CTR (31%) and a high Signup Rate (3.5%).

At $10k spent, Compare Health Coverage is our most expensive campaign. However, Customer Testimonial type campaigns convert economical customers at a low CPS of $1.8, indicating that investment in this type of campaign pays off in generating new signups.

Other campaign categories were linked to specific campaign types (eg., #CoverageMatters category with Product Promotion type campaigns) which requires further investigation with the marketing team.

### Plan & State-wise Performance:

* **New Jersey accounts for 50% of customers.** 8.2k out of 16.4k customers were from New Jersey. A further 1.3k were from neighbouring New York, indicating that 58% of customers hail from these states alone.
  
* **Underperformance of platinum & bronze plans.** Only 12 customers signed up to the platinmum plan, at a high CPS of $491, indicating poor performance of this plan. The bronze plan also generated few signups (591) at a high CPS of $24.


# Recommendations:

Based on the insights and findings above, we would recommend the marketing team to consider the following: 

- $11k allocated to poorly performing campaigns neither increases awareness nor generates signups. **Reallocating these resources to Health For All & Compare Health Coverage can generate a 17% increase in CTR & 13% increase in Signup Rate.**
- Customer Testimonial type campaigns drove peak & fall in Compare Health Coverage. **Expand this campaign type to Health For All, #CoverageMatters, and #Healthy Living to efficiently generate more economical signups.**
- Presence of various campaign category-campaign type pairs such as Compare Health Coverage-Customer Testimonials and #CoverageMatters-Product Promotion was noted. **Further examine category-type pairs to surface insights on attractive copies that increase awareness & generate signups.**
- High CPS & few customers sign up to Platinum & Bronze plans. **We recommend the sales team to investigate the bronze plan's offering and consider eliminating the platinum plan.**
- The Family Coverage Plan campaign did not receive any clicks, hampering analysis. **We recommend the data engineering team to investigate this issue to strengthen future analysis.**

# Caveats & Next Steps:
Find a copy of the entire presentation used [here](link).

To improve analysis, we recommend the following:
- **Address Data Quality Issues:** Family Coverage Plan had no data on clicks. 49 (0.3%) customer signups were not linked to any campaign. Combining data from separate tables creates nulls in new dimensions.
- **Add Dimensions to Improve Analysis:** Adding campaign start & end dates allows establishing a link of campaign performance with spend over time. Adding First Touch allows linking signups to marketing channel performance. Adding customer claims helps to explore links between campaign types and claim amount with categories.
- **Explore Dashboard for Self-Serve Insights:**
Uncover specific insights & visualise trends using Tableau dashboard [here](link).
