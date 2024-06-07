<h1>SOC Alpha 1</h1>

 <!-- ### [YouTube Demonstration](https://youtu.be/7eJexJVCqJo)/> -->

<h2>Description</h2>
You are a SOC analyst and handling the alerts within your SIEM, ELK, is part of daily duties. Answer the following questions by analysing the alerts provided in README.txt!
<br />


<h2>Languages and Utilities Used</h2>

- <b>ELK</b> 

<h2>Environments Used </h2>

- <b>Linux</b>

<h2>Program walk-through:</h2>

<p align="center">

<h3>Q1) Alert 1 (1/2) - What is the cmdlet used for downloading?</h3>
<b>Analyze README file </b> <br />
** Search Kibana >  Analytics > Discover > Update search index to winevent-powershell > Search time frame of alert > Search Rule of Alert 1<br />
** OSINT Invoke-WebRequest -  cmdlet to send HTTP and HTTPS requests<br />
** ANSWER TO Q1) Invoke-WebRequest <br /> <br />
<img src="https://github.com/nickstrunk/SOCAlpha1/assets/165805194/d36f5357-61c2-4da8-9ff5-726f422af84d" height="80%" width="80%" alt="Root Webpage Source"/>
<br />
<br />

<h3>Q2) Alert 1 (2/2) - What is the full URL from which the file is downloaded?</h3>
<b>Analyze Alert Data in Kibana</b> <br />
** Displayed is the URI of the Invoke-WebRequest<br /> 
** ANSWER TO Q2) hxxps[://]raw[.]githubusercontent[.]com/nerrorsec/SBT-SOC/main/MSWorker.exe <br /> <br />
<img src="https://github.com/nickstrunk/SOCAlpha1/assets/165805194/9b7713b6-c0e1-43f8-bb5d-3b6a9d4b3a1b" height="80%" width="80%" alt="Root Webpage Source"/>
<br />
<br />


<h3>Q3) What is the name of the php page which will process the stolen credentials?</h3>
<b>Inspect Page Source</b> <br />
** Right click web page > View Page Source <br /> 
** PHP script is called once credentials entered<br />
** ANSWER TO Q3) jeff.php <br /> <br />
<img src="" height="80%" width="80%" alt="Webpage Source"/>
<br />
<br />

<h3>Q4) What is the SHA256 of the phishing kit in ZIP format? (Provide the last 6 characters)</h3>
<b>Traverese Backwards Through URL</b> <br />
** Inspect HTML of each directory > (/secure) References "0ff1cePh1sh.zip"<br /> <br />
<img src="https://github.com/nickstrunk/Phishyv1/assets/165805194/e8f0bbc9-be91-4213-adb8-6ff6cc36c520" height="80%" width="80%" alt="Webpage Source Referencing Zip File"/>
<br />
<br />
**  Download the file from the web page directory where 0ff1cePh1sh.zip is referenced<br /> <br />
<img src="https://github.com/nickstrunk/Phishyv1/assets/165805194/2dfbcb08-446f-478a-95a0-7f260971337e" height="80%" width="80%" alt="Webpage Directory Storing Zip File"/>
<br />
<br />
** Run sha256sum on 0ff1cePh1sh.zip <br /> <br />
<img src="https://github.com/nickstrunk/Phishyv1/assets/165805194/f7a65f14-4c54-4cf3-84a3-7f819e67853f" height="80%" width="80%" alt="SHA256 on Zip File"/>
<br />
<br />
** ANSWER TO Q4) fa5b48 
<br />
<br />

<h3>Q5) What email address is set up to recieve the phishing credential logs?</h3>
<b>Investigate PHP File That Processes the Stolen Credentials </b> <br />
** Click on jeff.php file that is referenced in the HTML of the web page <br /> 
** Variable $recipient = "boris.smets@tfl-uk.co" <br />
** ANSWER TO Q5) boris.smets@tfl-uk.co <br /> <br />
<img src="https://github.com/nickstrunk/Phishyv1/assets/165805194/fc1b7cf2-29bf-4a85-9af5-960726a0c2c0" height="80%" width="80%" alt="PHP File"/>
<br />
<br />

<h3>Q6) What is the function called to produce the PHP variable which appears in the index1.html URL?</h3>
<b>Inspect URL </b> <br />
** Observe /index1.html then Epoch timestamp appended <br /> 
** Traverse backwards in URL to view-source:http://securedocument.net/secure/L0GIN/protected/login/portal/ <br />
** Displayed is the function Date().getTime(); <br />
** ANSWER TO Q6) Date().getTime(); <br /> <br />
<img src="https://github.com/nickstrunk/Phishyv1/assets/165805194/b9c33a93-6951-43b2-a2e1-233cf9deb406" height="80%" width="80%" alt="PHP File Function"/>
<br />
<br />

<h3>Q7) What is the domain of the website which should appear once credentials are entered?</h3>
<b>Inspect jeff.php </b> <br />
** Observe redirection domain <br /> 
** Displayed is the window.location <br />
** ANSWER TO Q7) office.com <br /> <br />
<img src="https://github.com/nickstrunk/Phishyv1/assets/165805194/ab5e6e7f-ed08-4533-bb03-27ff0d8bfe6a" height="80%" width="80%" alt="PHP Variable Function"/>
<br />
<br />

<h3>Q8) There is an error in this phishing kit. What variable name is wrong causing the phishing site to break? (Enter any of 4 potential answers)</h3>
<b>Inspecting jeff.php and Page Source of Webpage</b> <br />
** Observe HTML form on webpage > Variables are assigned email (userrr) and password (passss) <br /> <br />
<img src="https://github.com/nickstrunk/Phishyv1/assets/165805194/820a66fc-6f44-4552-b13c-c73db16a6aab" height="80%" width="80%" alt="Webpage Source"/>
<br />
<br />
** jeff.php expects variable names user1 (email) and pass1 (password) from submitted form <br /> <br />
<img src="https://github.com/nickstrunk/Phishyv1/assets/165805194/a11c82db-ec3a-44d0-8b1d-4fd5f7c9c990" height="80%" width="80%" alt="PHP File"/>
<br />
<br />
** ANSWER TO Q8) ANY OF THESE FOUR (userrr, passss, user1, pass1) <br /> <br />
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
