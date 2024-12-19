This folder contains testing lists. Utilize the below dataview table to generate tests for the week:
```dataview
TABLE file.outlinks as "Subjects to Test"
FROM #log and -"Zarchives"
LIMIT 7
```