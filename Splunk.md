To determine the indices that are available to us in Splunk, we can run the following:

| eventcount summarize=false index=* | dedup index | fields index

In Splunk, we can use the search function to locate information from various logs.

search: index="datasource" earliest=0

We are searching through a specific data source from the earliest data set. We could also use the All Time option on the Data Range list on the left hand side.

We can select a slice of the data by selection 1:100 or 1:1000 etc or use all the data by not filtering.

Once all the data has been loaded, there will be some fields listed by Splunk. We can use these to dig deeper into the data. 

https://user-images.githubusercontent.com/89241760/151162865-e9c7d7dc-94bd-40c6-b96c-5d9cec537892.png

The simplest search we can conduct is for a field and a value, for example, searching against our data for the source IP field (src) and the IP address value 10.10.10.50.

search src="10.10.10.50"

If we wanted to look for any logs or network traffic associated with this IP, we could also search for logs where the destination IP is stated as 10.10.10.50:

search src="10.10.10.50" OR dst="10.10.10.50"

Using the following simple query we could see what traffic is being directed towards the web server:

search dst="10.10.100.5"

While this would show us any logs where the destination IP is the web server, it will also show any other logs or traffic going to that server, which could result in a lot of logs that we are not interested in. We can apply additional arguments in our search query to perform actions such as filtering on HTTP traffic only.

What is a wildcard? A wildcard operator is the asterisk character (*) that can be used to mean anything. To explain what we mean, let’s go through another example. Security analysts determine that the host 10.10.10.73 has been compromised by a malicious actor, and that the next likely step in their plan is to search for other systems in that network (10.10.10.0/24). Using Splunk, we could see if the infected host has communicated with any of the other hosts using the query:

search src="10.10.10.73" dst="10.10.10.*"

We could also use this to look for words that may have different versions, such as “pass” and “password”. For example, we could search for logs that contain information about login failures with the following:

search pass* AND fail*
So with this query, it will return any logs that contain the following:

“pass” “fail”
“password” “fail”
“pass” “failure”
“password” “failure”

index="botsv1" earliest=0 Image="*\\cmd.exe" | stats values(CommandLine) by host

The above search query is using a new parameter, “Image=”. This is derived from Sysmon logs, such as Event ID 1, ‘New Process Created’. The Image field in Sysmon events shows the executable that has generated the process, in this example, cmd.exe, which should be located at C:\Windows\System32\cmd.exe (but we can wildcard the path). After the search for cmd.exe, we’re retrieving the events using values(CommandLine) to show what commands were used, and finally sorting it per host. Let’s see how this search looks once it has been run (with no event sampling):

https://user-images.githubusercontent.com/89241760/151165504-3e51bd97-945f-44c7-ab81-2f5be0f8379a.png


Use the following search query to identify the malicious activity (for a specific data set):

index="botsv1" sourcetype="stream:http" http_method=POST uri="/joomla/administrator/index.php"

The below will allow you to add a specific timestamp to your query. 

| spath timestamp | search timestamp="2016-08-10T21:46:44.453730Z"

Remove the details about timestamps from your search query and add the following 

| table timestamp,form_data

This adds a new nice tabular format, where you can view the most recent or oldest in a very simple way.

If we know that a site has been defaced or attacked from the web, we assume then that the web server is then the client IP, so we could use the following query to determine where the defacement file was downloaded from. 

c_ip=IP 
| stats count by url

Splunk has a built in stream to find brute force attacks against a server.

sourcetype=stream:http dest=”<IP address receiving the request>” http_method=POST |stats count BY src, form_data, status

If we want to find out what the file that was uploaded as part of an attack is and we know the host attacked, we can use the following query:
 
index=botsv1 sourcetype=stream:http dest=”IP″ “multipart/form-data” | head 1
 
and alternative query to the above is:

 index=”botsv1″ dest_ip=192.168.250.70 sourcetype=”stream:http” POST *.exe
 
 To find the md5 hash of a file using Splunk, we could run the following:
 
 name of executable sourcetype=XmlWinEventLog:Microsoft-Windows-Sysmon/Operational EventCode=1 CommandLine="name of executable"
|stats values(MD5)




