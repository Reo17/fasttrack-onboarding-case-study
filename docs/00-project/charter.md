# Project Charter: FastTrack Digital Onboarding
Version 0.1 | Status: Draft | Author: Debesh Shankhi | Updated: 2026-10-23
Change log: 0.1 initial draft

## 1. Background
Harbourline Credit Union is a member-owned financial cooperative based in the South Island, with about 85,000 members, 14 branches, and 420 staff. As a financial institution, it must comply with the AML/CFT Act 2009 and the Privacy Act 2020. The board's 2-year strategy is to grow under-35 membership by 20%. Prospective members currently apply through a web form that arrives as a PDF in a shared inbox, an Onboarding Officer re-keys the details into an Excel tracker and requests proof of identity and address by email. The Compliance team then checks each applicant manually against watchlists on a vendor portal, and an officer re-keys the approved details into the core banking system, which imports new accounts in a nightly batch. Younger customers increasingly expect to open an account from their phone within minutes, as digital-first banks already allow, which puts the board's growth target at risk.

## 2. Problem statement
The problem of a manual email-driven onboarding process affects new applicants, the Onboarding Operations team, and the Compliance team, the impact of which is a 9-business day median wait time to open an account, 34% of applicants abandoning before they finish, and 52 minutes of staff effort per application. A successful solution would let most eligible applicants open an account within the same day they apply, with far less manual effort required from the team and no reduction in AML/CFT compliance. 

## 3. Objectives

| ID | Objective | Baseline | Target | By when | Measured by | Owner |
| --- | --- | --- | --- | --- | --- | --- |
| OBJ-01 | Reduce median onboarding lead time | 9 business days | 1 business day or less | 12 months after go-live | Application and account-opened timestamps | Head of Member Experience |
| OBJ-02 | Reduce onboarding abandonment rate | 34% | 15% or less | 12 months after go-live | Application status records | Head of Member Experience |
| OBJ-03 | Reduce staff touch time per application | 52 min | 12 min or less | 12 months after go-live | Timed sample of 50 applications, before and after | Onboarding Ops Team Lead |
| OBJ-04 | Reduce applications needing manual AML review | 100% | 15% or less | 6 months after go-live | Screening outcomes by application | AML/CFT Compliance Officer |
| OBJ-05 | Maintain full AML/CFT screening coverage and accuracy | 100% screened before account opening | 100% screened; zero true matches missed in monthly QA sample; zero adverse audit findings | Ongoing from go-live | Screening logs, monthly QA review, annual AML/CFT audit | AML/CFT Compliance Officer |

**Metric definitions**

- **Lead time:** business days from application submitted to account number issued in core banking.
- **Abandonment:** applications started with no account opened within 30 days, excluding declined applications.
- **Touch time:** active staff minutes spent on one application, averaged across a timed sample.
- **Manual review rate:** percentage of applications where a compliance officer must make the decision.


## 4. Scope
**In Scope (Phase 1)**
- Personal account opening for individuals over 18 who are NZ residents
- Two channels: online (web and mobile browser), and staff-assisted on a tablet in local branch
- Identity verification of the applicant during the application
- Requesting and collecting missing documents from the applicant
- Risk-based AML/CFT screening, with manual compliance review only for potential matches
- Account creation in the core banking system without manual re-keying
- Email and SMS notifications to the applicant at key status changes
- An audit trail of every check and decision, retained for 5 years

**Out of Scope**
- Business and trust Accounts (Phase 2: it's a complex check to verify who owns and controls an entity)
- Joint Accounts (Phase 2: requires two identity checks, and more complex rules for operating the account)
- Applicants under 18 (Phase 2: require guardian consent and different identity documents)
- Non-residents and applicants without NZ address history (Phase 2: need different documents and enhanced checks)
- Credit products such as loans and credit cards (Separate project: lending carries its own legal obligations and does not directly drive membership growth)
- Re-verifying or migrating existing member's records (Phase 2: only once the new process has proven reliable)
- Replacing the core banking system (Separate project: See constraint C-01).
  
## 5. Key stakeholders
| Stakeholder | Role in project | Stated Goal |
| --- | --- | --- |
| Chief Operating Officer | Sponsor | Lower cost per new member |
| Head of Member Experience | Product Owner | Same-day account opening on mobile |
| AML/CFT Compliance Officer | Approver, veto power | Zero regulatory findings |
| | | |
## 6. Constraints           (C-01..)
| ID | Constraint | Type | Source | Impact on the solution |
| --- | --- | --- | --- | --- |
| C-01 | No changes to the core banking system, CRM and member email/SMS gateway. | Technical | Core Baking Platform Lead (IT)) | Changes in the system will hamper current member's experiences and nightly batch requests might be affected. |
| C-02 | No real-time calls to the core banking system between 01:00 and 04:00 (nightly batch window) | Technical/Operational | Core Banking Platform Lead; IT operations policy | Account-creation requests during this window must be queued and processed after 04:00 |
| C-03 | New solution must comply with the AML/CFT regulations | Regulatory/Legal | AML/CFT Compliance Officer | There must be a measure to maintain compliance even when the automatic screening fails. |
| C-04 | Thre must be an audit trail of every check and decision that should be retained for 5 years | Policy | Internal Audit | System must be capable to keep records of audit for explainability |
| C-05 | Must be completed before the new AGM | Time | Chief Operating Officer | Project should be manageable enough to finish before the new AGM to show results to the board members |


## 7. Assumptions           (A-01..A-08 minimum)
## 8. Top 3 risks           (risk, impact, mitigation)
## 9. Approval              (sponsor, date: blank for now)
