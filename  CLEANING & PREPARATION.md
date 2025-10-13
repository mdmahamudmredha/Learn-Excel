## 🧹 CLASS: DATA CLEANING & PREPARATION IN EXCEL

**“Data Cleaning & Preparation in Excel”** হচ্ছে **Data Analytics-এর প্রথম বাস্তবিক ধাপ** — যেখানে আমরা raw, messy data কে বিশ্লেষণের উপযোগী করে তুলি।

---

### 🧩 Topic 1: Remove Duplicates

**Real-life scenario:**
ধরা যাক তুমি customer list রাখো — কিন্তু একই customer একাধিকবার entry হয়েছে।
এই duplicate record report কে ভুল করে দেয়।

| CustomerName | Email                                       | City     |
| ------------ | ------------------------------------------- | -------- |
| Arafat       | [arafat@gmail.com](mailto:arafat@gmail.com) | Dhaka    |
| Mitu         | [mitu@gmail.com](mailto:mitu@gmail.com)     | Khulna   |
| Arafat       | [arafat@gmail.com](mailto:arafat@gmail.com) | Dhaka    |
| Tanvir       | [tanvir@gmail.com](mailto:tanvir@gmail.com) | Sylhet   |
| Nayeem       | [nayeem@gmail.com](mailto:nayeem@gmail.com) | Dhaka    |
| Mitu         | [mitu@gmail.com](mailto:mitu@gmail.com)     | Khulna   |
| Rafi         | [rafi@gmail.com](mailto:rafi@gmail.com)     | Rajshahi |
| Niloy        | [niloy@gmail.com](mailto:niloy@gmail.com)   | Dhaka    |
| Rafi         | [rafi@gmail.com](mailto:rafi@gmail.com)     | Rajshahi |
| Farhan       | [farhan@gmail.com](mailto:farhan@gmail.com) | Barishal |

**Shortcut:**
➡️ `Alt + A + M`

**Graphics:**
➡️ **Data Tab → Remove Duplicates (Ribbon)**

---

### 🧩 Topic 2: Trim Extra Spaces

**Real-life scenario:**
কখনও নাম বা প্রোডাক্টের নামের আগে/পরে space থেকে যায়, যা lookup বা matching এর সময় সমস্যা তৈরি করে।

| Name (Raw)  | Corrected Formula |
| ----------- | ----------------- |
| "  Arafat " | `=TRIM(A2)`       |
| " Tanvir "  | `=TRIM(A3)`       |

**Shortcut:**
➡️ No direct shortcut (use formula manually)

**Graphics:**
➡️ **Formula Tab → Text Functions → TRIM**

---

### 🧩 Topic 3: Change Case (UPPER, LOWER, PROPER)

**Real-life scenario:**
Customer names mixed case-এ আছে — presentation এর জন্য uniform করতে হয়।

| Name (Raw) | Formula       | Result |
| ---------- | ------------- | ------ |
| aRAFAt     | `=PROPER(A2)` | Arafat |
| TANVIR     | `=LOWER(A3)`  | tanvir |
| mitu       | `=UPPER(A4)`  | MITU   |

**Shortcut:**
➡️ No shortcut (formula only)

**Graphics:**
➡️ **Formulas → Text → UPPER/LOWER/PROPER**

---

### 🧩 Topic 4: Find & Replace (Clean Text)

**Real-life scenario:**
Dataset-এ "BD" ও "Bangladesh" দুই রকমভাবে লেখা আছে — সবকিছু এক রকম করতে হবে।

| City (Before)          |
| ---------------------- |
| Dhaka, BD              |
| Chittagong, Bangladesh |
| Rajshahi, BD           |

**Shortcut:**
➡️ `Ctrl + H`

**Graphics:**
➡️ **Home Tab → Editing Group → Find & Select → Replace**

---

### 🧩 Topic 5: Text to Columns

**Real-life scenario:**
Customer data এক কলামে আছে: “Arafat - Dhaka - 01712345678”
তোমাকে এটাকে আলাদা কলামে ভাগ করতে হবে।

| Full Info                    |
| ---------------------------- |
| Arafat - Dhaka - 01712345678 |

➡️ After Split ⬇️

| Name   | City  | Phone       |
| ------ | ----- | ----------- |
| Arafat | Dhaka | 01712345678 |

**Shortcut:**
➡️ `Alt + A + E`

**Graphics:**
➡️ **Data Tab → Text to Columns**

---

### 🧩 Topic 6: Handling Missing Data (Blanks)

**Real-life scenario:**
কিছু Sales Data-তে Product Name বা Quantity missing।

| Product | Quantity | Price |
| ------- | -------- | ----- |
| Shirt   | 2        | 800   |
| *Blank* | 1        | 600   |
| Pant    | *Blank*  | 1000  |

**Fix Methods:**

1. Highlight blanks: `Ctrl + G` → Special → Blanks
2. Fill manually or use formula: `=IF(A2="", "Unknown", A2)`

**Shortcut:**
➡️ `Ctrl + G` → Special → Blanks

**Graphics:**
➡️ **Home Tab → Find & Select → Go To Special**

---

### 🧩 Topic 7: Data Validation (Prevent wrong data entry)

**Real-life scenario:**
Employee Age column-এ কেউ “twenty” লিখে ফেলেছে — যা invalid।

✅ Solution: Allow only whole numbers between 18–60.

**Shortcut:**
➡️ `Alt + D + L`

**Graphics:**
➡️ **Data Tab → Data Tools → Data Validation**

---

### 🧩 Topic 8: Convert Text to Number

**Real-life scenario:**
তুমি CSV ফাইল থেকে data নিয়েছো, কিন্তু সংখ্যাগুলো “Text” format-এ আছে (left aligned)।

| Sales (Text) | Converted |
| ------------ | --------- |
| '5000        | 5000      |

**Fix Methods:**

* `=VALUE(A2)`
* অথবা: select → small warning icon → “Convert to Number”

**Shortcut:**
➡️ `Alt + D + E` (Text to Columns also works)

**Graphics:**
➡️ **Data → Text to Columns → Finish**

---

### 🧩 Topic 9: Remove Blank Rows

**Real-life scenario:**
ডেটার মাঝে মাঝে খালি সারি আছে, যা chart বা pivot table-এ সমস্যা দেয়।

| Name   | Sales |
| ------ | ----- |
| Arafat | 500   |
|        |       |
| Mitu   | 600   |
|        |       |
| Tanvir | 700   |

**Shortcut:**
➡️ `Ctrl + G → Special → Blanks → Ctrl + -`

**Graphics:**
➡️ **Home → Find & Select → Go To Special → Blanks → Delete Rows**

---

### 🧩 Topic 10: Find Errors (#DIV/0!, #N/A, etc.)

**Real-life scenario:**
Formula data error দেখাচ্ছে — report clean করার আগে এগুলো ধরতে হবে।

**Fix Methods:**

| Formula | Meaning              | Fix                                     |
| ------- | -------------------- | --------------------------------------- |
| #DIV/0! | Division by zero     | Use `=IFERROR(A2/B2, 0)`                |
| #N/A    | Missing lookup value | Use `IFERROR(VLOOKUP(...),"Not Found")` |

**Shortcut:**
➡️ No direct shortcut

**Graphics:**
➡️ **Formulas Tab → Error Checking**

---

### 🧩 Topic 11: Use Filters to Inspect Data

**Real-life scenario:**
Dataset খুব বড়। Missing বা unusual value বের করতে চাই।

**Shortcut:**
➡️ `Ctrl + Shift + L`

**Graphics:**
➡️ **Data Tab → Sort & Filter → Filter**

---

### 🧩 Topic 12: Sort Data Properly

**Real-life scenario:**
Sales রিপোর্ট city অনুযায়ী সাজাতে হবে বা highest to lowest sort করতে হবে।

**Shortcut:**
➡️ `Alt + D + S`

**Graphics:**
➡️ **Data Tab → Sort (Ribbon)**

---

### 🧩 Topic 13: Combine Data (CONCAT / TEXTJOIN)

**Real-life scenario:**
First Name এবং Last Name আলাদা কলামে আছে — full name বানাতে হবে।

| First  | Last    | Formula              | Result         |
| ------ | ------- | -------------------- | -------------- |
| Arafat | Hossain | `=CONCAT(A2," ",B2)` | Arafat Hossain |

**Shortcut:**
➡️ No shortcut (formula only)

**Graphics:**
➡️ **Formulas → Text → CONCAT or TEXTJOIN**

---

### 🧩 Topic 14: Flash Fill (Auto Pattern Detection)

**Real-life scenario:**
Email বানাতে চাও → [first.last@gmail.com](mailto:first.last@gmail.com) pattern অনুসারে।

| First  | Last    | Email                            |
| ------ | ------- | -------------------------------- |
| Arafat | Hossain | (type one example, press Ctrl+E) |

**Shortcut:**
➡️ `Ctrl + E`

**Graphics:**
➡️ **Data Tab → Flash Fill**

---

### 🧩 Topic 15: Remove Unnecessary Characters (CLEAN & SUBSTITUTE)

**Real-life scenario:**
Copy-pasted text এ hidden characters আছে, যেমন line break বা unwanted symbol।

| Text                  | Formula                  | Result  |
| --------------------- | ------------------------ | ------- |
| “Arafat@#”            | `=SUBSTITUTE(A2,"@","")` | Arafat# |
| “Tanvir” (line break) | `=CLEAN(A3)`             | Tanvir  |

**Shortcut:**
➡️ No shortcut

**Graphics:**
➡️ **Formulas → Text → CLEAN / SUBSTITUTE**

---

### 🧩 Topic 16: Standardize Date Format

**Real-life scenario:**
একই dataset এ “01-02-2024”, “Feb 1, 2024”, “2024/02/01” — সব রকম তারিখ ফরম্যাট আছে।

✅ Solution:

* Select → Right-click → Format Cells → Date → choose consistent style.

**Shortcut:**
➡️ `Ctrl + 1` → Date Format

**Graphics:**
➡️ **Home → Number Format → Date**

---

### 🧩 Topic 17: Check for Outliers (Basic)

**Real-life scenario:**
কেউ sales amount 50000 দিয়েছে, বাকিরা 1000–3000 range এ। এটা ভুল হতে পারে।

✅ Use Conditional Formatting → Highlight cells above average.

**Shortcut:**
➡️ `Alt + H + L`

**Graphics:**
➡️ **Home → Conditional Formatting → Top/Bottom Rules → Above Average**

---

### 🧩 Topic 18: Remove Duplicates Across Sheets (Advanced tip)

**Real-life scenario:**
Customer List Sheet1 & Sheet2 তে আছে — combine করে unique list দরকার।

✅ Use:

```excel
=UNIQUE( {Sheet1!A2:A100; Sheet2!A2:A100} )
```

*(available in Excel 365+)*

---

## ✅ BONUS TIP: Cleaning Workflow Summary

1. Remove Duplicates
2. Trim / Clean / Substitute
3. Fix missing / blanks
4. Format numbers & dates
5. Validate data
6. Apply filters & sorting
7. Save as “Clean Data”
