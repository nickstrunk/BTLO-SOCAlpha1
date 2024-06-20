<h1>SOC Alpha 1</h1>

 <!-- ### [YouTube Demonstration](https://youtu.be/7eJexJVCqJo)/> -->

<h2>Description</h2>
You are a SOC analyst and handling the alerts within your SIEM, ELK, is part of daily duties. Answer the following questions by analysing the alerts provided in README.txt!
<br />


<h2>Languages and Utilities Used</h2>

- <b>ELK</b>
- <b>Splunk</b>

<h2>Environments Used </h2>

- <b>Linux</b>

<h2>Program walk-through:</h2>

<p align="center">

<h3>Q1) Alert 1 (1/2) - What is the cmdlet used for downloading? </h3>
<b>Analyze README file and Kibana</b> <br />
** Search Kibana >  Analytics > Discover > Update search index to winevent-powershell > Search time frame of alert > Search Rule of Alert 1<br />
** OSINT Invoke-WebRequest -  cmdlet to send HTTP and HTTPS requests<br />
** ANSWER TO Q1) Invoke-WebRequest <br /> <br />
<img src="https://github.com/nickstrunk/SOCAlpha1/assets/165805194/d36f5357-61c2-4da8-9ff5-726f422af84d" height="80%" width="80%" alt="Download cdmlet/>
<br />
<br />

<h3>Q2) Alert 1 (2/2) - What is the full URL from which the file is downloaded? </h3>
<b>Analyze Alert Data in Kibana</b> <br />
** Displayed is the URI of the Invoke-WebRequest<br /> 
** ANSWER TO Q2) hxxps[://]raw[.]githubusercontent[.]com/nerrorsec/SBT-SOC/main/MSWorker.exe <br /> <br />
<img src="https://github.com/nickstrunk/SOCAlpha1/assets/165805194/9b7713b6-c0e1-43f8-bb5d-3b6a9d4b3a1b" height="80%" width="80%" alt="URL of File"/>
<br />
<br />


<h3>Q3) Alert 2 (1/1) - What is the name of the suspicious EXE that is added for Persistence? </h3>
<b>Inspect Previous Alert in Kabana and README file</b> <br />
** Parameter -OutFile shows program probably stored in Temp folder <br /> 
** Searching Kibana using alert 2 source and rule > Displays Sysmon Event ID 11 - File creation operations > Executable stored in Startup Folder<br />
** ANSWER TO Q3) MSWorker.exe <br /> <br />
<img src="https://github.com/nickstrunk/SOCAlpha1/assets/165805194/965d18ac-4491-4f7d-9b6e-8c0f9d0670cc" height="80%" width="80%" alt="Persistence Exe"/>
<br />
<br />

<h3>Q4) Alert 3 (1/2) - What is the name of the suspicious executable file involved? </h3>
<b>Inspect Alert in Kabana and README file</b> <br />
** Searching Kibana using alert 3 source and rule ><br />
** Sysmon Events 12, 13, and 14 > OSINT shows events involve Windows Registry <br />
** Alert contains Sysmon Event 13 <br />
- /t REG_SZ = specifies type of registry <br />
- /F /D C:\Windows\sevices.exe = adds registry without prompt and specifies the new data <br />
** ANSWER TO Q4) service.exe <br /> <br />
<img src="https://github.com/nickstrunk/SOCAlpha1/assets/165805194/f3d099e9-4011-4c50-8553-54d62090d55a" height="80%" width="80%" alt="Services Executable"/>
<br />
<br />

<h3>Q5) Alert 3 (2/2) - What is the name of the key path? </h3>
<b>Analyze Registry Path</b> <br />
** Registry is made out of Keys and Sub Keys and has paths similar to files <br /> 
** Look at the last entry in the path <br />
** ANSWER TO Q5) Service <br /> <br />
<img src="https://github.com/nickstrunk/SOCAlpha1/assets/165805194/bb56bdc4-e458-4a69-a1c6-ca29940c3e84" height="80%" width="80%" alt="PHP File"/>
<br />
<br />

<h3>Q6) Alert 4 (1/2) - What is the name of the task? </h3>
<b>Inspect Alert in Kabana and README file </b> <br />
** Observe "SchTasks" command used ("SchTasks Create") <br />
- /SC Daily = run everyday <br />
- /TN "MyTask" = task name <br />
- /TR "C:\Program Files\GameLoaderGen\gen.bat" = program to run <br />
** ANSWER TO Q6) My Task <br /> <br />
<img src="https://github.com/nickstrunk/SOCAlpha1/assets/165805194/3d8b9a5d-eb0d-4766-85c8-dc8ee320368e" height="80%" width="80%" alt="PHP File Function"/>
<br />
<br />

<h3>Q7) Alert 4 (2/2) - What is the full path of the program? </h3>
<b>Inspect Alert in Kabana and README file </b> <br />
** Parameter /TR is provided with the program to run <br /> 
** ANSWER TO Q7) C:\Program Files\GameLoaderGen\gen.bat <br /> <br />
<img src="https://github.com/nickstrunk/SOCAlpha1/assets/165805194/51b75438-1659-4161-a959-3be13a900adb" height="80%" width="80%" alt="PHP Variable Function"/>
<br />
<br />

</p>

<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
