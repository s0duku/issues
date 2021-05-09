
A issue was dicovered on wavlink device with firmware at least from M79X3.V5030.180530 to M79X3.V5030.201201(newest version for now).   

A remote attacker can execute arbitrary code by sending  a crafted POST request to /cgi-bin/adm.cgi.    

Notice that it isn't like CVE-2020-10971.  

## How it start  

When I was trying to analyze CVE-2020-10971，I downloaded the newest WL-WN579X3-A firmware posted on the official website of Wavlink.   

firmware: https://www.wavlink.com/en_us/firmware/details/3a4d65ad3d.html  

After I checked all the code branches, I couldn't find the CVE-2020-10971, then I find a more old version firmware on the internet, I do notice that there was a RCE problem at adm.cgi correspond to https://james-clee.com/2020/04/18/multiple-wavlink-vulnerabilities/ saying.   

However I notice another RCE at the code branch which is responsible for handling password changes.  

Older versions of the firmware do not have this problem, but newer versions has RCE problem when the web server are handling the request for changing the password from uthenticated user.  

## The problem code  



## POC  

First I try the RCE at a old version.  


