# customer_retention
This is a dataset of customers who have churn or not churned from a call company
Started the analysis by filtering the columns to check for missing values and duplicates that may affect my analysis.
removed duplicates and deleted the missing values.
inserted coulumns calloed the churn flag and churned so i can use it to cal for a measure in power bi
=IF(AND(F8=MAX($F$2:$F$7033)-1, I8="yes"), "lastmonth", "other") to calculate churned
=COUNTIF(I3,"yes") to cal churn flag
=IF(F4<=12, "0-12 months", IF(F4<=24, "13-24 months", IF(F4<=36, "25-36 months", IF(F4<=48, "37-48 months", IF(F4<=60, "49-60 months", "61-72 months"))))) to cal tenure group
ChurnRate = [total_churned] / COUNT('01 Churn-Dataset'[count]) * 100
total_churned = SUM('01 Churn-Dataset'[Churn_flag])
