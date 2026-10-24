# Recruitment Analytics: Power BI

Power BI report on a hiring pipeline: job postings, applications, interviews, offers and salaries. The goal is to find where candidates drop off, which sources work best, and how offers compare with posted salaries.

SQL part of this project: https://github.com/hajrijemjeku/RecruitmentAnalytics

## Tools
Power BI Desktop, Power Query, DAX

## Data
Dataset: job-postings-applications by mindweave (https://huggingface.co/datasets/mindweave/job-postings-applications),
licensed under CC BY-NC 4.0 (https://creativecommons.org/licenses/by-nc/4.0/).
Changes: data was cleaned and modeled in Power BI.
The original CSV files are in `data/raw/`.

Tables: applications, candidates, companies, interviews, jobs, offers

## Data Model
![Data model](screenshots/data_model.png)

- Companies → Jobs → Applications → Offers / Interviews
- Candidates → Applications
- A Date table connects to applications by `applied_date` (active). Relationships to offers (offered and accepted dates), interviews and jobs are inactive and used in DAX measures with `USERELATIONSHIP`.

## How to open
Open `report/RecruitmentAnalytics.pbix` in Power BI Desktop (Windows). To refresh the data, update the file paths in Power Query (Transform data → Data source settings → Change Source).