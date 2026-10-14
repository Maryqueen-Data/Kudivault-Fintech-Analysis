# Kudivault-Fintech-Analysis
KudiVault is a Nigerian fintech savings app. This Power BI dashboard tracks onboarding drop-off, transaction and fraud risk, and marketing performance, built on cleaned data.

## Tools
- PowerBi
- DAX
- Excel

## The Business Problem
Users start the journey but do not consistently finish it. The deck names seven challenges: low user trust, onboarding drop-off, low first deposits, failed transactions, security concerns, poor retention and weak marketing performance.
The product question was: how do we move users from sign-up to successful saving with confidence? The dashboard had to show where users drop off, where money and trust are at risk, and which marketing spend works.

## What the dashboards solved
The three pages answer one chain of questions: where do users drop off, can they transact safely, and which marketing works. The findings for each page follow.

### KPI Overview
<img width="1194" height="844" alt="Screenshot 2026-10-14 224225" src="https://github.com/user-attachments/assets/ad4fdd97-1632-4bc9-80a9-c1bd9501c679" />

#### Questions it answers
- How many users are active, onboarded and saving?
- Are we hitting our KPI targets?
#### Observations
- MAU is 963, current active users are 904, and 988 users save on a recurring basis.
- KYC completion is 719 users (0.72 against a 0.80 target) and bank linking is 93 users (0.09 against 0.80), so bank linking is the biggest gap.
- The total 30-day savings balance is ₦2.37M and there were 9.22K successful transactions.
- MAU (0.96 against 0.70) and successful transactions (0.89 against 0.50) are above target.
#### Recommendations
- Make bank linking mandatory with guided onboarding.
- Run a KYC push over Push, Email and SMS to close the 8-point gap.

### Transaction and Security
<img width="1164" height="788" alt="image" src="https://github.com/user-attachments/assets/dda156ae-0fd2-4cef-b8f4-15d657534aa8" />

#### Questions it answers
- Which payment methods fail most?
- Are outlier transactions a risk?
- Do IP mismatch, device switching, failed logins and MFA line up with fraud risk?
#### Observations
- Bank Transfer carries most of the volume (5.7K successful, 0.4K failed), followed by Card (2.3K, 0.2K) and USSD (1.2K, 0.1K).
- The outlier chart shows ₦292.79K against ₦15.79K for normal transactions, so outliers are about 18.5x larger, not 20x. It looks like an average amount, so check the measure.
- Flagged users score 2.03 on device switching against 0.59 for non-flagged users, about 3.4x higher.
- Suspicious activity is 28.81% when the IP mismatches and 9.35% when it matches, about 3x higher.
- Failed logins rise with risk level: Escalated 3.33, Monitored 2.78, Clear 1.34.
- 592 users have MFA and 408 don't, which matches the deck's 59% and 40.8%. 39 flagged users (26 Monitored plus 13 Escalated) have no MFA, which also matches the deck.
- MFA alone doesn't separate flagged from clear users. About 62-64% of Monitored and Escalated users have MFA, against 59% of Clear users.
#### Recommendations
- Investigate Bank Transfer failures first.
- Add review limits and authorization for outlier amounts.
- Use risk-based authentication triggered by IP mismatch, device switching and repeated failed logins, not just MFA.
- Push MFA toward the 70%+ target, starting with the 39 flagged users who lack it.

### Marketing and Retention
<img width="1185" height="801" alt="image" src="https://github.com/user-attachments/assets/fb843be6-c8c5-40f3-865e-15e34e2feb74" />

#### Questions it answers
- Which channels, campaigns and creative themes convert cheapest?
- How are users split by retention bucket?
- Where are users located?
#### Observations
- By channel, Push, Email and SMS cost about ₦0.4K per conversion. TikTok is ₦1.5K, X ₦1.6K and Instagram ₦1.8K.
- By campaign type, Reactivation is cheapest (₦676.74) and Rate Promo is most expensive (₦862.57).
- By creative theme, Save Smarter is cheapest (₦615.89) and Beat Inflation is most expensive (₦928.96).
- Retention buckets split 359 (35.9%), 350 (35%), 285 (28.5%) and 6 (0.6%). The 285 slow-conversion users are the main opportunity.
- 904 users (90.4%) are not churned and 96 (9.6%) are.
- Lagos has 283 users, about 3x Abuja (90). Port Harcourt (86), Benin City (81), Enugu (81) and Ibadan (81) follow closely.
- The location chart adds up to 980 users out of 1,000. The missing 20 (2%) match the "missing location on ~2% of rows" issue, which shows how the data cleaning appears in the dashboard.
#### Recommendations
•	Move budget to Push, Email and SMS, and keep TikTok and X for limited reactivation.
•	Scale Save Smarter and Reactivation messaging, and rework Beat Inflation.
•	Study what the fast converters did and use it to shrink the slow-conversion group.
•	Target the 96 churned users with a reactivation campaign.
•	Test acquisition in the cities close behind Abuja, to see whether Lagos dominance is market size or acquisition.

## Overall recommendations
The data points to one objective: get more users safely through activation, then keep them saving.
- Fix onboarding first. Make KYC a priority (71.9%) and bank linking mandatory (9.3%).
- Make transactions reliable. Success is 87.62% against a target near 95%, with Bank Transfer failing most.
- Secure the journey. Enforce MFA and use risk signals (IP mismatch, device switching, failed logins) to catch fraud.
- Spend where it converts. Move budget to Push, Email and SMS, which cost 4-5x less per conversion than paid social.

