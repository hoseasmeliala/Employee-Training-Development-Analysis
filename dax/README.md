# DAX Analytical Measures

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

## Training Participants
```
Training Participants =
DISTINCTCOUNT(FactTraining[EmployeeID])
```

---

## Training Participation Rate    
```
Training Participation Rate =
DIVIDE(
    [Training Participants],
    DISTINCTCOUNT(DimEmployee[EmployeeID]),
    0
)
```
---

## Average Training Hours per Participant
```
Average Training Hours per Participant =
DIVIDE(
    SUM(FactTraining[TrainingHours]),
    DISTINCTCOUNT(FactTraining[EmployeeID]),
    0
)
```

---

## Employees Low Training Exposure   
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

## Learning Improvement  
```
Learning Improvement =
AVERAGE(FactTraining[PostTrainingScore])
-
AVERAGE(FactTraining[PreTrainingScore])
```

--- 

## Training Completion Rate  
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


## Total Training Cost 
```
Total Training Cost =
SUM(FactTraining[TrainingCost])
```

---

## Cost per Participant  
```
Cost per Participant =
DIVIDE(
    SUM(FactTraining[TrainingCost]),
    DISTINCTCOUNT(FactTraining[EmployeeID]),
    0
)
```

---


