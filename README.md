# Project 8 - Pentesting Live Targets

Time spent: **4** hours spent in total

> Objective: Identify vulnerabilities in three different versions of the Globitek website: blue, green, and red.

The six possible exploits are:
* Username Enumeration
* Insecure Direct Object Reference (IDOR)
* SQL Injection (SQLi)
* Cross-Site Scripting (XSS)
* Cross-Site Request Forgery (CSRF)
* Session Hijacking/Fixation

Each version of the site has been given two of the six vulnerabilities. (In other words, all six of the exploits should be assignable to one of the sites.)

## Blue

Vulnerability #1: SQL Injection  
- The ID field in the URL of a salesperson is used in a SQL command. The Blue site does not sanitize this.
<img src="https://i.imgur.com/0iWZSua.gif" width="800">

Vulnerability #2: Session Hijacking  
- Using the provided PHP tool, it can be shown that there is not proper checking for what session the current browser has on this site.
<img src="https://i.imgur.com/tT9HAYD.gif" width="800">

## Green

Vulnerability #1: Username Enumeration  
- The inner HTML has a field for error checking. The green site shows "failure" if the username is correct and "failed" if the username is incorrect.
<img src="https://i.imgur.com/2oDjqQt.gif" width="800">

Vulnerability #2: Cross-Site Scripting  
- The feedback form does not sanitize user input, allowing for stored XSS.
<img src="https://i.imgur.com/yqt59lf.gif" width="800">

## Red

Vulnerability #1: Insecure Direct Object Reference  
- The salesperson id field can be used to access user id 10, which is an unposted salesperson.  
<img src="https://i.imgur.com/9vwPJPv.gif" width="800">

Vulnerability #2: Cross-Site Request Forgery  
- The CSRF token used in POST message can be ignored, allowing for hidden forms to secretly update information.
<img src="https://i.imgur.com/FR9kJh0.gif" width="800">

## Notes

Finding a way to show CSRF was tricky.  
Username Enumeration was also weirdly hidden.

