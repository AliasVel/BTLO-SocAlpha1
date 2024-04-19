<h1>Blue Team Labs Online - Soc Alpha 1 lab</h1>

<h2>Description</h2>
Project consists handling alerts within my SIEM, ELK, as part of daily duties as a SOC Analyst. Questions were given based on the alerts that were left in a README.txt file for me to analyze.
<br />


<h2>Utilities Used</h2>

- <b>ELK/Kibana</b> 
- <b>ElasticSearch</b>

<h2>Lab walk-through:</h2>

<!-- <p align="center"> -->
Understanding the objective: <br/> The README.txt file tells us which alerts to look into. <br/>
<img src="https://i.imgur.com/epP76u8.png" height="80%" width="80%" alt="reading the README.txt file"/>
<br />
<br />
  
<b>Alert 1 (A1):</b>  <br/> The README.txt file informs us that  A1's source is winevent-powershell, the rule is  ("*.DownloadFile*" OR "*.DownloadString*" OR "*Invoke-WebRequest*"), and the timframe is (14-4-2021 10:00 to 4-14-2021 11:00). With this information, we can filter out the logs we need to view.
<img src="https://i.imgur.com/L4jGsfV.png" height="80%" width="80%" alt="Filtering data for alert 1"/>
<br />
Questions regarding A1: <br/>
 <b>What is the cmdlet used for downloading? </b><br/>
   The cmdlet used is Invoke-WebRequest <br/><br/>
<b>What is the full URL from which the file is downloaded? </b><br/>
   The full url is https://raw.githubusercontent.com/nerrorsec/SBT-SOC/main/MSWorker.exe.
<br />
<br />

<b>Alert 2 (A2):</b> <br/> The README.txt file informs us that A2's source is sysmon, the rule is (Event_System_EventID :"11" AND Event_EventData_Image : *Windows\\Start*\\Programs\\Startup*), and the timframe is (14-4-2021 10:30 to 14-4-2021 13:00)
<img src="https://i.imgur.com/Ihd0UZ5.png" height="80%" width="80%" alt="Filtering data for alert 2"/>
<br />
Questions regarding A2: <br/>
 <b>What is the name of the suspicious EXE that is added for Persistence? </b><br/>
   The suspicious EXE is MSworker.exe <br/><br/>
<br />

<b>Alert 3 (A3):</b>  <br/> The README.txt file informs us that A3's source is sysmon, the rule is (Event_System_EventID:("12" OR "13" OR "14") AND (Event_EventData_TargetObject:("*\\SOFTWARE\\Wow643 OR "*\\Software\\Wow6432Node\\Microsoft\\Command*Processor\\Autorun*" OR "*\\SOFTWARE\\Wow6432Node\\ OR "*\\SOFTWARE\\Microsoft\\Windows*CE*Services\\AutoStartOnDisconnect*" OR "*\\SOFTWARE\\Microsoft))), and the timframe is (15-4-2021 08:00 to 15-4-2021 09:00)
<img src="https://i.imgur.com/fvTUvKJ.png" height="80%" width="80%" alt="Filtering data for alert 3"/>
<br />
Questions regarding A3: <br/>
 <b>What is the name of the suspicious executable file involved? </b><br/>
  The name of the suspicious executable file involved is service.exe <br/><br/>
<b>What is the name of the key path? </b><br/>
   The name of the key path is Service
<br/>
<br />

<b>Alert 4 (A4):</b>  <br/> The README.txt file informs us that A3's source is sysmon, the rule is Event_EventData_Image:*schtasks.exe* AND Event_EventData_CommandLine:*Create*, and the timframe is (20-4-2021 10:00 to 20-4-2021 15:00)
<img src="https://i.imgur.com/FL1P8RV.png" height="80%" width="80%" alt="Filtering data for alert 4"/>
<br />
Questions regarding A4: <br/>
 <b>What is the name of the task? </b><br/>
  The name of the task is My Task <br/><br/>
<b>What is the full path of the program? </b><br/>
   The full path of the program is C:\Program Files\GameLoaderGen\gen.bat
<br />
<br />

