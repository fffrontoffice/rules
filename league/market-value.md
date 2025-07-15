
# Market Value Data Source & Calculation

**Purpose.**  Market Value (MV) must reliably reflect an unbiased “going rate” for players in salary-cap dynasty leagues that resemble ours. The process below intends to provide clear guidelines for fair market value calculation and what to do if a market value is considered inaccurate.


## 0️⃣  Annual Provider Selection (2 weeks before draft)

1. **Evaluation window** – Each year in the weeks leading up to the draft, the Commissioner (or a designated officer) reviews all publicly available auction-value sources against this checklist:

   | ✅ Requirement | Minimum bar |
   |---------------|-------------|
   | Freshness     | Updated regularly |
   | Accuracy     | Values in line with previous live auction ranges by position and tier |
   | Configurable  | Supports 12 teams, 0.5 PPR scoring, and publishes dollar figures |
   | Breadth       | ≥ 100 offensive players **and** (ideally) IDP values |
   | Exportable    | CSV / JSON or scrape-friendly HTML |

3. The Commissioner posts the provider recommendation to the `#league-updates` Slack channel no later than **2 weeks before the draft**.

4. **Owner review window** – Owners have **72 hours** to file an objection via Slack thread or GitHub issue.
   *Objections must show that another source meets the checklist materially better.*

5. If **>50 %** of all owners back an objection, the challengers’ preferred provider replaces the Commissioner’s DP; otherwise the original recommendation stands.

---

## 1️⃣  Snapshot Day (1 week before draft)

* **Timing** – **1 weeks before draft day before midnight PT**.
* **Action** – Commissioner exports raw data from the market value provider with closest matching configuration (12 teams, 0.5 PPR, \$1000 cap scaled if necessary).
* **Publication** – Upload to [FFFO](http://fffrontoffice.com), available on FFFO team pages, and announce completion in `#league-updates`.

---

## 2️⃣  Challenge Period

Owners have **48 hours** after publication to audit:

* **Transcription / scaling errors**
* **Missing players** who satisfy our roster requirements
* **Provider failure** (e.g., stale data, obvious errors)

Submit challenges via Slack.  The Commissioner rules within **24 hours**:

| Outcome | Criteria | Next step |
|---------|----------|-----------|
| **Accept** | Clear evidence of error or provider failure | Re-run Snapshot with corrected export or invoke fallback (see 3️⃣) |
| **Deny** | No objective error shown | Close issue; MV remains intact |

The Commissioner’s ruling can be **appealed** to a league-wide vote; overturn requires **2∕3 majority** of all owners within 24 hours with the majority agreeing on how to proceed.

---

## 3️⃣  Emergency Fallback Logic

If the market value provider cannot produce a usable value **before** Snapshot Day (or during a re-run), the Commissioner proceeds down this list until one succeeds:

1. ESPN auction cheat sheet scaled to $1000
2. ChatGPT prompt using all current+historic contract data and ESPN draft list cheat sheet.

Any emergency switch is immediately disclosed in Slack/GitHub with a brief rationale.
