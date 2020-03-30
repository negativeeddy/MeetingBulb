# MeetingBulb

[![Deploy to Azure](http://azuredeploy.net/deploybutton.png)](https://azuredeploy.net/)

When first deployed, the "Get calendar view of events" activity will fail because it has not been authorized. Open the logic app editor and expand the Connections node. Then click the "!" under "invalid." That will initiate the authentication flow.

You can find your calendar ID by using the [Graph Explorer](https://developer.microsoft.com/en-us/graph/graph-explorer) and running the query "https://graph.microsoft.com/v1.0/me/Calendars"
