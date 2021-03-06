Time spent: **5** hours spent in total

> Objective: Find, analyze, recreate, and document **five vulnerabilities** affecting an old version of WordPress

## Pentesting Report

1. (Required) WordPress <= 4.3 - Authenticated Shortcode Tags Cross-Site Scripting (XSS)
  - [x] Summary: A stored/persistent, Cross-Site script XSS vulnerablilty which allows remote attackers to inject arbitrary web script/HTML by abusing the way unclosed HTML elements
   during the processing of shortcode tags are mishandled.
    - Vulnerability types: XSS
    - Tested in version: 4.2
    - Fixed in version: 4.3
  - [x] GIF Walkthrough:
<img src= 'https://github.com/nodasaul/security/blob/master/XSS.gif' title='XSS' alt='XSS' />

  - [x] Steps to recreate: Create a new post and place the following code in the body:

    ```
    [caption width="3" caption='<a href="' ">]</a><a href="http://onmouseover='alert(1)'">Xss Here!</a>
    ```

    When a user hovers over the text characters, the injected code is executed.

  - [x] Affected source code:https://core.trac.wordpress.org/browser/branches/4.1/src/wp-includes/post.php)

2. (Required) WordPress 2.5-4.6 - Authenticated Stored Cross-Site Scripting via Image Filename
  - [x] Summary: This vulnerability allows remote attackers to create a specially crafted image file name that will inject arbitrary web script.  This abuses the insufficient validation of the file names of uploaded images.
    - Vulnerability types: XSS
    - Tested in version: 4.2
    - Fixed in version: 4.6.1
  - [x] GIF Walkthrough:
<img src= 'https://github.com/nodasaul/security/blob/master/XSS1.gif' title='XSS1' alt='XSS2' />


  - [x] Steps to recreate: Create a new media post and upload an image with the following filename format:

    ```
    filename<img src=a onerror=alert(10)>.png
    ```

    When the attachment page is viewed, the injected code is executed.

  - [x] Affected source code: https://core.trac.wordpress.org/browser/branches/4.2/src/wp-admin/includes/media.php)

3. (Required) WordPress  4.0-4.7.2 - Authenticated Stored Cross-Site Scripting (XSS) in YouTube URL Embeds
  - [x] Summary: This vulnerablity allows remote attackers to inject arbitrary web script or HTML via video URL in YouTube emebeds.
    - Vulnerability types: XSS
    - Tested in version: 4.2
    - Fixed in version: 4.7.3
  - [x] GIF Walkthrough:

<img src= 'https://github.com/nodasaul/security/blob/master/XSS2.gif' title='XSS2' alt='XSS2' />

  - [x] Steps to recreate: Create a new page and place the following code in the body:

    ```
    [embed src='https://youtube.com/embed/12345\x3csvg onload=alert(1)\x3e'][/embed]
    ```

    When the page is viewed, the injected code is executed.

  - [x] Affected source code: https://core.trac.wordpress.org/browser/branches/4.1/src/wp-includes/media.php)
  
  4. (Required) WordPress 4.2 User Enumeration
- [x] Summary: 
- Vulnerability types: User Enumeration
- Tested in version: 4.2
- Fixed in version: N/A
- [x] GIF Walkthrough:
 <img src= 'https://github.com/nodasaul/security/blob/master/UE.gif' title='UE' alt='UE' />
- [x] Steps to recreate:
 - Go to the WordPress login page, first, check the input for admin with empty password,
   then it shows the error because the password is empty.Second, when you input admin as    username, and put password randomly.It shows the password for admin is incorrect. When   you put other name (ex.user1), and random password, it shows error. 

## Assets

No additional assets, such as scripts or files, were used.

## Resources

- [WordPress Source Browser](https://core.trac.wordpress.org/browser/)
- [WordPress Developer Reference](https://developer.wordpress.org/reference/)

## Notes

## License

    Copyright [2018] [Saul Noda]

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

        http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.
