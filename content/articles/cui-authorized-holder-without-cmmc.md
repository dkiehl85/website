---
title: "Do CUI Rules Apply to Contractors Without a CMMC or DFARS Clause?"
date: 2026-10-26
draft: false
description: "Why a contractor that receives CUI is an authorized holder under 32 CFR 2002, even with no CMMC clause, and where the FAR CUI rule stands."
topics: ["CUI & CMMC"]
---

A prime contractor for a government agency sends you, a subcontractor, a drawing package marked CUI. The contract has no DFARS 252.204-7012, no CMMC level, and no CUI clause anyone can find. The question that follows is whether the company has any obligation to protect it, or whether CUI is really a DoW and CMMC problem.

The confusion makes sense. For most of the defense industrial base, CUI compliance has meant CMMC for years, and 32 CFR Part 2002 says it applies to executive branch agencies.

## The short answer

In my view, you must protect CUI in accordance with the requirements set forth in NIST SP 800-171. A contractor that lawfully receives CUI is an authorized holder under Part 2002, and the regulation puts its handling duties on authorized holders. NARA probably can't enforce Part 2002 directly against a contractor, which is the strongest point on the other side. But the duty doesn't depend on a CMMC clause, and enforcement usually comes from elsewhere: the contract, the law governing the specific CUI category, or the False Claims Act.

## How Part 2002 reaches contractors

### The scope clause

[Section 2002.1(f)](https://www.law.cornell.edu/cfr/text/32/2002.1) says the part "applies to all executive branch agencies that designate or handle information that meets the standards for CUI." It then says the part doesn't apply directly to non-executive branch entities and reaches them indirectly, through agreements. [Section 2002.4(c)](https://www.law.cornell.edu/cfr/text/32/2002.4) defines agreements and arrangements broadly (contracts, grants, licenses, MOAs, information-sharing agreements), and [2002.16(a)(6)](https://www.law.cornell.edu/cfr/text/32/2002.16) lists what those agreements must require: handling under EO 13556, Part 2002, and the CUI Registry, notice that misuse carries penalties, and reporting of non-compliance to the agency.

If you stop reading there, the contract-only view looks right; however, the analysis shouldn't stop there. 

### Whose obligation is it?

Most of the operative provisions are written to the "authorized holder," which [2002.4(d)](https://www.law.cornell.edu/cfr/text/32/2002.4) defines as "an individual, agency, organization, or group of users that is permitted to designate or handle CUI." If the drafters meant only federal personnel, "agency" would have covered it. "Organization" and "group of users" only add something if they reach outside the executive branch.

Here's what authorized holders have to do:

| Provision | Duty on the authorized holder |
|---|---|
| [32 CFR 2002.14(a)(4)](https://www.law.cornell.edu/cfr/text/32/2002.14) | Comply with the Order, Part 2002, and the CUI Registry; for CUI Specified, also follow the underlying law or policy |
| [32 CFR 2002.14(c)](https://www.law.cornell.edu/cfr/text/32/2002.14) | "take reasonable precautions to guard against unauthorized disclosure of CUI," including controlled environments and at least one physical barrier outside them |
| [32 CFR 2002.16(a)(3)–(4)](https://www.law.cornell.edu/cfr/text/32/2002.16) | Mark CUI before sharing it, and have a reasonable expectation that the recipient is authorized and knows how to handle it |
| [32 CFR 2002.20(a)(7)](https://www.law.cornell.edu/cfr/text/32/2002.20) | Handle qualifying information as CUI even when it isn't marked |

A contractor obtains CUI because an agency shared it for a lawful Government purpose, which 2002.4(bb) defines as including activities the Government authorizes. That contractor is permitted to handle CUI and is an authorized holder. Nothing in 2002.4(d) makes a CUI clause a precondition to that status.

## What the FAR CUI rule is meant to fix

Part 2002 told agencies to include CUI requirements in their agreements, but it never provided a standard way to do so. The DoW wrote its own clause (DFARS 252.204-7012), DHS wrote its own HSAR clauses, and most civilian agencies have relied on one-off contract language or nothing at all. That's how a subcontractor ends up holding a CUI-marked drawing package with no clause telling it what to do.

The FAR CUI rule is the fix the CUI Program has been waiting on since Part 2002 took effect in 2016. It would give every executive branch agency the same clause, which is the government-wide version of the agreement that 2002.1(f) relies on. Under the current proposal:

- Every solicitation and contract would come with a standard CUI form stating whether CUI is involved, which categories, and what safeguarding and reporting apply. Contractors would know before the award, rather than finding out when a marked file shows up.
- NIST SP 800-171 Rev 3 would be the system standard for CUI on contractor systems, with SP 800-172 added for the small set of programs an agency designates.
- Incidents would be reported within 72 hours of discovery, regardless of the agency.
- Primes would have to flow the clause and the form down to every subcontract tier that handles CUI. In the example at the top of this article, the prime would owe both to the sub.

The rule won't reach everything. It applies to FAR-based contracts, so grants, cooperative agreements, and CRADAs stay outside it. It applies going forward, so existing contracts won't pick it up unless they're modified to add it. Contracts solely for COTS items are excepted. For CUI that arrives through any of those routes, you're still relying on the authorized holder analysis above.

### Where it stands

The rule still isn't final. The FAR Council first proposed it on January 15, 2025 (FAR Case 2017-016, 90 FR 4278). On June 23, 2026, it replaced that proposal with [FAR Case 2026-001](https://natlawreview.com/article/rfo-rulemaking-gives-contractors-second-opportunity-comment-far-cui-rule) (91 FR 37550) as part of the Revolutionary FAR Overhaul, moving the CUI provisions into a new FAR Part 40. Comments closed July 23, 2026. The FAR Council was aiming to finalize by the end of 2026 ([Hunton](https://www.hunton.com/government-contracts-intelligence-briefing/far-council-releases-updated-cui-proposed-rule-as-part-of-the-revolutionary-far-overhaul)), and at least one industry tracker now estimates spring 2027. Once final, it's expected to take effect without a phase-in period.

Here's what changed between the two proposals:

| Item | Jan. 2025 proposal | June 2026 re-proposal |
|---|---|---|
| Location | FAR Part 4 | New FAR Part 40, clause 52.240-7 |
| Incident reporting | 8 hours | 72 hours from discovery, with supplemental reports |
| System standard | NIST SP 800-171 | NIST SP 800-171 Rev 3, plus SP 800-172 where an agency specifies |
| Contractor liability for response costs | Included | Removed |
| Contract-level CUI form | Yes | Yes |
| Contracts solely for COTS items | Excepted | Excepted |

Rev 3 is a newer baseline than the one DoW uses. DFARS 252.204-7012 still points to Rev 2, so a company with civilian and defense work may be running two baselines for a while. On the DoW side, [CMMC Phase 2 was suspended](https://www.mcdermottlaw.com/insights/far-council-speeds-up-cui-rules-while-dow-slows-down/) on July 13, 2026, about four months before it was set to start. DFARS 7012, Level 1 and Level 2 self-assessments, and SPRS affirmations remain in effect.

## Where contractors get this wrong

### Forgetting the category's own law

Many CUI Specified categories exist because a statute or regulation already controls the information, and those authorities often bind whoever holds it. Export-controlled technical data is governed by the ITAR, 10 CFR 110/810, and the EAR, regardless of whether a CUI clause exists. Sensitive Security Information is governed by 49 CFR Part 1520, which covers contractors who receive it. UCNI falls under 10 CFR Part 1017, which carries civil penalties. 

A second mistake is treating "strongly encourages" as permission to do nothing. When an agency shares CUI without an agreement, 2002.16(a)(5)(ii) only requires it to tell the recipient that the Government strongly encourages protection, and some contractors read that as optional. But if the company has represented that it protects government information, the False Claims Act becomes the enforcement tool. DOJ's Civil Cyber-Fraud Initiative has been settling cases on that theory since 2021.


## What I'd do with CUI that arrives without a CMMC clause

- [ ] Inventory CUI by where it comes from (contracts, grants, informal exchanges), not by which clause is in the contract.
- [ ] Read the full contract, the agency supplement, and the SOW for CUI terms before deciding there aren't any.
- [ ] Look up each item's CUI Registry category, and for CUI Specified, pull the handling rules from the underlying authority.
- [ ] Apply the 2002.14(c) physical and access precautions to all CUI, not just DoW CUI.
- [ ] Route all CUI into one environment built to NIST SP 800-171, which 2002.14(h)(2) already names as the standard for non-federal systems.
- [ ] Treat unmarked information that looks like CUI as CUI, and get the contracting officer's answer in writing.
- [ ] Before passing CUI to a subcontractor or consultant, confirm they're authorized and able to protect it, and put the handling terms in writing.
- [ ] Check what your proposals, reps, and certs say about protecting government information, and make sure your practice matches.
