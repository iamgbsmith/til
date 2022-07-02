# Count Cells In Excel Matching A Value

__Category: Office__

You can count cells in an Excel worksheet column that match a specific value using the `COUNTIF` function.

For example, to count the number of cells in column C for rows 2 to 210 which match the string value "Upgrade":

```shell
=COUNTIF(C2:C210,"Upgrade")
```

To count the number of cells in column F for rows 2 to 300 which are greater than the numeric value 50:

```shell
=COUNTIF(F2:F300,">50")
```
