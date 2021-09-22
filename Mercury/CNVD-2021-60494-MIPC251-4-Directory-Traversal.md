
# CNVD-2021-60494

A issue was dicovered on Mercury MIPC251-4-V2.0 with firmware MIPC251-4-V2.0_2.0.21_Build_200608_Rel.69649n and MIPC252-4-V2.0 with firmware MIPC252-4-V2.0_1.0.6 Build 210305 Rel.41318n  

A remote attacker can read any file by requesting URL like '/web-static/../../etc/passwd' directory without authenticated  
 
Product page:   
https://www.mercurycom.com.cn/product-469-1.html   
https://www.mercurycom.com.cn/product-572-1.html   
  
Firmware version:   
MIPC251-4-V2.0_2.0.21_Build_200608_Rel.69649n    
MIPC252-4-V2.0_1.0.6 Build 210305 Rel.41318n   
   
Firmware dowload page:   
https://service.mercurycom.com.cn/product-469-2.html    

## Problem Code  

![](https://github.com/s0duku/issues/blob/main/Mercury/MIPC251-4-Directory-Traversal/MIPC251-4-Directory-Traversal-code0.png?raw=true)  

![](https://github.com/s0duku/issues/blob/main/Mercury/MIPC251-4-Directory-Traversal/MIPC251-4-Directory-Traversal-code1.png?raw=true)   

![](https://github.com/s0duku/issues/blob/main/Mercury/MIPC251-4-Directory-Traversal/MIPC251-4-Directory-Traversal-code2.png?raw=true)   

![](https://github.com/s0duku/issues/blob/main/Mercury/MIPC251-4-Directory-Traversal/MIPC251-4-Directory-Traversal-code3.png?raw=true)   


## POC  


![](https://github.com/s0duku/issues/blob/main/Mercury/MIPC251-4-Directory-Traversal/MIPC251-4-Directory-Traversal-poc.png?raw=true)


