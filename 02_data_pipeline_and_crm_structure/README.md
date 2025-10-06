# 🔗 Data Pipeline & CRM Structure

## 1. Objective
Create a clean, connected data ecosystem to ensure accurate reporting and efficient handoffs between GTM teams.

---

## 2. CRM Setup (HubSpot)
| Object | Key Fields | Description |
|---------|-------------|-------------|
| Contacts | Name, Email, Lead Source, Lifecycle Stage, Region | Identifies each lead |
| Companies | Company Name, Domain, Industry, Employee Count | Groups related contacts |
| Deals | Deal Name, Stage, Amount, Close Date | Tracks pipeline |
| Activities | Calls, Emails, Notes | Logs communication |

---

## 3. Data Hygiene Rules
- Standardize lead source values (Website / Demo / Referral / Email Campaign)  
- No duplicate emails or companies  
- Every deal must be linked to a company and contact  
- Weekly data audit to clean incomplete or invalid entries  

---

## 4. Data Enrichment
**Tools:** Apollo, Clearbit, manual research  
**Fields Added:**  
- LinkedIn URL  
- Tech Stack Used  
- Company Size  
- Funding Stage  

---

## 5. Example Schema
| Field | Type | Source | Notes |
|--------|------|--------|-------|
| email | text | Form / Upload | Unique key |
| company_name | text | CRM | Required |
| lead_source | dropdown | Form | Controlled values |
| region | dropdown | Manual / API | Based on country |
| deal_stage | dropdown | CRM | Automated transitions |

---

✅ *Next: [Reporting Dashboard →](./03_reporting_dashboard.md)*
