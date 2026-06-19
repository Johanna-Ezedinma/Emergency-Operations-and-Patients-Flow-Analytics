# Code Blue - Emergency Operations & Patient Flow Analytics
### *How small failures compound into crisis*


**Author:** Johanna Ezedinma  
**Date:** June 2026   

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/johanna-ezedinma/) [![Medium](https://img.shields.io/badge/Medium-12100E?style=for-the-badge&logo=medium&logoColor=white)](https://medium.com/@johannaezedinma/code-blue-emergency-operations-patient-flow-analytics-1cf7176a1ec7) [![GitHub](https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/Johanna-Ezedinma)



> An 11-hospital NHS network is showing signs of strain: long waits, staff burnout,
> rising readmissions, and a mortality rate that varies sharply by hospital. This
> report investigates where the system is breaking down, why, what it's costing,
> and what to do about it.

Built in Power BI with DAX and Power Query for **The FP20
Analytics Challenge 38**.

---

## The Business Problem

A network of 11 NHS and private hospitals had two years of operational data:
patient visits, staffing, and finances, but no way to see which hospitals were
under the most pressure, why patients were waiting so long, or what any of it
was costing the network in money and in lives.

The stakeholders needed answers to three questions, in order: **Where is the system
breaking down? Why is it breaking down? And what would it cost in money and
in lives to fix it?**

This report was built to answer all three, with evidence drawn from 9,994
patient visits across 24 months.

---

## The Approach

Rather than organising the report around what the dataset contained, every page
was structured around what a Director of Operations would need to know, in the
order they'd need to know it. The guiding question throughout was: *if I had to
walk into a board meeting with this data, what would I say first, second, and
third?*

That produced a single connected story: network-wide pressure - flows
into the operational mechanism behind it - which flows into cost and
recommended action - The department page goes one level deeper, checking
whether the same failure patterns hold at the clinical-department level and
finds that they don't. The diagnosis page goes
deeper still, checking whether the same patients are even reaching the right
department in the first place.

---

## Project Overview

| Metric | Detail |
|---|---|
| Patient visits | 9,994 |
| Hospitals | 11 (NHS and Private) |
| Clinical departments | 12 |
| Diagnosis categories | 13 |
| Period | 2024 – 2025 (24 months) |
| Currency | GBP (£) |
| Fact tables | 3:  Patient Visits, Staffing, Financials |
| Dimension tables | 8 |

---


## Report Structure

The report is organised into five pages that tell one connected story. Each
page ends by raising the question the next page answers.

---

### Page 1 — Pulse: Network Demand & Pressure Overview

**Question answered:** Where is the network under pressure right now, and which
hospitals need attention first?

**Key insight:** Four hospitals — Sandwell General, Nuffield Health, Leeds
General Infirmary, and University College London are flagged Critical
simultaneously. Sandwell is the only one failing on *every* tracked dimension at
once: wait time, staffing stress, bed occupancy, and mortality. Emergency
admissions carry both the highest volume and the highest mortality rate in the
network, and the morning shift on Mondays alone absorbs 44% of weekly demand.

**Recommendation:** Four hospitals operating beyond safe capacity is a symptom.
The next page goes inside the operation to find the cause.

![Pulse](./Dashboards/Code%20Blue%20—%20Emergency%20Operations%20&%20Patient%20Flow%20Analytics_C38_Pulse.jpg)

---

### Page 2 — Operations: Diagnosing the Care Pathway

**Question answered:** Why are these hospitals under pressure, and at which
stage of the patient journey does it actually happen?

**Key insight:** Sandwell sits alone in the highest-overtime, longest-wait
quadrant with Critical staffing stress, the only hospital combining all three.
Severity 1 (Immediate) patients wait 50 minutes at triage, only 36 minutes
faster than Severity 5 (Non-Urgent) patients at 14 minutes, the triage queue
isn't prioritising by urgency. The afternoon shift carries both the highest
overtime and the highest burnout of any shift in the network.

**Recommendation:** These are the mechanisms behind Page 1's pressure. The next
page puts a price on them and sets out what to do.

![Operations](./Dashboards/Code%20Blue%20—%20Emergency%20Operations%20&%20Patient%20Flow%20Analytics_C38_Operations.jpg)

---

### Page 3 — Impact: Cost, Recommendations & Simulation

**Question answered:** What is this costing the network, and what should
be done first?

**Key insight & recommendations:**

1. **Activate an Immediate Surge Protocol**
   Sandwell being the only hospital in the network simultaneously flagged Critical
   on staffing stress, wait time (103 mins), bed occupancy (56%), and mortality
   (4.02%), an immediate surge protocol should be activated.
2. **Commission a Network-Wide Triage Audit.** The 36-minute gap between
   Severity 1 and Severity 5 wait times at triage is a clinical governance
   failure requiring review at all 11 hospitals, not just the worst-performing
   one.
3. **Deploy Structured Discharge Planning Across the Network.** King's College
   Hospital NHS FT has the network's highest 30-day readmission rate at 18.2%
   against a 17.0% average checklists, telemedicine check-ins, and community
   follow-up calls could close this gap without new infrastructure spend.

**The simulator** — moving the sliders updates three live results: at a
21-minute triage target, 3,841 patients currently fall outside it; at 89%
occupancy, that threshold was crossed 16 times across the network in two years
(roughly 0.7 hospitals over capacity every month); and a 25% reduction in wait
times would save an estimated £132.7K against the current £530.88K cost of
long-wait visits.

**Recommendation:** These three actions address the network at hospital level. 
The next page checks whether the same failures repeat at the clinical
department level, or whether each specialty needs its own fix.

![Impact](./Dashboards/Code%20Blue%20—%20Emergency%20Operations%20&%20Patient%20Flow%20Analytics_C38_Impact.jpg)

---

### Page 4 — Department: Specialty-Level Vulnerabilities

**Question answered:** Do hospital-level failures look the same across clinical
departments, or does each specialty have its own failure mode?

**Key insight:** Oncology carries the network's highest mortality rate, likely
reflecting the severity of patients on arrival rather than a process failure.
Cardiology has the highest readmission rate, echoing King's College's
hospital-level finding from Page 3: the discharge-planning gap shows up by
specialty as well as by hospital. Mental Health patients face the network's
longest treatment delays (86 minutes), pointing to an access problem rather than
a severity one.

**Recommendation:** Each specialty needs a tailored intervention rather than one
network-wide polic: faster access pathways in Mental Health, tighter discharge
protocols in Cardiology and Geriatrics, and further investigation into whether
Oncology's mortality figure reflects casemix severity, pathway delay, or both.
But department-level failure is still one step removed from the patient. The
final page checks whether the underlying diagnosis is reaching the right
department in the first place.

![Department](./Dashboards/Code%20Blue%20—%20Emergency%20Operations%20&%20Patient%20Flow%20Analytics_C38_Department.jpg)

---

### Page 5 — Diagnosis: Is the Right Patient in the Right Department?

**Question answered:** Do the diagnoses with the worst outcomes line up with the
departments built to treat them or is the network routing patients to the
wrong place?

**Key insight:** Neurological conditions carry the network's highest mortality
rate (4.91%) but not its longest length of stay — suggesting acute severity
rather than prolonged deterioration. Substance Abuse drives the highest
readmission rate (18.97%). Endocrine/Diabetes patients stay the longest, an
average of 44 hours. None of these three findings overlap, meaning each failure
mode has its own diagnostic signature rather than one diagnosis driving every
metric.

The Diagnosis × Department matrix is the page's central finding: Emergency
Department absorbs the highest patient volume across 11 of the network's 13
diagnosis categories including Cardiovascular, Respiratory, and Neurological
presentations that specialist departments exist to treat. Emergency isn't just
the busiest department in the network; it is functioning as a catch-all for
conditions that should be routed to specialist care, which helps explain why it
can never fully clear its queue.

**Recommendation:** Fixing hospital-level and department-level pressure won't
hold if the underlying routing problem isn't addressed, patients need to reach
the correct department on the first pass, not after Emergency absorbs them by
default.

![Diagnosis](./Dashboards/Code%20Blue%20—%20Emergency%20Operations%20&%20Patient%20Flow%20Analytics_C38_Diagnosis.jpg)

---

## Repository Contents

```
📁 Code-Blue-Emergency-Operations-Patient-Flow-Analytics
│
├── 📄 README.md
└── 📁 screenshots/
    ├── page1_pulse.png
    ├── page2_operations.png
    ├── page3_impact.png
    ├── simulator.gif
    ├── page4_department.png
    └── page5_diagnosis.png
```

---

## Tools Used

| Tool | Purpose |
|---|---|
| Power BI Desktop | Report building, visualisation, data modelling |
| DAX | Calculated measures, conditional formatting, dynamic recommendation text |
| Power Query (M) | Row-level transforms, custom date table, data cleaning |

---

## Dataset Structure

**Fact tables:**
- `Fact_Patient_Visits` - one row per patient visit, covering wait time, triage
  delay, treatment delay, length of stay, severity level, admission type,
  mortality flag, and 30-day readmission flag
- `Fact_Staffing` - one row per hospital per shift, covering overtime hours,
  burnout index, and absence rate
- `Fact_Financials` - one row per hospital per month, covering cost per visit,
  revenue per visit, and bed occupancy rate

**Dimension tables:** `Dim_Hospital`, `Dim_Date`, `Dim_Department`, `Dim_Region`,
`Dim_Patient`, `Dim_Doctor`, `Dim_Diagnosis`, plus a `Vocabulary` table used to
drive field-parameter toggles.

---

## Key DAX Measures

### Core KPIs

```dax
Total Visits =
COUNTROWS(Fact_Patient_Visits)

Avg Wait Time =
AVERAGE(Fact_Patient_Visits[Wait_Time_Minutes])

Avg Bed Occupancy =
AVERAGE(Fact_Financials[Bed_Occupancy_Rate])
```

### Time Intelligence

```dax
-- Year-over-year change in average wait time
Wait YoY % =
VAR CurrentVal = [Avg Wait Time]
VAR PY = [Wait PY Value]
RETURN
    DIVIDE(CurrentVal - PY, PY, BLANK())

-- Month-over-month change in average wait time
Wait MoM % =
VAR CurrentVal = [Avg Wait Time]
VAR PrevMonth =
    CALCULATE(
        [Avg Wait Time],
        DATEADD(Dim_Date[Full_Date_Parsed], -1, MONTH)
    )
RETURN
    DIVIDE(CurrentVal - PrevMonth, PrevMonth, BLANK())
```

### Pressure & Risk Scoring

```dax
-- Composite score: 40% wait time, 30% bed occupancy, 30% mortality,
-- each normalised against the network maximum
Operational Pressure Score =
VAR WaitScore =
    DIVIDE(
        [Avg Wait Time],
        CALCULATE(MAXX(VALUES(Dim_Hospital[Hospital_Name]),
            [Avg Wait Time]), ALL(Dim_Hospital))
    ) * 40
VAR OccScore =
    DIVIDE(
        [Avg Bed Occupancy],
        CALCULATE(MAXX(VALUES(Dim_Hospital[Hospital_Name]),
            [Avg Bed Occupancy]), ALL(Dim_Hospital))
    ) * 30
VAR MortScore =
    DIVIDE(
        [Mortality Rate],
        CALCULATE(MAXX(VALUES(Dim_Hospital[Hospital_Name]),
            [Mortality Rate]), ALL(Dim_Hospital))
    ) * 30
RETURN
    ROUND(WaitScore + OccScore + MortScore, 2)

Pressure Category =
IF([Operational Pressure Score] >= 80, "Critical",
IF([Operational Pressure Score] >= 65, "At Risk",
IF([Operational Pressure Score] >= 50, "Stable",
"Performing")))
```

### Conditional Formatting

```dax
-- Returns a hex colour: red for the worst hospital, green for the best,
-- black for everyone in between. Same pattern used across Triage Delay,
-- Treatment Delay, LOS, Burnout, Overtime, Bed Occupancy and Readmission Rate
Mortality Rate Colour =
VAR MaxVal =
    CALCULATE(
        MAXX(VALUES(Dim_Hospital[Hospital_Name]), [Mortality Rate]),
        ALL(Dim_Hospital)
    )
VAR MinVal =
    CALCULATE(
        MINX(VALUES(Dim_Hospital[Hospital_Name]), [Mortality Rate]),
        ALL(Dim_Hospital)
    )
RETURN
SWITCH(
    TRUE(),
    [Mortality Rate] = MaxVal, "#ff4200",
    [Mortality Rate] = MinVal, "#51A25A",
    "black"
)
```

### Cost of Inaction

```dax
-- Patients waiting over 4 hours, multiplied by the cost of treating them
Cost of Long Wait Visits =
VAR CostPerVisit = [Cost per Visit]
VAR LongWaitVisits =
    COUNTROWS(
        FILTER(
            Fact_Patient_Visits,
            Fact_Patient_Visits[Wait_Time_Minutes] > 240
        )
    )
RETURN
    CostPerVisit * LongWaitVisits

-- Emergency readmissions within 30 days, valued at cost per visit
Readmission Financial Cost =
VAR EmergencyReadmissions =
    CALCULATE(
        COUNTROWS(Fact_Patient_Visits),
        Fact_Patient_Visits[Readmission_30_Days_Flag] = TRUE(),
        Fact_Patient_Visits[Admission_Type] = "Emergency"
    )
RETURN
    EmergencyReadmissions * [Cost per Visit]
```

### Dynamic Recommendation Text

Each of the three priority cards on Page 3 is a single measure that rewrites
itself based on the current filter context  if filtered to NHS-only or
2025-only, the hospital named and the numbers quoted update automatically.

```dax
Rec 1 Text =
VAR SandwellWait =
    CALCULATE([Avg Wait Time], Dim_Hospital[Hospital_Name] = "Sandwell General Hospital")
VAR SandwellMort =
    CALCULATE([Mortality Rate], Dim_Hospital[Hospital_Name] = "Sandwell General Hospital")
VAR SandwellOcc =
    CALCULATE([Avg Bed Occupancy], Dim_Hospital[Hospital_Name] = "Sandwell General Hospital")
RETURN
    "Activate an Immediate Surge Protocol at Sandwell General Hospital. " &
    "Sandwell is the only hospital in the network simultaneously flagged as Critical on staffing stress, " &
    "wait time (" & FORMAT(SandwellWait, "0") & " mins), " &
    "bed occupancy (" & FORMAT(SandwellOcc, "0%") & "), " &
    "and mortality (" & FORMAT(SandwellMort, "0.00%") & "). " &
    "A pre-agreed diversion protocol, fast-discharge pathway for non-urgent patients, " &
    "and emergency staffing reinforcement must be triggered immediately."
```

```dax
Rec 2 Text =
VAR ImmediateWait = CALCULATE([Avg Triage Delay], Fact_Patient_Visits[Severity_Level] = 1)
VAR NonUrgentWait = CALCULATE([Avg Triage Delay], Fact_Patient_Visits[Severity_Level] = 5)
VAR Gap = ImmediateWait - NonUrgentWait
RETURN
    "Commission a Network-Wide Triage Audit. " &
    "Severity 1 (Immediate) patients wait " & FORMAT(ImmediateWait, "0") & " minutes at triage, " &
    FORMAT(Gap, "0") & " minutes longer than non-urgent Severity 5 patients who wait only " &
    FORMAT(NonUrgentWait, "0") & " minutes. " &
    "The most critically ill patients are being assessed last. " &
    "This is a clinical governance failure requiring immediate triage protocol review at all 11 network hospitals."
```

```dax
Rec 3 Text =
VAR HighReadmitHospital =
    CALCULATE(
        FIRSTNONBLANK(Dim_Hospital[Hospital_Name], 1),
        TOPN(1, SUMMARIZE(Fact_Patient_Visits, Dim_Hospital[Hospital_Name], "RR", [Readmission Rate]), [RR], DESC)
    )
VAR HighReadmitRate =
    CALCULATE(
        [Readmission Rate],
        TOPN(1, SUMMARIZE(Fact_Patient_Visits, Dim_Hospital[Hospital_Name], "RR", [Readmission Rate]), [RR], DESC)
    )
VAR NetworkReadmit = [Readmission Rate]
VAR FinancialCost = [Readmission Financial Cost]
RETURN
    "Invest in Structured Discharge Planning Across the Network. " &
    HighReadmitHospital & " records the highest 30-day readmission rate at " &
    FORMAT(HighReadmitRate, "0.0%") & " against a network average of " &
    FORMAT(NetworkReadmit, "0.0%") & ". " &
    "The financial cost of emergency readmissions across the network is " &
    FORMAT(FinancialCost, "£#,##0") & ". " &
    "Structured discharge checklists, 7-day community follow-up calls, " &
    "and telemedicine check-ins within 72 hours of discharge would reduce this burden " &
    "without requiring new infrastructure investment."
```

### What-If Simulator

Three What-If parameters drive sliders on Page 3. Each slider's underlying
result is calculated by one measure, and a second measure converts that result
into a plain-language sentence.

```dax
Patients Breaching Triage Target =
COUNTROWS(
    FILTER(
        Fact_Patient_Visits,
        Fact_Patient_Visits[Triage_Delay_Minutes] > [Triage Target Minutes Value]
    )
)

Rec 1 Dynamic =
VAR Target = [Triage Target Minutes Value]
VAR Breaches = [Patients Breaching Triage Target]
RETURN
    "If the triage target is set to " & FORMAT(Target, "0") &
    " minutes, " & FORMAT(Breaches, "#,##0") &
    " patients currently fall outside this threshold and would require " &
    "intervention to bring the network into compliance."
```

```dax
Projected Savings =
VAR ReductionFactor = [Wait Reduction Target Value]
VAR CurrentCost = [Cost of Long Wait Visits]
RETURN
    CurrentCost * ReductionFactor

projected savings Dynamic =
VAR ReductionFactor = [Wait Reduction Target Value]
VAR CurrentCost = [Cost of Long Wait Visits]
VAR Savings = [Projected Savings]
RETURN
    "Reducing wait times by " & FORMAT(ReductionFactor, "0%") &
    " from their current level would save an estimated " &
    FORMAT(Savings, "£#,##0") &
    " against a current cost of long-wait visits of " &
    FORMAT(CurrentCost, "£#,##0") & "."
```

```dax
Months in Surge =
CALCULATE(
    COUNTROWS(Fact_Financials),
    FILTER(
        Fact_Financials,
        Fact_Financials[Bed_Occupancy_Rate] > [Bed Occupancy Threshold Value]
    )
)

Surge Frequency Text =
VAR Instances = [Months in Surge]
VAR PerMonth = DIVIDE(Instances, 24, 0)
RETURN
    "At " & FORMAT([Bed Occupancy Threshold Value], "0%") &
    " occupancy, this threshold was crossed " &
    FORMAT(Instances, "#,##0") &
    " times across the network in the past two years, that's roughly " &
    FORMAT(PerMonth, "0.0") &
    " hospitals over capacity every month."
```

---

## Power Query Tables

All row-level columns were created in Power Query rather than DAX, keeping the
measures table focused on aggregation and conditional logic. Key transforms
include:

- **`Fact_Patient_Visits`** - Arrival_Date / Hour / DayOfWeek / Shift, Wait_Band,
  Severity_Label, Is_High_Severity, Triage_Delay_Minutes, Is_Long_Wait, LOS_Band,
  Month_Year, and Outcome_Group
- **`Fact_Staffing`** - Total_Clinical_Staff, Absence_Rate, Burnout_Band,
  Overtime_Flag, and Shift_Sort (for correct AM/PM/Night ordering)
- **`Fact_Financials`** - Cost_Per_Visit, Revenue_Gap, Occupancy_Band, and a
  Date_Key column to fix the relationship to `Dim_Date`
- **`Dim_Date`** - a full custom date table built via Power Query script, plus
  Month_Year_Label and Month_Year_Sort
- **`Dim_Hospital`** - Stress_Sort, Hospital_Short, and Is_NHS

---

## What I Learned

**Dynamic text turns a static report into a tool.** Writing the three priority
recommendations as measures, rather than text boxes, means they update if a
viewer filters by year, region, or ownership type, the report keeps making
sense under filters instead of becoming misleading.

**A finding that doesn't repeat is still a finding.** Page 4 was built expecting
department-level failures to mirror hospital-level ones. They didn't. Oncology,
Cardiology, and Mental Health each fail in a different way, for a different
reason, requiring a different fix.

**A number that breaks its own logic is worth investigating, not hiding.**
Spotting that Treatment Delay could exceed Wait Time meant the relationship
between two fields couldn't be taken at face value. Reframing the metric rather
than quietly dropping it kept the finding intact while being honest about what
the data could and couldn't support.

---

## Links
[![Medium](https://img.shields.io/badge/Medium-12100E?style=for-the-badge&logo=medium&logoColor=white)](https://medium.com/@johannaezedinma) [![GitHub](https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/Johanna-Ezedinma) 
[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/johanna-ezedinma/)



**Challenge:** [(FP20 Analytics Challenge 38](https://fp20analytics.com/live-challenge/)]

---

## Author


**Johanna Ezedinma**

[![GitHub](https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/Johanna-Ezedinma) [![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/johanna-ezedinma/)   
