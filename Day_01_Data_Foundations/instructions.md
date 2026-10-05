# Day 1 — Data Foundations: what *kind* of data is this?

🏢 **You are:** a brand-new analyst at **FoodCo**, an Indian food-delivery startup.

## Files in this folder
```
instructions.md        ← this file
data/
  orders_sample.csv    40 completed orders (rows & columns)
  app_events.json      nested events logged by the mobile app
  customer_reviews.txt  free-text reviews customers typed
  gps_pings.csv        a delivery rider's location pings
  data_inventory.csv   ← the worksheet YOU fill in
```

## 📋 The business scenario
It's your first morning and the Ops team has dumped eight different files on your desk — spreadsheets, app logs, reviews, a menu photo, a call recording. Before anyone can analyse anything, leadership needs you to say **what type of data each one is** and **where it fits in the analytics lifecycle** (collect → clean → analyse → report).

## ✅ Your task
1. Open each file in `data/` and look at its *shape*:
   - `orders_sample.csv` in Excel/Sheets
   - `app_events.json` in a text editor or browser
   - `customer_reviews.txt` in Notepad
   - `gps_pings.csv` in Excel/Sheets
2. Open **`data/data_inventory.csv`** (8 artifacts are listed, including a menu photo, a support-call audio, and a WhatsApp complaint that aren't physical files here — classify them anyway).
3. Fill the two blank columns for every row:
   - **`your_classification`** → `Structured`, `Semi-structured`, or `Unstructured`
   - **`which_analytics_type`** → which lifecycle stage / analysis it best supports
4. Below the table (new sheet or a `notes.md`), write **3 bullets**:
   - Which files can go *straight* into Excel with no transformation?
   - Which need parsing/flattening first?
   - Which can't be analysed at all until they're converted into structured data?

## 🎯 Deliverable
A completed `data_inventory.csv` (save as `data_inventory_solved.csv`) + your 3 bullets.

## 💡 Hints
- Rows-and-columns with one value per cell = **structured**.
- Has structure but nests/repeats (keys, tags, arrays) = **semi-structured** (JSON, GPS logs).
- No rows/columns at all — prose, images, audio = **unstructured**.
- Ask yourself: *could I `=SUM()` this today?* If not, what would it take?

## ✔️ You're done when
Every row of `data_inventory.csv` has both blank columns filled and you can defend each call in one sentence.
