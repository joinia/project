# GetSimple Authenticated Stored Cross-Site Scripting(XSS)

#### Description

Persistent XSS (or Stored XSS) attack is one of the three major categories of XSS attacks, the others being Non-Persistent (or Reflected) XSS and DOM-based XSS. In general, XSS attacks are based on the victim’s trust in a legitimate, but vulnerable, website or web application.GetSimple CMS does not filter the content correctly at the "content" module, resulting in the generation of stored XSS.

#### Affects Plugins

GetSimple CMS

https://github.com/GetSimpleCMS/GetSimpleCMS

#### Author

webraybtl@webray.com.cn inc

#### Proof of Concept

1. Login the CMS.

2. Open Page http://127.0.0.1:8086/admin/edit.php

3. Put XSS payload  (<script>alert(111)</script>) in the content box and click on save page to publish the page

   ![image](https://github.com/joinia/project/blob/main/GetSimple/images/write.png)

4. Use "burp"  to capture and change packages

   ![image](https://github.com/joinia/project/blob/main/GetSimple/images/package-1.png)

   ![image](https://github.com/joinia/project/blob/main/GetSimple/images/package-2.png)

5. Viewing the successfully published page,We can see the alert.

![image](https://github.com/joinia/project/blob/main/GetSimple/images/pagealert.png)

