# Project 7 - WordPress Pentesting

Time spent: 5 hours spent in total

> Objective: Find, analyze, recreate, and document **five vulnerabilities** affecting an old version of WordPress

## Pentesting Report

1. (Required) Authenticated Stored Cross-Site Scripting
  - [ ] Summary: A stored/persistent, Cross-Site script XSS vulnerablilty which allows remote attackers to inject arbitrary web script/HTML by abusing the way unclosed HTML elements during the processing of shortcode tags are mishandled.
    - Vulnerability types:XSS
    - Tested in version:4.2
    - Fixed in version: 4.3
  - [ ] GIF Walkthrough: 
  - [ ] Steps to recreate: 
   ```
    [caption width="3" caption='<a href="' ">]</a><a href="http://onmouseover='alert(1)'">Xss Here!</a>
    ```

    When a user hovers over the text characters, the injected code is executed.

  - [ ] Affected source code:
    - [Link 1](https://core.trac.wordpress.org/browser/tags/version/src/source_file.php)
2. (Required) WordPress 2.5-4.6 - Authenticated Stored Cross-Site Scripting via Image Filename
  - [ ] Summary: This vulnerability allows remote attackers to create a specially crafted image file name that will inject arbitrary web script.  This abuses the insufficient validation of the file names of uploaded images.
    - Vulnerability types:XSS
    - Tested in version:4.2
    - Fixed in version: 4.6.1
  - [ ] GIF Walkthrough: 
  - [ ] Steps to recreate: 
   ```
    filename<img src=a onerror=alert(10)>.png
    ```

    When the attachment page is viewed, the injected code is executed.
  - [ ] Affected source code:
    - [Link 1](https://core.trac.wordpress.org/browser/tags/version/src/source_file.php)
1. (Optional) Vulnerability Name or ID
  - [ ] Summary: 
    - Vulnerability types:
    - Tested in version:
    - Fixed in version: 
  - [ ] GIF Walkthrough: 
  - [ ] Steps to recreate: 
  - [ ] Affected source code:
    - [Link 1](https://core.trac.wordpress.org/browser/tags/version/src/source_file.php)
1. (Optional) Vulnerability Name or ID
  - [ ] Summary: 
    - Vulnerability types:
    - Tested in version:
    - Fixed in version: 
  - [ ] GIF Walkthrough: 
  - [ ] Steps to recreate: 
  - [ ] Affected source code:
    - [Link 1](https://core.trac.wordpress.org/browser/tags/version/src/source_file.php) 

## Assets

List any additional assets, such as scripts or files

## Resources

- [WordPress Source Browser](https://core.trac.wordpress.org/browser/)
- [WordPress Developer Reference](https://developer.wordpress.org/reference/)

GIFs created with [LiceCap](http://www.cockos.com/licecap/).

## Notes

Describe any challenges encountered while doing the work

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
