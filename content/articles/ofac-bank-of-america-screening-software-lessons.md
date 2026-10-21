---
title: "When software does the compliance job: lessons from the Bank of America OFAC settlement"
date: 2026-10-21
draft: false
description: "OFAC traced 475 Bank of America violations to screening logic, late list updates, and an auto-release rule. A checklist for testing any compliance software."
topics: ["Export Controls"]
---

On October 13, OFAC announced an $11,662,930 settlement with Bank of America, N.A. for 475 apparent sanctions violations between September 2021 and April 2025. 

The OFAC release is the one I'd send to anyone outside banking. Nearly every violation traces back to screening software that was set up wrong or was fed stale data, then trusted without anyone checking. If you run restricted-party screening for export controls, a DLP rule that keeps CUI out of personal email, an automated marking rule, or a workflow that routes license determinations, you've entrusted software with a regulatory duty. The regulator will hold you responsible for what it does.

## The short version

Screening tools rarely fail loudly. At Bank of America, the failures were a priority setting, two late watchlist updates, a rule meant to cut false positives, and analysts who cleared real hits. None of them would have shown up on a dashboard as an outage, and together they let $14.8 million move to or through blocked parties.

OFAC's position is blunt: Each organization remains responsible for its own compliance regardless of whether it relies upon third-party providers. If software performs a regulatory duty for you, confirming that it's running isn't enough. You have to test what it actually does.

## What went wrong at Bank of America

The enforcement release describes four problems. 

### Exact matches went to the low-priority queue

A design flaw in the alert prioritization logic sent alerts on customers whose name *and* date of birth exactly matched a blocked person to the low- or medium-priority queue. Those are the strongest hits a screening system can produce, and they waited. Three designated individuals completed 31 transactions ($56,258) between September 2021 and February 2024. The fix landed six months after the bank first identified the issue.

### The watchlist was out of date twice

From May 24 to June 28, 2023, a vendor error caused the bank's watchlist to fail to reflect changes to the SDN List. Six payments ($100,828) went to newly designated entities. The bank learned about it in July, after another U.S. bank blocked one of the payments downstream.

In February 2025, the problem was on the bank's side. A technical issue kept a vendor update with the previous day's designations from loading. Twenty-six transactions ($146,543) went to a newly designated ship management company before the update went live almost a week later.

### Analysts cleared real hits

Between February 2022 and March 2025, the bank processed 403 transactions ($14,340,100) through 35 blocked banks. Those banks stayed in the routing directory its payment engine used, and the bank knew that from March 2022. Some payments went out before the filter caught up with a new designation. Analysts approved others, treating them as false positives, and the rule described next automatically released others.

### A rule turned old decisions into standing exemptions

The bank had an "alert suppression rule." If a new alert matched the criteria of one that an analyst had already cleared as a false positive, the payment could be released without anyone looking at it. One person's judgment call on one day quietly became policy.

OFAC found the conduct reckless, noted it had already sent the bank multiple cautionary letters about similar conduct, and gave no reduction from the base penalty.

## The same mistakes show up outside banks

Each of these has an export-control equivalent.

**"Running" gets mistaken for "working."** Screening dashboards report volumes and clearance times. They almost never show whether a name you know is listed would actually alert. If you've never fed your tool a known bad name, you don't know that it catches one.

**The vendor's list is assumed to be current.** OFAC's 2019 *Framework for OFAC Compliance Commitments* already listed "sanctions screening software or filter faults" as a recurring root cause, including tools that weren't updated with SDN changes. Entity List additions are published in the Federal Register and often take effect right away. Ask your vendor how fast updates load, get the answer in writing, and check it yourself the day after a designation.

**Rules get tuned for the reviewer's workload.** False positives are the universal complaint about screening tools, so rules get added to cut them: raise the match threshold, suppress repeat alerts, and auto-clear names that were cleared before. Each one trades risk for convenience. Any rule that clears an alert without a person looking at it is a compliance decision, and it should be approved and documented like one.

**Volume trains people to click "clear."** When nearly every alert is a false positive, reviewers learn to dismiss them. An analyst who has cleared 400 hits on a common surname will clear the 401st, even when it's real.

**The first lookback is too narrow.** Bank of America's initial review missed the full scope, which only came out after OFAC issued an administrative subpoena in January 2025. When you find a gap, assume it's wider than your first query shows.

## Borrow a standard that already exists

The most specific rule I know of comes from New York's Department of Financial Services. Part 504 (3 NYCRR 504.3) requires covered institutions to run "end-to-end, pre- and post-implementation testing" of their sanctions filtering program. That includes data matching, whether "the OFAC sanctions list and threshold settings map to the risks of the institution," the matching logic, model validation, and data input and program output. It also requires validating the data that feeds the system, governance over changes, and a vendor selection process.

OFAC's Framework puts it more briefly: select and calibrate technology for your risk profile, and routinely test it to ensure it works.

Part 504 only binds DFS-regulated institutions. You don't need to be one to use it as a test plan.

## Checklist: testing software that does a compliance job

This works for restricted party screening, sanctions filters, and any automated rule that makes or skips a regulatory decision.

**Before you rely on it**

- [ ] Write down the regulatory duty the tool performs and the person who owns the result. "The vendor" is not an answer; it must be someone within your organization.
- [ ] Map every data source that should feed it (customer master, vendor master, shipping, payments) and confirm each one arrives complete.
- [ ] List the restricted lists it screens against (SDN, Entity List, Denied Persons, Unverified, Military End-User, and so on) and note any it doesn't.
- [ ] Document the match logic and threshold, and why that threshold fits your risk.
- [ ] Test with known positives: real listed names plus variations (transliterations, reordered names, missing middle names, alternate spellings like "Habana" for "Havana").

**List updates**

- [ ] Get the vendor's update commitment in hours, in writing.
- [ ] After a new designation, screen a newly listed name the next business day to confirm the update has loaded.
- [ ] Have a fallback for outages, such as a manual check against the government's own list.

**Alert handling**

- [ ] Exact and near-exact matches go to the top of the queue.
- [ ] Inventory every rule that suppresses, auto-clears, or downgrades an alert. Each needs a named approver, a written reason, and a review date.
- [ ] A false-positive decision expires. It shouldn't clear future alerts indefinitely, and it gets rechecked when the lists change.
- [ ] A second person reviews a sample of cleared alerts on a set schedule.

**Changes**

- [ ] Changes to logic, thresholds, data feeds, or vendors go through change control, with testing before and after.
- [ ] Roll changes out in stages so you don't create a backlog. OFAC's release calls for exactly this.

**When something breaks**

- [ ] Put a compensating control, usually manual review, in place immediately.
- [ ] Run a lookback wider than you think you need, and document how you scoped it.
- [ ] Decide quickly, with counsel, whether to voluntarily self-disclose. In this case, OFAC counted the 62 violations Bank of America self-disclosed at half their transaction value when setting the base penalty, and the other 413 at the full schedule amount.

**Once a year**

- [ ] Someone independent of the people who configured the tool tests the whole chain end-to-end.
- [ ] The results, including what you found and fixed, should be reported to management in writing.


