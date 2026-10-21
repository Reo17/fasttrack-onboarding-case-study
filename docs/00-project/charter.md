# Project Charter: FastTrack Digital Onboarding
Version 0.1 | Status: Draft | Author: Debesh Shankhi | Updated: 2026-10-20
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


## 4. Scope                 (in / out, bullet lists)
**In Scope**
- Individual Personal Accounts
- NZ Residents
- Online and in-branch tablet channels
- Risk-based AML screening
- Automated account creation

**Out of Scope**
- Business and Trust Accounts (Phase 2, high risk to implement before Individual personal accounts)
- Joint Accounts (Phase 2, multiple people means multiple identity checks, the rules for operating the account are complicated)
- Credit Products (goes way from goal of increasing membership by 20%).
- Migration of Existing Members (Phase 2, high risk to attempt before we can trust the phase 1 results)
- Replacing Core Banking (high effort, and cannot be fit into the schedule, should be a separate project).
  
## 5. Key stakeholders      (names and roles only; detail is tomorrow)
## 6. Constraints           (C-01..)
## 7. Assumptions           (A-01..A-08 minimum)
## 8. Top 3 risks           (risk, impact, mitigation)
## 9. Approval              (sponsor, date: blank for now)
