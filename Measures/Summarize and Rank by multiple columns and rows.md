TableSummarize = SUMMARIZECOLUMNS(Table1[Client Name], Table1[Revenue Stream], "Total Revenue", SUM(Table1[Total Revenue]) )
Rank = RANKX(Filter(TableSummarize, TableSummarize[Revenue Stream] = EARLIER(TableSummarize[Revenue Stream])),TableSummarize[Total Revenue],,DESC,Dense)

https://community.powerbi.com/t5/Desktop/Summarize-and-Rank-by-multiple-columns-and-rows/m-p/330108
