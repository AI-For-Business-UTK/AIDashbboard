AI Jobs Dashboard — README
Overview
This interactive dashboard, built with Python Dash, visualizes the landscape of AI-related job postings across the United States. It allows users to explore how AI jobs are distributed geographically, which career fields are most AI-intensive, and which technical skills are most in demand — with state-by-state comparisons throughout.
"AI jobs" are defined as job postings that include skills classified as AI-related (e.g. Machine Learning, Data Science, Natural Language Processing).
Running the App
Requirements
Install dependencies with:
bash
pip install dash dash-bootstrap-components plotly pandas
Launch
bash
python ElliotDashboard.py
Data Files
The dashboard expects the following four CSV files in the same directory as ElliotDashboard.py:

DensityMapData.csv:	State-level AI job counts and totals by year, used for the choropleth map
AISkillsTab_data.csv:	AI skill mentions per career area and state, used for the skills comparison chart
CareeerAreaStateShare.csv:	Career area share of a state's AI jobs, used in the career comparison tab
CareerAreaIntensity.csv:	AI intensity (AI jobs / all jobs) by career area and state
Column Reference
DensityMapData.csv
•	state_name — Full state name
•	year — Year of the job posting data
•	ai_jobs_count — Number of AI job postings in that state/year
•	all_jobs_state_year — Total job postings in that state/year
•	state_ai_share_within_state — Pre-computed ratio (ai_jobs / all_jobs)
AISkillsTab_data.csv
•	state_name — State
•	lot_career_area_name — Career area category
•	skills_name — Name of the AI-related skill
•	skill_count — Number of AI postings mentioning this skill
•	total_ai_listings — Total AI postings in that state/career area (denominator)
•	proportion — skill_count / total_ai_listings
CareeerAreaStateShare.csv
•	state_name — State
•	lot_career_area_name — Career area category
•	entry_count — AI job postings in that career area
•	total_jobs — Total AI jobs in that state (denominator)
•	proportion — entry_count / total_jobs
CareerAreaIntensity.csv
•	state_name — State
•	lot_career_area_name — Career area category
•	all_jobs — Total jobs in that career area/state
•	ai_jobs — AI jobs in that career area/state
•	intensity — ai_jobs / all_jobs
 
Dashboard Tabs
Tab 1 — Evolution of AI Jobs
A choropleth map of the US showing AI job concentration over time. Use the year range slider to filter by year, or press Play to animate year-by-year.
Two metric options:
•	State share — AI jobs as a percentage of all jobs in that state
•	US share — AI jobs in that state as a percentage of all US AI jobs
Tab 2 — AI Job Intensity in Careers
A grouped bar chart comparing the top 10 career areas between two selected states.
Two metric options:
•	Share of state's AI jobs — Which career areas dominate AI hiring within a state
•	AI intensity within career area — Which career areas are most AI-focused relative to their total job volume
Tab 3 — Top AI Skills
A grouped bar chart comparing the top 10 AI-related skills in two selected states, with an optional filter by career area. Skills are ranked by the proportion of AI postings in State 1 that mention them, and State 2 is shown alongside for the same skill set.
 
Notes
•	"Other / Unknown" career area entries are filtered out of all charts.
•	The skills chart counts skill mentions, not unique job postings — one posting may list multiple skills.
•	The intensity metric (Tab 2) can be inflated for career areas with very low overall job counts.

<img width="468" height="629" alt="image" src="https://github.com/user-attachments/assets/8e388479-73df-45a4-91b9-99f58a8a5896" />
