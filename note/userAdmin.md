
####Goal: to run a php script that can add new "User" and "Website" as piwik administer

####Detail:
1. Create new piwik user
2. Account management
	- add,
	- edit,
	- delete
3. Superuser can assign administration authority to lower user
4. Website management
	- add,
	- edit,
	- delete
5.	other website setting......
6. "user" associate "website", with permission to view data, information......

**Attention**
when each website added, need to generate tracking code for new website


####key point:
1. need to access piwik database and modify the correspond table (such as add "user" and "website")  
2. (need to know how to call piwik API in php or other script)  
3. find out what modal/APIs/functions might need.   
Here is for classes list(http://developer.piwik.org/api-reference/classes)

	("acess") (http://developer.piwik.org/api-reference/Piwik/Access)

        $view->clientSideConfig = PiwikConfig::getInstance()->getClientSideOptions();
        $view->enableMeasurePiwikForSiteId = PiwikConfig::getInstance()->Debug['enable_measure_piwik_usage_in_idsite'];
        $view->isSuperUser = Access::getInstance()->hasSuperUserAccess();
        $view->hasSomeAdminAccess = Piwik::isUserHasSomeAdminAccess();
        $view->hasSomeViewAccess  = Piwik::isUserHasSomeViewAccess();
        $view->isUserIsAnonymous  = Piwik::isUserIsAnonymous();
        $view->hasSuperUserAccess = Piwik::hasUserSuperUserAccess();
		
		        if (!Piwik::isUserIsAnonymous()) {
            $view->emailSuperUser = implode(',', Piwik::getAllSuperUserAccessEmailAddresses());
        }
		
		
	C:\xampp\htdocs\piwik\piwik\core\Settings\.....
	C:\xampp\htdocs\piwik\piwik\core\Access.php
	
	
http://piwik.org/docs/manage-users/
Analytics Web API (http://piwik.org/docs/analytics-api/)
Call piwik API (http://developer.piwik.org/guides/querying-the-reporting-api)

####In "plugin" related with user right

		Dashboard 
		Login 



