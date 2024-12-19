[Roadmap Projects](https://roadmap.sh/projects)
## Active Projects
```dataview
TABLE project_subject as "Subject", estimated_time as "Etimated Time", tracked_time as "Tracked Time"
FROM #activeproject and -"Zarchives"
```
## Completed Projects
```dataview
TABLE project_subject as "Subject", estimated_time as "Original Estimate", tracked_time as "Tracked Time", start_date as "Started On", completion_date as "Completed On"
FROM #finishedproject and -"Zarchives"
```