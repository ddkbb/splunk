# splunk

navigate to the splunk console in the browser

select time frame on the right next to search button
index="wls"
  this searches for windows event logs

index="wls" EventID=4624 LogonType=2
  searches for specific events and types

index="wls" EventID=4624 LogonType=2
| dedup TargetUserName
| table_time, EventID, TargetUserName, Computer
  use | to add more commands
  dedup TargetUserName asks for unique users
  table_time, EventID, TargetUserName, Computer is tabling out fields

Earliest=10/15/2020:00:00:00 latest=10/15/2020:12:00:00 index=wls EventID=4624
  search in a specfic timeframe
