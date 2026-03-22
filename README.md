# 🧑‍💼 Workforce Performance & Efficiency Dashboard
### HR Analytics | Power BI

> <!-- PICK ONE AND DELETE THE REST:
> Option A: HR analytics dashboard tracking workforce turnover, hiring efficiency, and employee engagement across departments — built with Power BI and DAX.
> Option B: End-to-end HR analytics project covering data cleaning, DAX modelling, and interactive dashboard development in Power BI.
> Option C: Exploring what drives employee turnover and hiring costs — an HR analytics dashboard built from a cleaned Kaggle dataset using Power BI.
> -->

<img width="1325" height="743" alt="HR Analytics Dashboard (main view)" src="https://github.com/user-attachments/assets/6e4b9d73-4b51-4145-91f4-a2debefec7fd" />

---

## 📌 Overview

This dashboard provides HR stakeholders with a centralised view of key workforce metrics — from headcount and turnover trends to recruitment cost and employee satisfaction — enabling data-driven decisions around talent management and organisational efficiency.

The dataset is sourced from **Kaggle** (open source HR analytics dataset), cleaned and transformed in Power Query prior to visualisation.

---

## 📊 Dashboard Sections

| Section | Key Metrics |
|---|---|
| **Workforce Overview** | Current & Total Headcount, Revenue per Employee, Turnover Rate |
| **Productivity & Absenteeism** | Absenteeism Rate, Avg Overtime Hours, Training Completion Rate, Avg Absences by Dept |
| **Engagement & Satisfaction** | Avg Employee Satisfaction Score, Engagement Survey Rating |
| **Hiring Efficiency** | Avg Time to Hire, Hires by Recruitment Source, Avg Cost-per-Hire by Dept |

---

## 🔍 Key Insights

- **33.44% turnover rate** signals a retention challenge worth investigating at department level
- **Software Engineering** and **IT/IS** departments show the highest average revenue per employee
- **Indeed and LinkedIn** are the top recruitment sources by volume
- **Executive Operations** has the highest cost-per-hire at ~RM8.05K (20.15% of total)
- Average employee satisfaction sits at **3.89 / 5** — room for engagement improvement

---

## 🛠️ Tools & Technologies

![Power BI](https://img.shields.io/badge/Power%20BI-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)
![DAX](https://img.shields.io/badge/DAX-0078D4?style=for-the-badge&logo=microsoft&logoColor=white)
![Power Query](https://img.shields.io/badge/Power%20Query-217346?style=for-the-badge&logo=microsoft&logoColor=white)

- **Power BI Desktop** — report development and data modelling
- **DAX** — custom measures for headcount, turnover, hiring efficiency metrics
- **Power Query** — data cleaning and transformation
- **Dataset** — Open source HR analytics dataset from Kaggle (`cleaned_hr_data`)

---

## 📐 DAX Measures (Selected)

```dax
-- Active Employee Headcount (returns 0 instead of blank when filtered)
Headcount = 
COALESCE(
    CALCULATE(
        COUNTROWS('cleaned_hr_data'),
        ISBLANK('cleaned_hr_data'[DateofTermination])
    ),
    0
)

-- Turnover Rate
Turnover Rate = 
DIVIDE(
    CALCULATE(COUNTROWS('cleaned_hr_data'), NOT ISBLANK('cleaned_hr_data'[DateofTermination])),
    COUNTROWS('cleaned_hr_data')
)
```

---

## 🗂️ Repository Structure

```
📁 hr-analytics-dashboard/
├── 📄 README.md
├── 📊 HR_Analytics.pbix          ← Power BI report file
├── 📄 HR_Analytics.pdf           ← Static PDF export
└── 📁 screenshots/
    └── HR_Analytics_Screenshot1.png
```

---

## 🚀 How to Use

1. Download `HR_Analytics.pbix`
2. Open with **Power BI Desktop** (free download at microsoft.com/powerbi)
3. Explore the report using the slicers — **Employment Status**, **Gender**, **Department** — to filter views

---

## 👩‍💻 Author

**Nur Alisa Zarina Binti Nazmi**  
Data & Analytics Specialist | BI Developer  
[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=flat&logo=linkedin&logoColor=white)](https://linkedin.com/in/your-linkedin-url)
[![GitHub](https://img.shields.io/badge/GitHub-181717?style=flat&logo=github&logoColor=white)](https://github.com/your-github-username)

---

*Built as part of a personal analytics portfolio showcasing end-to-end BI development skills.*
