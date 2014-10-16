The CLI tool has created a new file Reports/GetLastVisitsByBrowser.php within your plugin folder. 
We recommend to take the time to have a look at all the methods and comments to get an idea how a report is defined.


//////////////////////////////////////////////
Statistics logger（）
Users & Permissions（）
Site（）
Archived data（data）
Debug / Info log（test/info record）
SQL query profiling（SQL)


1. Statistics logger
--- log, from js, cookie, php

--- each visitor will be mark as unique "visitor_idcookie"

--- "log_visit" record user's each visit, eg a user visit a web twice, that will be
a two record.

--- each page as an "action", with a name and a type (log_action)

--- each user's new action will be recorded in "log_link_visit_action", also include
("idaction" and "idvisit"). This table also contain "idaction_ref" and "time_spent_ref_action"
for recording last action.
 
---If we require second page, program will get the last page's "idaction" from cookie and save it
as "action_ref", and record the time "time_spent_ref_action". That means we don't need to update 
the time of last record, only need to record current father page's infomation.








