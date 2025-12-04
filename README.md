# Marketing-Analytics-Case-Study-Promotions-Strategy-Optimisation:
A short Report on the understanding of the Data.
Tide acquires it’s customers using the 3 different types of marketing channels: Affiliates, Partnerships and
Referral.
Describing Datasets:
1. Member’s Data
) These datasets has customer records with member_ID as a Unique column and helps to know channel; wise
member’s revenue.(
File name: Affiliates, partnerships and Referral - Tells about the members we acquired.
Breif Explanation of the columns:
 Member Id: Represents Who they are
 Platform Joining Date: When they joined
 promo_code:It is the code that convinced them to join or offer they used to join.
 Industry class: What kind of business they run which helps us segment our customers (important to
undersdtand they type of audience)
 Active last 7days: This shows Are they still with us? It is our engagement metric this helps to measure
activity
 Revenue 1st 45 days: this data show our ROI. It shows the net revenue Tide earned from this member
in their first 45 days. This directly tells us the initial value of the member.

2. Promotions data:
)Which has promocode datamthat descibes the features, spend, nature of promotional offers).
Files: affiliates_promo_code.csv, partnerships_promo_code.csv, referral_promo_code.csv
Brief Explanation of the columns:
 Promo Code: Unique Promom code to identify the specific promotional offer.Sub Channel: Refers to
where the offer ran, it further breakdown within the main (This is only present for Affiliate channel).
 Promotion Type: It shows the reward type, whether the reward is given as direct cash or non cash
such as some other benefit (like vouchers or free transfers).
 Member Incentive Amount: The money spent to aquire them. It’s the direct cost to the member for
participating in the promotion.
 Minimum Funding Requirement: The lowest amount the member should add or fund in their tide
account to be eligible to get the incentive amount.
 Maximum Funding Days: Number of days within which funding or amount should be added to their
tide account to earn the incentive.
(Minimum Funding Requirement, Maximum Funding Days – Related to members who gets incentive
when they add money in their account).
 Minimum Spending Requirement: The minimum amount the member needs to spend using their Tide
account to be eligible.

 Maximum Spending Months: The maximum number of months allowed for spending to get the
promotion or incentive benefit/am,ount.
(Minimum Spending Requirement, Maximum Spending Months – Ralted to members who gets
incentive when they spend money from their tide account).

Trabsformation of Data:
Data Collation and Preparation
The first step in the analysis was to bring together all the raw data from different sources into one main file a
Master Sheet (also called a “Single Source of Truth”). This was done using Power Query in Excel to merge
and clean the data.
A. Merging Member and Promotion Data
The original data was split across multiple files one with member details, one with transaction records, and
another with promotion information.
Action:
I merged the member data (which included promo codes) with the promotion details table.
Result:
This made it possible to link each member’s revenue (from their first 45 days) to the specific promotion and
marketing channel they came from. In the end, a single, clean Master Sheet was created by combining all
three sources: member data, transaction data, and promo data.
B. Cleaning and Standardizing Data
To make the Pivot Table analysis and marketing reports easier to read and interpret, I cleaned and standardized
several key columns:
1. Promotion Type (promo_type):

The original data had Cash and Non-Cash, and many blank or zero values.
Action: Replaced blanks and zeros with the label “None Promo Type.”
Result: The column now clearly shows three values — Cash, Non-Cash, and None Promo
Type, helping identify members who joined without any specific offer.

2. Activation Status (active_last_7_days):
The original data used numbers: 0 and 1.
Action: Replaced them with clear text labels Active and Non-Active.

Result: Makes the data more understandable when checking member activity rates.

C. Creating Strategic Analysis Columns
Two new columns were added to help with deeper analysis and insights:
1. Incentive Barrier Type:

Action: Created a formula to categorize promotions based on what was required to earn the
incentive (for example, a minimum funding or spending amount).
Result: Formed three groups Fund Barrier, Spend Barrier, and No Barrier.
This helped compare which type of customer action led to the best performance.

2. Channel:

Action: Added this from the promotions table so every member record showed which
marketing channel (e.g., Affiliate, Referral) brought them in.
Result: Allowed ROI comparison across channels, helping identify which ones gave the best
return on marketing spend.
