Revenue Avg 7D =
VAR MaxDate = MAX ( 'Dates'[Date] )
VAR AvgVal =
CALCULATE (
AVERAGEX (
VALUES ( 'Dates'[Date] ),
[Revenue]
),
DATESINPERIOD ( Dates[Date], MaxDate, -7, DAY )
)
RETURN
AvgVal
Revenue Diff 7D =
VAR CurrVal = [Revenue]
VAR AvgVal = [Revenue Avg 7D]
RETURN
CurrVal - AvgVal
