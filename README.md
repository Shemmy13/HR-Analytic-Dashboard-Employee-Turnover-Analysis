# HR Analytics Dashboard & Employee Turnover Analysis

This repository contains a comprehensive HR analytics project designed to evaluate employee demographics, performance metrics, department distributions, and key turnover factors. Using a thoroughly cleaned dataset of **310 employees** (originally 311 rows before removing an inconsistent record), this project uncovers critical workforce insights to help improve retention strategies and optimize departmental engagement.

The visual analytics are designed in Excel using automated **Power Query transformations**, allowing users to click **Refresh** when a new raw dataset is introduced simply.

---

## 📊 Executive Summary & KPIs

The project features a dedicated executive summary dashboard tracking **8 core KPIs**:

| KPI | Value | Calculation Logic |
| :--- | :--- | :--- |
| **Total Employees** | 310 | Count of all Employee IDs |
| **Active Employees** | 207 | Count where Termd = 0 |
| **Terminated Employees** | 103 | Count where Termd = 1 |
| **Turnover Rate** | 33.23% | (Terminated ÷ Total) × 100 |
| **Average Age** | 39.05 Years | AVERAGE(Age column) |
| **Average Tenure** | 5.35 Years | AVERAGE(Tenure_Years column) |
| **Average Salary** | $69,033.80 | AVERAGE(Salary column) |
| **Average Engagement** | 4.11 / 5.00 | AVERAGE(EngagementSurvey column) |

---

## 🔍 Business Questions Answered (The 8 Key Questions)

### Q1: What is the overall turnover rate? Which department has the highest/lowest turnover?
* **Answer:** The overall turnover rate is **33.23%**.
  * **Highest Turnover:** **Production** at **79.61%** (82 out of 103 employees terminated).
  * **Lowest Turnover:** **Executive Office** at **0.00%** (0 out of 103 employee terminated), followed by **Sales** at **4.85%** (5 out of 31 terminated).
* **Insight:** Production is the operational core of the business but represents **79.61% of all terminations** in the company.
* **Recommendation:** Implement a targeted retention study for the Production team (e.g., review shift schedules, working conditions, and immediate supervisor relationships).

### Q2: Which year between 2010 and 2018 had the most terminations?
* **Answer:** **2015** was the peak year with **23 terminations**, closely followed by **2016** with **22 terminations**.
* **Insight:** **43.69%** of all historical terminations occurred within this 2-year window (2015–2016).
* **Recommendation:** Investigate historical company events during 2015–2016 (e.g., management changes, restructuring, or compensation freezes) to prevent similar retention spikes.

### Q3: What is the average tenure of employees who leave? Do Production employees leave sooner than IT employees?
* **Answer:** The average tenure of employees who leave is **3.44 years**. **Yes**, Production employees leave sooner than IT employees:
* **Insight:** Production employees leave **more than twice as fast** as IT staff.

### Q4: Which recruitment source produces the most hires? Which source produces the highest performing employees?
* **Answer:**
  * **Most Hires:** **Indeed** (87 hires), followed closely by **LinkedIn** (75 hires).
  * **Highest Performance:** **Diversity Job Fair** produces the highest proportion of top performers with **20.69%** of candidates achieving an *"Exceeds Expectations"* rating, followed by **Employee Referrals** at **16.13%**.
* **Insight:** While Google Search and LinkedIn bring in high volume, Diversity Job Fairs and Employee Referrals provide the highest quality of long-term performers.
* **Recommendation:** Shift recruiting budget towards local Diversity Job Fairs and establish a more robust internal Employee Referral program.

### Q5: Is there a gender pay gap? What is the average salary for males vs females?
* **Answer:** There is a slight pay disparity:
  * **Male Average Salary:** $70,629.40
  * **Female Average Salary:** $67,802.91
  * **Pay Gap:** Males are paid **4.17%** more on average than females.
* **Insight:** While the gap is relatively narrow compared to broader industry averages, a difference of nearly **$2,826** exists.
* **Recommendation:** Conduct a pay-equity audit grouped by position and experience level to identify if the discrepancy is due to role distributions (e.g., more males in technical/senior DB roles) or true gender pay inequality.

### Q6: Which age group (Under 30, 30-44, 45-59, 60+) has the highest turnover rate?
* **Answer:** The **30-44** age group has a staggeringly high turnover rate of **56.31%** (58 terminations out of 103 employees in this bracket).
  * **Below 30:** 28.16% turnover rate.
  * **45-59:** 15.53% turnover rate.
  * **60 and Above:** 0.00% turnover rate (0 terminations).
* **Insight:** Younger workers between 30 to 44 are highly transient and leave the organization at more than double the rate of older demographics.
* **Recommendation:** Design entry-level mentorship programs, professional training opportunities, and clear career pathing to engage and retain younger talent.

### Q7: Which department has the highest average engagement score? Which has the highest average satisfaction?
* **Answer:**
  * **Highest Average Engagement:** **Executive Office** (4.83 / 5.00), followed by **Admin Offices** (4.39 / 5.00).
  * **Highest Average Satisfaction:** **Software Engineering** (4.09 / 5.00), followed closely by **Sales** (4.03 / 5.00).
* **Insight:** Sales has strong day-to-day job satisfaction (4.03) but holds the lowest overall team engagement (3.82), highlighting a gap in deep-seated company alignment.
* **Recommendation:** Organize cross-departmental alignment sessions for the Sales department to connect their day-to-day metrics to broader company achievements.

### Q8: Do employees who exceed expectations stay longer than those who need improvement? Compare their average tenure.
* **Answer:** **Yes.**
  * **Exceeds Expectations:** **6.16 Years** average tenure.
  * **Needs Improvement:** **5.22 Years** average tenure.
* **Insight:** High performers (*"Exceeds"*) stay with the company approximately **11 months longer** than those needing improvement.
* **Recommendation:** Provide immediate performance-coaching programs for struggling employees to improve performance, rather than letting tenure passively decline toward performance issues.

---

## 🛠️ Data Cleaning & Transformation Process

A rigorous data cleaning process was executed to ensure data integrity and prepare the dataset for accurate analysis:

* **Row Filtering & Inconsistency Removal:** The initial raw dataset contained 311 rows. After identifying significant data inconsistency in one of the entries, that row was removed, resulting in a finalized clean dataset of **310 rows**.
* **Feature Engineering:**
  * Calculated the exact **tenure (years spent)** for each employee using the relationship between their `Date of Hire` and `Date of Termination` or `December 31, 2019`.
  * Formatted and validated employee **Age** to ensure absolute consistency with their Date of Birth (DOB) and operational dates.
* **Text Standardization:**
  * Converted and standardized general text columns using Excel's `PROPER` function.
  * Formatted the `HispanicLatino` column to standardized capitalized text (`YES` / `NO`) to eliminate duplicate categories caused by varying case inputs.

---

## 📦 Project Deliverables

* **An Excel file:** Featuring the original dataset, a cleaned dataset, an Interactive Excel Dashboard, 8 KPI values, 6 PivotTables, 6 Charts, and 3 Slicers (Department, Performance Score, Sex).
* **Business Report:** The detailed narrative answering all 8 key questions.
