# 🧮 DAX & Analytical Layer

This section documents the DAX logic used to build the analytical layer of the Power BI project.

The DAX implementation consists of:

1. **DAX Calculated Table - DimDate**
2. **DAX Measures - Business KPI**
3. **DAX Measures - Label Display**

---
# 1. DAX Calculated Table - DimDate

## DimDate Column
| Column          | Purpose                              |
| --------------- | ------------------------------------ |
| Date            | Base calendar date                   |
| Year            | Year filtering                       |
| Month Number    | Chronological month sorting          |
| Month           | Month display                        |
| Quarter         | Quarterly analysis                   |
| Year Month      | Monthly trend analysis               |

The `DimDate` table provides a dedicated date dimension for time-based analysis, including year filtering, monthly analysis, quarterly analysis, and trend reporting.

## 1.1 - DimDate 
```
DimDate =
ADDCOLUMNS(
    CALENDAR(
        MIN(FactTraining[TrainingDate]),
        MAX(FactTraining[TrainingDate])
    ),
    "Year", YEAR([Date]),
    "Month Number", MONTH([Date]),
    "Month", FORMAT([Date], "MMM"),
    "Quarter", "Q" & FORMAT([Date], "Q"),
    "Year Month", FORMAT([Date], "YYYY-MM")
)
```



# 2. DAX Measures - Business KPI 

| Domain        | Measure                                | Purpose                    |
| ------------- | -------------------------------------- | -------------------------- |
| Workforce     | Training Participants                  | Count unique participants  |
| Participation | Training Participation Rate            | Measure coverage           |
| Development   | Average Training Hours per Participant | Measure exposure           |
| Development   | Employees Low Training Exposure        | Identify low exposure      |
| Effectiveness | Learning Improvement                   | Pre vs post score change   |
| Completion    | Training Completion Rate               | Completion performance     |
| Investment    | Total Training Cost                    | Total investment           |
| Investment    | Cost per Participant                   | Investment per participant |

---

## 2.1 - Training Participants
```
Training Participants =
DISTINCTCOUNT(FactTraining[EmployeeID])
```

---

## 2.2 - Training Participation Rate    
```
Training Participation Rate =
DIVIDE(
    [Training Participants],
    DISTINCTCOUNT(DimEmployee[EmployeeID]),
    0
)
```

---

## 2.3 - Average Training Hours per Participant
```
Average Training Hours per Participant =
DIVIDE(
    SUM(FactTraining[TrainingHours]),
    DISTINCTCOUNT(FactTraining[EmployeeID]),
    0
)
```

---

## 2.4 - Employees Low Training Exposure   
```
Employees Low Training Exposure =
COUNTROWS(
    FILTER(
        VALUES(DimEmployee[EmployeeID]),
        CALCULATE(
            SUM(FactTraining[TrainingHours])
        ) < 30
    )
)
```

---

## 2.5 - Learning Improvement  
```
Learning Improvement =
AVERAGE(FactTraining[PostTrainingScore])
-
AVERAGE(FactTraining[PreTrainingScore])
```

--- 

## 2.6 - Training Completion Rate  
```
Training Completion Rate =
DIVIDE(
    CALCULATE(
        COUNTROWS(FactTraining),
        FactTraining[CompletionStatus] = "Completed"
    ),
    COUNTROWS(FactTraining),
    0
)
```

---


## 2.7 - Total Training Cost 
```
Total Training Cost =
SUM(FactTraining[TrainingCost])
```

---

## 2.8 - Cost per Participant  
```
Cost per Participant =
DIVIDE(
    [Total Training Cost],
    [Training Participants],
    0
)
```

---

# 3. DAX Measures - Label Display
Display measures are used only for **presentation formatting** in Power BI dashboard cards. They do not serve as primary analytical calculations.

| Measure | Purpose | Output Example | Used For |
|---|---|---|---|
| `Learning Improvement Label` | Formats the learning improvement value with a positive sign and readable decimal format | `+7.99` | KPI Card |
| `Cost Per Participant Label` | Converts cost per participant into a human-readable currency format | `Rp 7.0 Juta` | KPI Card |
| `Total Training Cost Label` | Converts total training cost into a readable Indonesian currency format | `Rp 6.5 Miliar` | KPI Card |

> **Note:** Analytical calculations are performed by the underlying KPI measures. Label measures are created separately to improve readability and presentation.

--- 

## 3.1 - Learning Improvement Label
```
Learning Improvement Label = 
VAR Improvement = [Learning Improvement]
RETURN
IF(
    Improvement > 0,
    "+" & FORMAT(Improvement, "0.000"), 
    FORMAT(Improvement, "0.000")
)
```

---

## 3.2 - Cost per Participant Label
```
Cost Per Participant Label = 
VAR CPP = [Cost per Participant]
RETURN
SWITCH(
    TRUE(),
    CPP >= 1000000000,
        "Rp " & FORMAT(CPP / 1000000000, "0.0") & " Miliar",
    CPP >= 1000000,
        "Rp " & FORMAT(CPP / 1000000, "0.0") & " Juta",
    CPP >= 1000,
        "Rp " & FORMAT(CPP / 1000, "0.0") & " Ribu",
    "Rp " & FORMAT(CPP, "#,##0")
)
```

---

## 3.3 - Total Training Cost Label
```
Total Training Cost Label = 
VAR Cost = [Total Training Cost]
RETURN
SWITCH(
    TRUE(),
    Cost >= 1000000000,
        "Rp " & FORMAT(Cost / 1000000000, "0.0") & " Miliar",
    Cost >= 1000000,
        "Rp " & FORMAT(Cost / 1000000, "0.0") & " Juta",
    Cost >= 1000,
        "Rp " & FORMAT(Cost / 1000, "0.0") & " Ribu",
    "Rp " & FORMAT(Cost, "#,##0")
)
```


---
