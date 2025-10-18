## 📊 Dataset: Employee Performance Table (10 rows)

| ID | Name  | Department | Days_Worked | Salary | Score | Attendance | Bonus | Grade | Remarks |
| -- | ----- | ---------- | ----------- | ------ | ----- | ---------- | ----- | ----- | ------- |
| 1  | Rafi  | Sales      | 27          | 30000  | 85    | Present    |       |       |         |
| 2  | Nisa  | HR         | 21          | 28000  | 72    | Present    |       |       |         |
| 3  | Adnan | IT         | 25          | 35000  | 33    | Absent     |       |       |         |
| 4  | Mahir | Sales      | 29          | 32000  | 90    | Present    |       |       |         |
| 5  | Sara  | HR         | 23          | 31000  | 45    | Present    |       |       |         |
| 6  | Rakib | IT         | 19          | 36000  | 27    | Absent     |       |       |         |
| 7  | Lina  | Finance    | 26          | 40000  | 60    | Present    |       |       |         |
| 8  | Ziya  | HR         | 30          | 29000  | 91    | Present    |       |       |         |
| 9  | Sami  | IT         | 24          | 34000  | 50    | Present    |       |       |         |
| 10 | Asha  | Sales      | 22          | 28000  | 20    | Absent     |       |       |         |

---

## 🧠 এখন আসল অংশ: “IF” function এর প্রশ্নগুলো 👇

### 🎯 Basic `IF`

1️⃣ **Question:**
যদি `Score` 33 এর বেশি হয় তাহলে “Pass”, নাহলে “Fail” লেখো।
👉 Formula:

```excel
=IF(F2>33,"Pass","Fail")
```

---

### 🎯 IF with Arithmetic Operation

2️⃣ **Question:**
যারা 24 দিনের বেশি অফিস করেছে (`Days_Worked>24`), তাদের `Salary`-এর সাথে ৫% বাড়তি বোনাস যোগ হবে, নাহলে একই Salary থাকবে।
👉 Formula:

```excel
=IF(D2>24, E2*1.05, E2)
```

---

### 🎯 Nested IF (Multiple Conditions)

3️⃣ **Question:**
`Score` অনুযায়ী Grade দাও:

* 80 বা তার বেশি → A
* 60 বা তার বেশি → B
* 40 বা তার বেশি → C
* অন্যথায় → F
  👉 Formula:

```excel
=IF(F2>=80,"A",IF(F2>=60,"B",IF(F2>=40,"C","F")))
```

---

### 🎯 IF + AND (Multiple logical condition একসাথে)

4️⃣ **Question:**
যদি কেউ 25 দিনের বেশি কাজ করে **এবং** তার `Score` 70 এর বেশি হয়, তাহলে “Top Performer” লেখো, নাহলে “Normal”।
👉 Formula:

```excel
=IF(AND(D2>25, F2>70),"Top Performer","Normal")
```

---

### 🎯 IF + OR (যেকোনো একটা শর্ত পূরণ করলেই)

5️⃣ **Question:**
যদি কেউ `Sales` বা `HR` ডিপার্টমেন্টে থাকে, তাহলে “Client-facing” লেখো, নাহলে “Back-office”।
👉 Formula:

```excel
=IF(OR(C2="Sales", C2="HR"),"Client-facing","Back-office")
```

---

### 🎯 IF + TEXT output

6️⃣ **Question:**
`Attendance` যদি “Absent” হয়, তাহলে “Not eligible for bonus”, নাহলে “Eligible” লেখো।
👉 Formula:

```excel
=IF(G2="Absent","Not eligible","Eligible")
```

---

### 🎯 IF + DATE logic (hypothetical)

7️⃣ **Question:**
ধরা যাক একটা কলাম আছে `Join_Date`,
যদি কেউ 2024 সালের আগেই যোগ দেয়, তাহলে “Old Employee”, নাহলে “New Employee”।
👉 Formula:

```excel
=IF(J2<DATE(2024,1,1),"Old Employee","New Employee")
```

---

### 🎯 IF + Mathematical Condition

8️⃣ **Question:**
যাদের `Score` 50 এর কম, তাদের Salary থেকে ১০% কেটে দাও (Penalty হিসেবে)।
👉 Formula:

```excel
=IF(F2<50,E2*0.9,E2)
```

---

### 🎯 IF + Nested Text Logic

9️⃣ **Question:**
`Attendance` যদি “Absent” হয়, তাহলে “Check Discipline”;
অন্যথায়, যদি `Score` 80 এর বেশি হয়, তাহলে “Excellent”;
নাহলে “Good”.
👉 Formula:

```excel
=IF(G2="Absent","Check Discipline",IF(F2>80,"Excellent","Good"))
```

---

### 🎯 IFERROR (Error handle করার জন্য)

🔟 **Question:**
ধরা যাক তুমি একটা formula লিখেছো: `=E2/D2` (salary per day বের করতে)।
কিন্তু যদি `Days_Worked` শূন্য হয় তাহলে error আসবে, সেটার জায়গায় “Invalid” দেখাও।
👉 Formula:

```excel
=IFERROR(E2/D2,"Invalid")
```

---

## ✅ Summary: আজ তুমি যেগুলো শিখলে

| Function Type    | Formula Concept              |
| ---------------- | ---------------------------- |
| Basic IF         | Simple True/False condition  |
| IF + Arithmetic  | Salary increase/decrease     |
| Nested IF        | Multiple grading levels      |
| IF + AND         | একাধিক শর্ত একসাথে           |
| IF + OR          | যেকোনো একটি শর্তে কাজ        |
| IF + Text        | Text-based output            |
| IF + DATE        | সময়-ভিত্তিক শর্ত             |
| IF + Math        | Penalty বা Bonus Calculation |
| IF + Nested Text | Multi-level decision         |
| IFERROR          | Error handling               |
