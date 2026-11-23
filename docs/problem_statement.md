# Problem Statement: FlowDesk Churn & Retention Analytics

> **Note:** UpCloud is a fictional company. All data is synthetic and produced by the generator in `data_generator/`.

## 1. Company and product

**UpCloud** is a B2B SaaS workflow and project-management tool for small teams (5-50 people), sold mainly in Europe. Customers pay by subscription, billed monthly or annually.

| Plan | Price (per workspace) | Target customer |
|---|---|---|
| Free | €0 | Individuals trying the product |
| Bronze | €25 / month | Small teams |
| Silver | €80 / month | Growing teams needing automation |
| Gold | €150 / month | Larger teams needing admin and security features |
| Annual Bronze | €300 / annual | Annual plan for small teams |
| Annual Silver | €960 / annual | Annual plan for larger teams |
| Annual Gold | €1800 / annual | Annual plan for teams needing more control |

Customers are acquired through organic search, paid ads, referrals, and partnerships.

## 2. The problem

Over the last six months, UpCloud's monthly logo churn rose from about **3.2% to 5.1%**, and MRR growth has stalled. Leadership has three suspicions but no evidence:

1. Failed card payments are silently cancelling customers.
2. The March price increase on the Silver and Gold plan pushed customers out.
3. A recently scaled paid-ads channel brings low-quality customers who leave quickly.

Today, reporting is done manually in spreadsheets. Teams define "churn" differently, so numbers don't match across departments, and nobody can say which segments are leaving or why.

## 3. Stakeholders

| Stakeholder | Needs |
|---|---|
| CEO | Trusted headline numbers: MRR, churn, growth |
| Head of Growth | Which channels and funnel steps leak customers |
| Head of Customer Success | Which customers are at risk, and early warning signs |
| Finance lead | Reconciled revenue and churn figures |

## 4. Business questions

| # | Question | Decision it informs |
|---|---|---|
| 1 | How has MRR changed each month (new, expansion, contraction, churned)? | Is growth stalled by too few new customers or too many lost ones? |
| 2 | Which segments (plan, channel, tenure, company size) churn the most? | Where to focus retention effort |
| 3 | What does retention look like by signup cohort? | Whether newer cohorts are worse than older ones |
| 4 | What share of churn is involuntary (failed payments) vs voluntary? | Whether to invest in payment recovery |
| 5 | Where does the funnel leak between signup, activation, and paid conversion? | Where to improve onboarding |
| 6 | Which early behaviors (first 30 days) predict retention at 90 days? | What to measure for customer-success alerts |

## 5. Definitions

- **MRR:** monthly recurring revenue; annual plans are divided by 12.
- **Logo churn rate:** customers who cancelled in a month ÷ customers active at the start of that month.
- **Revenue churn rate:** MRR lost to cancellations and downgrades ÷ MRR at the start of the month.
- **Involuntary churn:** cancellation after a failed payment that was not recovered within 14 days.
- **Activated customer:** completed the key actions (created 3 projects and invited 1 teammate) within 14 days of signup.
- **Reactivation:** a customer who cancelled and later returns. The cancellation counts as churn in its month, and the return counts as a reactivation (win-back), not as a new customer.

## 6. Success metrics

**Project (technical):**
- The pipeline runs end to end with one command and passes all data-quality tests.
- Metrics reconcile: MRR bridge and churn totals match between models.
- The analysis recovers the churn drivers planted in the synthetic data.

**Business (illustrative targets):**
- Identify the top three churn drivers, each with an estimated € impact.
- Show a path to reduce monthly logo churn from 5.1% to 4.0% within two quarters.
- Recommend a measurable plan (for example an A/B test) for each driver.

## 7. Deliverables

- An AWS data platform (S3, Glue, Athena, dbt) provisioned with Terraform
- Gold-layer tables for MRR, churn, cohorts, and funnel
- A dashboard and a written business report with recommendations
- Documentation in English and German

## 8. Out of scope

- Real-time or streaming ingestion
- Predictive churn modeling
- Running live pricing or product experiments
- Real customer data or personal data (synthetic only)