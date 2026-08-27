# Donor-Retention-and-Analysis-Project--Riverstone-Foundation

Riverstone Community Donor Segmentation and Retention Analysis
*Uses synthetic data*

Robert Powell

Data and Tools

Five linked tables;
  • Donors (600 rows) — donor master list
  • Campaigns (18 rows) — fundraising campaigns 2022-2025
  • Donations (4,085 rows) — gift transactions
  • RecurringGiftSchedule (129 rows) — recurring gifts incl. card expiration + status
  • EventRegistrations (572 rows) — event sign-ups

~4,700 records. Built using VLOOKUP, INDEX/MATCH, COUNTIFS/SUMIFS, MINIFS/MAXIFS, pivot tables, conditional formatting, and charts.

Context/Objective

Nonprofits’ donation amount is a common indicator of both financial health and trust. To be set up for success nonprofits must monitor the health of their donation flow as well as individual donors because of their potential impact to the organization. This project segments donors by engagement level, flags at-risk recurring gifts, and identifies where retention efforts should be concentrated.

Methodology

I began by structuring the data from the five tables into Excel tables so formulas could reference the column names directly. This made the 4,700 records easier to digest and manipulate
Built a central donor summary, using one row per donor. I pulled together their identity data like name, donor type, gift officer via VLOOKUP. I then did their giving behavior via COUNTIFS, SUMIFS, and MINIFS/MAXIFS. This allows me to calculate all of these values from the Donations table via formulas
Established a fixed Analysis Date so each calculation stays consistent and reproducible.
Built a recency and segmentation model, using Days Since Last Gift and then classifying donors into Active, Lapsing, or Lapsed categories. Added the “Never Gave” exception to ensure donors who never gave weren’t miscategorized or affected charting.
Pulled in recurring gift status using INDEX/MATCH to the summary table. This connected giving behavior to payment frequency
Built targeted reports via Pivot Tables to answer business questions. This includes the donor segment by type, campaign performance, and segment-level averages for gift frequency and lifetime value
Verified findings against raw data by filtering and sorting individual donor records to confirm patterns. Cross referenced a campaign discrepancy against the EventRegistrations table.
Converted pivot table outputs into static charts using color coding consistent with the segment logic
Built a recurring gift health monitor by using the DATE() function. Flagged recurring gifts as needing outreach if the payment failed or the card was set to expire within a 60 day window. Made sure to exclude already canceled gifts.
Documented findings and recommendations for donor outreach

Key Findings

Active donors are 58% of the total donor base but produce 93% of the revenue. The revenue is more concentrated in engaged donors than the headcount could suggest. Despite only being 42% of the population, lapsed and lapsing donors just give around 7% of lifetime contributions
Active donors average 10.8 lifetime gifts, while Lapsed donors are at 1.7. The donors being lost are one or two time donors who never developed a giving habit, rather than engaged donors who disengaged.
Averages are able to mask outliers, so I filtered the Lapsed segment and sorted by lifetime value to check the top of the list directly. The highest-value donor there gave $1,000, from a single recurring gift that was canceled after one payment cycle. This confirms there’s no major donor quietly churning in this segment. The largest case here reflects a single canceled transaction rather than gradual disengagement. 
Live monitoring check currently identifies 3 recurring gifts with failed payments and 18 cards expiring within the next 60 days; a combined list of 21 donors that gift officers can proactively contact. Payment failures and expiring cards are among the most preventable causes of donor attrition, and this live monitoring turns that risk into an actionable list.

Recommendations

Focus lapsed-donor outreach on relationship development rather than reactivation of a prior giving pattern, since most lapsed donors never became recurring givers in the first place. This illustrates the “second gift” problem as opposed to “winning them back”. The goal should be moving first-time donors to a second gift.
Gift officers should also prioritize the 21 donors flagged by the recurring gift health check for direct outreach before their recurring gifts lapse due to payment issues.

Challenges

The dataset being synthetic showed a lack of the structural messiness of a real CRM. I feel as if I missed out on some real-world data cleaning steps within this project.
The data was generated with realistic but simplified assumptions, which means the findings confirmed expected patterns as opposed to surfacing an unexpected answer. I believe a real dataset would reveal a lot more anomalies worth investigating.
With more time, I would build out a gift officer performance review and compare variables like retention rates and average gift value across each officer. I would have liked to see if donor assignment correlates with outcomes or improves retention for at-risk donors.
Finally, I would have incorporated the EventRegistrations table more directly, like flagging donors who attend events but haven’t donated recently.




 
