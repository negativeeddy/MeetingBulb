# MeetingBulb
For my blog post https://blog.negativeeddy.com/2020/03/30/wfh-diy-meeting-light-bulb/ describing my quick solution to turn a light bulb on/off based on my O365 Calendar schedule ("Light on" == I'm in a meeting)

This is an ARM template which deploys the Logic App portion of the solution. The logic app checks my "busy" status on my calendar on a schedule. If I am busy it, calls a webhook which turns a wifi light bulb on/off in my house. That way, my family knows I'm unavailable/available (and doesnt have to poke their head in and mime "are you on the phone?!?" all the time). 

[![Deploy to Azure](https://aka.ms/deploytoazurebutton)](https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2Fnegativeeddy%2FMeetingBulb%2Fmaster%2Fazuredeploy.json)

[![Visualize](https://raw.githubusercontent.com/Azure/azure-quickstart-templates/master/1-CONTRIBUTION-GUIDE/images/visualizebutton.png)](http://armviz.io/#/?load=https%3A%2F%2Fraw.githubusercontent.com%2Fnegativeeddy%2FMeetingBulb%2Fmaster%2Fazuredeploy.json)

When first deployed, the "Get calendar view of events" activity will fail because it has not been authorized. Open the logic app editor and expand the Connections node. Then click the "!" under "invalid." That will initiate the authentication flow.

You can find your calendar ID by using the [Graph Explorer](https://developer.microsoft.com/en-us/graph/graph-explorer) and running the query "https://graph.microsoft.com/v1.0/me/Calendars"
