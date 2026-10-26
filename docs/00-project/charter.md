# Project Charter: FastTrack Digital Onboarding
Version 0.1 | Status: Draft | Author: Debesh Shankhi | Updated: 2026-10-24
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
| Onboarding Operations Team Lead | Key user, 6 FTE team | Fewer chasing emails |
| Branch Manager (Riccarton) | Secondary user | Walk-in applicants handled on a tablet |
| Core Banking Platform Lead (IT) | System owner | No changes to the core |
| Privacy & Security Officer | Approver | Data minimisation, encrypted ID images |
| Internal Audit | Reviewer | Full audit trail of every decision |
| New member (persona: 24-year old apprentice) | End user | Open an account from a phone in 10 minutes |
| ID verification vendor | External | Sell per-check volume |

## 6. Constraints
| ID | Constraint | Type | Source | Impact on the solution |
| --- | --- | --- | --- | --- |
| C-01 | The core banking system stays in place and cannot be modified; integration must use its exisiting SOAP API and batch import. | Technical | Core Baking Platform Lead (IT)) | Account creation must go through the existing SOAP API. No new fields or custom code should be added in core banking system. |
| C-02 | No real-time calls to the core banking system between 01:00 and 04:00 (nightly batch window) | Technical/Operational | Core Banking Platform Lead; IT operations policy | Account-creation requests during this window must be queued and processed after 04:00 |
| C-03 | Identity verification and AML/CFT screening must be completed before an account in opened. | Regulatory | AML/CFT Act 2009; Harbourline AML/CFT programme | Account creation must be blocked until both checks have passed or a compliance officer has approved the application. |
| C-04 | Customer records (identity documents, verification and screening results) must be kept for at least 5 years. | Regulatory | AML/CFT Act 2009 | Records must be stored durably, retrievable on request, and protected from deletion for 5 years |
| C-05 | Every automated and manual decision must be explainable after the fact. | Policy | Internal Audit | Each decision must be logged with timestamp, actor (system or person), inputs and reason; the log cannot be edited. |
| C-06 | Personal information, including ID images, must be collected only for onboarding, kept secure, and stored in NZ or AU | Regulatory/Policy | Privacy Act 2020; Privacy and Security Officer | ID vendor and document storage must meet data-residency rules; images must be encrypted; only fields needed for onboarding should be collected. |
| C-07 | Phase 1 must be live within 6 months of project approval (board-endorsed, ahead of AGM) | Time | Chief Operating Officer | Phase 1 is limited to the agreed scope; anything that risks the data moves to Phase 2. |

## 7. Assumptions
| ID | Assumption | Category | Impact if wrong | Owner | How to validate | Validate by | Status |
| --- | --- | --- | --- | --- | --- | --- | --- |
| A-01 | The ID verification vendor can verify NZ driver licences, not only passports | Vendor | High: applicants with only a driver licence (many under-35s) could not apply | Head of Member Experience | Obtain the vendor's supported-documents list in writing | Before vendor selection | Open |
| A-02 | At least 85% of applicants return no watchlist match | Volume / Compliance | High: OBJ-04 target of 15% manual review is unachievable | AML/CFT Compliance Officer | Run a sample of 200 anonymised past applicants through the screening vendor's trial and count matches | Before design sign-off | Open |
| A-03 | The core banking SOAP API can create accounts outside the batch window | Technical | High: account creation needs a workaround, possibly a queue for all requests | Core Banking Platform Lead | Create 10 test accounts via the SOAP API in the test environment during and after the 01:00-04:00 window | Before design sign-off | Open |
| A-04 | Phase 1 can be delivered within 6 months of approval (illustrative figure agreed with the COO) | Delivery | High: scope must be cut or the date moves | Chief Operating Officer | Build a bottom-up estimate of Phase 1 tasks and review it with the delivery team | Before project approval | Open |
| A-05 | The ID vendor stores images only in NZ or Australia | Vendor / Privacy | High: breaks C-06, so the vendor must be replaced | Privacy & Security Officer | Obtain written confirmation of storage region from the vendor's contract or data processing agreement | Before vendor selection | Open |
| A-06 | The applicants have a suitable phone with a working camera to scan the documents | Technical | High: Need additional option to upload a pre-captured photo of the document | IT Lead | Run a member survey to validate if current members have access to phones with cameras | Before technical implementation | Open |
| A-07 | The baseline data form Excel tracker is trustworthy and accurate | Technical | High: Leads to misinterpret project progress and misleading project reports. | IT Lead | Cross-check data findings with stakeholders to ensure reliability | Before charter sign-off | Open |
| A-08 | Compliance team accepts risk-based screening instead of reviewing everyone | Compliance | High: Higher likelihood of non-compliance with regulations, leading to potential fines and legal scrutiny, further damaging reputation. | AML/CFT Compliance Officer | Review the screening workflow in AML/CFT and confirm that compliance has approved the risk-based methodology in committee minutes | Before project approval | Open |

## 8. Top 3 risks           (risk, impact, mitigation)
| ID | Risk | Category | Impact | Owner | Mitigation |
| --- | --- | --- | --- | --- | --- |
| R-01 |  |  |  |  |  |
| R-02 |  |  |  |  |  |
| R-03 |  |  |  |  |  |

## 9. Approval              (sponsor, date: blank for now)
