# SAP R2R Capstone Project — KashiTech Industries Pvt. Ltd.

> **Academic Capstone Project | KIIT University — School of Computer Engineering**
> B.Tech Computer Science & Engineering | SAP Enterprise Resource Planning |

---

## Overview

This repository contains the complete SAP Capstone Project Report documenting the end-to-end implementation of the **Record-to-Report (R2R)** business process for a fictional mid-sized manufacturing company — **KashiTech Industries Pvt. Ltd.**

The R2R process covers all financial accounting activities from recording transactions to delivering financial statements, implemented using **SAP S/4HANA Finance (FI module with CO integration)**.

---

## Company Profile

| Field | Details |
|-------|---------|
| Company | KashiTech Industries Pvt. Ltd. |
| Industry | Manufacturing — Electronic Components |
| Headquarters | Pune, Maharashtra, India |
| SAP System | SAP S/4HANA 2023 — On-Premise |
| Company Code | NTIL |
| Fiscal Year | April to March (Indian FY) |
| Go-Live Date | April 21, 2025 |

---

## Project Scope

**Module:** SAP FI (Financial Accounting) with CO Integration

**Key Sub-Modules Covered:**
- FI-GL — General Ledger (New G/L with document splitting)
- FI-AP — Accounts Payable
- FI-AR — Accounts Receivable
- FI-AA — Asset Accounting
- CO-CCA — Cost Center Accounting
- CO-PCA — Profit Center Accounting
- CO-PA — Profitability Analysis

---

## R2R Process — 12 Steps

| # | Step | T-Code |
|---|------|--------|
| 1 | Pre-Close Checklist | OB52, MMPV |
| 2 | Intercompany Reconciliation | FB01, F-01 |
| 3 | GR/IR Clearing | MR11, F.19 |
| 4 | Foreign Currency Valuation | FAGL_FC_VAL |
| 5 | Accruals & Provisions | FBD1, F.14, F107 |
| 6 | Fixed Asset Depreciation | AFAB |
| 7 | Cost Allocation (CO) | KSV5, KSU5 |
| 8 | Recurring Entries | FBD1, F.14 |
| 9 | Balance Sheet Reclassification | F.19 |
| 10 | Financial Statement Generation | S_ALR_87012301 |
| 11 | Management Reporting (CO-PA) | KE30, KE5T |
| 12 | Period Close & Balance Carryforward | F.16, FAGLGVTR |

---

## Repository Structure

```
SAP-R2R-KashiTech-Capstone/
│
├── docs/
│   ├── KashiTech_R2R_Final.docx          # Main project report (enhanced)
│   └── KashiTech_R2R_Changes_Report.docx # Document changes log
│
├── images/
│   ├── fig7_ob52_screen.png             # OB52 — Open/Close Posting Periods
│   ├── fig8_mr11_screen.png             # MR11 — GR/IR Account Clearing
│   ├── fig9_afab_screen.png             # AFAB — Depreciation Run
│   ├── fig10_s_alr_87012301_screen.png  # S_ALR_87012301 — Balance Sheet/P&L
│   └── fig11_faglgvtr_screen.png        # FAGLGVTR — Balance Carryforward
│
└── README.md
```

---

## Key Results After SAP Implementation

| KPI | Before SAP | After SAP |
|-----|-----------|-----------|
| Month-End Close Duration | 12–15 business days | 4–5 business days |
| Manual Journal Entries/Month | ~380 | ~65 (83% reduction) |
| Audit Queries (Annual) | 240+ | <40 |
| GR/IR Uncleared Balance | INR 18 Crore | INR <50 Lakhs |
| Intercompany Differences | INR 4.2 Crore | INR <5 Lakhs |
| Finance Headcount for Close | 22 FTEs | 14 FTEs |
| Restatement Incidents (Quarterly) | 6–8 | 0 |

---

## SAP Configuration Highlights

- **Fiscal Year Variant:** V3 (April–March, 12 regular + 4 special periods)
- **Chart of Accounts:** NTCA (8-digit account numbers)
- **Parallel Ledgers:** 0L (Indian GAAP) + 1L (IFRS)
- **Document Splitting:** Enabled by Profit Center and Segment
- **Depreciation Areas:** Area 01 (Indian GAAP), Area 15 (IFRS), Area 20 (IT Act)
- **India Localization:** GST (TAXIN procedure) + TDS withholding tax

---

## Module Integration

```
MM (Procurement)          SD (Sales)
       |                      |
       | GR/IR Posting         | Billing Document
       |                      |
       └──────► FI-GL ◄────────┘
                 | (Universal Journal — ACDOCA)
                 ├──► FI-AP
                 ├──► FI-AR
                 ├──► FI-AA
                 └──► CO ──► CCA / PCA / CO-PA
```

---

## References

- SAP Help Portal — [help.sap.com](https://help.sap.com/docs/SAP_S4HANA_ON-PREM)
- SAP Best Practices — Record-to-Report Scenario J58
- SAP Learning Hub — Module S4F20 (Financial Closing with SAP S/4HANA)
- Krolczyk & Hunting (2019) — *Financial Accounting with SAP S/4HANA*, SAP Press
- ICAI (2024) — Guidance Note on Accounting for GST

---

## Academic Info

| Field | Details |
|-------|---------|
| University | KIIT University, Bhubaneswar |
| School | School of Computer Engineering |
| Course | B.Tech — Computer Science & Engineering |
| Subject | SAP Enterprise Resource Planning (Capstone) |
| Academic Year | 2024–2025 |
| Document Version | 1.0 |

---

*This project is created for academic purposes only. KashiTech Industries Pvt. Ltd. is a fictional company used solely for SAP learning demonstration.*
