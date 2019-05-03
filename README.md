# Facebook CyberSecurity Course for Veterans Week 7 &amp; 8 Assignment: Wordpress vs. Kali
# Project 7 - WordPress Pentesting

Time spent: **10** hours spent in total

> Objective: Find, analyze, recreate, and document **3 - 5 vulnerabilities** affecting an old version of WordPress

## Pentesting Report

### 1. Comment Cross-Site Scripting
  - [ ] Summary: 
    - Vulnerability type(s): XSS (2017 OWASP Top 10: A7)
    - Version(s) affected: Wordpress 3.9 - 5.1
    - Tested in version: 4.2
    - Fixed in version: 4.2.23
  - [ ] GIF Walkthrough: 
  ![Comment XSS gif](https://i.imgur.com/13OEriP.gif)
  - [ ] Steps to recreate:
    - Write a comment on any post
    - Include scripted elements into the comment
      - Example: <script> alert('HOLD THE DOOR') <script>
    - Post the comment for the scripted elements to be stored and applied
  - [ ] Affected source code:
    - [Link](https://github.com/WordPress/WordPress/commit/0292de60ec78c5a44956765189403654fe4d080b)
    
### 2. Sessions Not Terminated Upon Explicit User Logout
  - [ ] Summary: 
    - Vulnerability type(s): Auth Bypass/Broken Authentication (2017 OWASP Top 10: A2)
    - Version(s) affected: Wordpress 3.4.2 - 3.9.2
    - Tested in version: 3.9.1
    - Fixed in version: 4.0
  - [ ] GIF Walkthrough: 
  ![Auth Bypss gif](https://i.imgur.com/TvBZ5xM.gif)
  - [ ] Steps to recreate: 
    - After Admin user is logged out, use burp to grab cookie credentials
    - Apply stolen cookies to visit the admin interface 
      - Example: root/wp-admin/profile.php
  - [ ] Affected source code:
    - [Link 1](https://whiteoaksecurity.com/blog/2012/12/17/cve-2012-5868-wordpress-342-sessions-not-terminated-upon-explicit-user-logout)
    - [Link 2](https://www.trustwave.com/en-us/resources/blogs/spiderlabs-blog/leveraging-lfi-to-get-full-compromise-on-wordpress-sites/)

### 3. User Enumeration
  - [ ] Summary: 
  
    - Vulnerability type(s): User Enumeration through WPScan
    - Tested in version: 4.2.2
    - Fixed in version: ____
  - [ ] GIF Walkthrough: 
  ![User Enumeration](https://i.imgur.com/ylUHLpW.gif)
  - [ ] Steps to recreate: 
    - In the command line: "wpscan --url {URL TO ENUMERATE} --enumerate u"
  - [ ] Affected source code:
    - [Link](https://github.com/WordPress/WordPress/blob/4.2-branch/wp-login.php)
    
## Resources

- [WordPress Source Browser](https://core.trac.wordpress.org/browser/)
- [WordPress Developer Reference](https://developer.wordpress.org/reference/)

GIFs created with [LiceCap](http://www.cockos.com/licecap/).

## License

    Copyright [2019] [Dalina Dao]

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

        http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.
