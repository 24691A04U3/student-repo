# Day 2 — The 4 analytics types & data ethics

🏢 **You are:** the FoodCo analyst. Today leadership fires questions at you, and Legal flags a privacy problem.

## Files in this folder
```
instructions.md
data/
  business_questions.csv   15 real questions from leadership — you tag each
  customers_pii.csv        60 customers incl. personal data — you audit & mask it
  orders_sample.csv        200 orders for quick descriptive stats
```

## 📋 The business scenario
Leadership fires off fifteen questions, ranging from *"what was revenue in August?"* to *"what discount should we give each customer to keep them?"*. At the same time, Legal points out the customer table is full of personal data nobody has reviewed — and reminds everyone that FoodCo answers to India's **DPDP Act 2023**. You must sort the questions by **analytics type**, then audit *and* mask the customer data so it's safe to share.

## ✅ Your task

**Part A — Classify the questions (`business_questions.csv`)**
Tag each of the 15 questions as one of:
- **Descriptive** — what happened? (the past, summarised)
- **Diagnostic** — why did it happen? (root cause)
- **Predictive** — what will happen? (forecast / likelihood)
- **Prescriptive** — what should we do about it? (recommend an action)

**Part B — Build a "safe-to-share" customer table (`customers_pii.csv`)**
1. List every column that is **PII** (personally identifiable information), and flag any **quasi-identifier** (a field that re-identifies someone *in combination* — e.g. city + date of birth).
2. For each PII column, add a masked column using the **text functions from Day 1** (`LEFT`, `RIGHT`, `MID`, `FIND`, `TEXT`). Examples:
   - phone → `="xxxxxx"&RIGHT(D2,4)`  → `xxxxxx2098`
   - email → `=LEFT(C2,2)&"***@"&MID(C2,FIND("@",C2)+1,50)`  → `kr***@example.com`
   - date_of_birth → year only `=TEXT(E2,"yyyy")`
   - **keep `customer_id` unmasked** — it's your analysis key, not personal.
3. Save the masked result as `safe_customers.csv` (the version you *could* hand to a partner).
4. Name **one question from Part A** that would be *unethical or risky* to answer using the raw data as-is, and say why (consent? discrimination? re-identification?).

**Part C — Feel the difference (`orders_sample.csv`)**
In Excel compute three **descriptive** numbers with Day 1's functions: total revenue (`SUM`), average order value (`AVERAGE`), number of orders (`COUNT`). Then write one sentence: *why can't these same formulas answer a predictive question?*

**Part D — The ethics desk (discussion, done in class)**
For each request, decide **Answer / Refuse / Answer only masked-&-aggregated**, and justify:
- Marketing wants the **phone numbers of churned customers** to cold-call them.
- A partner brand wants to **buy your customer list segmented by age**.
- The CEO wants **average order value by age band**.
- Ops wants to know **which customers live nearest the new dark store**.

## 🎯 Deliverable
`business_questions_solved.csv` (all 15 tagged) + `safe_customers.csv` (every PII column masked) + a short `audit.md` (PII + quasi-identifier list, masking rule per column, the one risky question & why) + your 3 descriptive numbers.

## 💡 Hints
- "How many / what was / total / average" → usually **Descriptive**.
- "Why / what's driving / what caused" → **Diagnostic**.
- "Will / likely / next month / forecast" → **Predictive**.
- "What should we / best / optimise / recommend" → **Prescriptive**.
- PII = anything that identifies a person alone or combined: name, email, phone, DOB, exact address.

## ✔️ You're done when
All 15 questions are tagged, you've produced `safe_customers.csv` with every PII column masked (and `customer_id` left intact), and you've named one question that shouldn't be answered with raw PII.
