# Redline
### Learn how to use Redline to perform memory analysis and to scan for IOCs on an endpoint.
Many tools can aid a security analyst or incident responder in performing memory analysis on a potentially compromised endpoint. an analyst to dig deep into the weeds when examining memory artifacts from an endpoint. But this process can take time. Often, when an analyst is triaging, time is of the essence, and the analyst needs to perform a quick assessment to determine the nature of a security event.

#### One of the most popular tools is Volatility
* [https://www.volatilityfoundation.org/](https://www.volatilityfoundation.org/)

That is where the FireEye tool [Redline](https://www.fireeye.com/services/freeware/redline.html) comes in. Redline will essentially give an analyst a 30,000-foot view (10 kilometers high view) of a Windows, Linux, or macOS endpoint. Using Redline, you can analyze a potentially compromised endpoint through the memory dump, including various file structures. With a nice-looking GUI (Graphical User Interface) - you can easily find the signs of malicious activities. 

#### Here is what you can do using Redline:
* Collect registry data (Windows hosts only)
* Collect running processes
* Collect memory images (before Windows 10)
* Collect Browser History
* Look for suspicious strings
* And much more!

### There are three ways or options to collect data using Redline: 
* Standard Collector - this method configures the script to gather a minimum amount of data for the analysis.
* Comprehensive Collector - this method configures the script to gather the most data from your host for further analysis. This method takes up to an hour or more. You will choose this method if you prefer the full analysis of the system.
* IOC Search Collector (Windows only) - this method collects data that matches with the Indicators of Compromise (IOCs) that you created with the help of IOC Editor. You will choose this method if you want to run the data collection against known IOCs that you have gathered either through threat intelligence (data feed or narrative report), incident response, or malware analysis.


