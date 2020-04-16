# Project 7 - WordPress Pentesting

Time spent: **10** hours spent in total

> Objective: Find, analyze, recreate, and document **five vulnerabilities** affecting an old version of WordPress

## Pentesting Report

1. (Required) Authenticated Stored Cross-Site Scripting (XSS) in YouTube URL Embeds
  - [x] Summary: 
    - Vulnerability types: XSS
    - Tested in version: 4.2
    - Fixed in version: 4.2.13
  - [x] GIF Walkthrough: ![](youtube.gif)
  - [x] Steps to recreate: 
    - Create a page.
    - Paste the code below.
     ```
     [embed src='https://youtube.com/embed/123\x3csvg onload=alert(123)\x3e'][/embed]
     ```
    - View the page.
  - [x] Affected source code:
    - [Link 1](https://github.com/WordPress/WordPress/commit/419c8d97ce8df7d5004ee0b566bc5e095f0a6ca8)
    
2. (Required) Authenticated Shortcode Tags XSS
  - [x] Summary: 
    - Vulnerability types: XSS
    - Tested in version: 4.2
    - Fixed in version: 4.7.2
  - [x] GIF Walkthrough: ![](comment.gif)
  - [x] Steps to recreate: 
    - Make a comment as an admin with the code below.
    ```
    <a href = "XSS" onmouseover=alert(123) rel="nofollow">CLICK HERE!</a>
    ```
    - Hover over the link.
  - [x] Affected source code:
    - [Link 2](https://github.com/WordPress/WordPress/commit/f72b21af23da6b6d54208e5c1d65ececdaa109c8)
    
3. (Required) Authenticated Cross-Site Scripting (XSS) via Media File Metadata
  - [x] Summary: 
    - Vulnerability types: XSS
    - Tested in version: 4.2
    - Fixed in version: 4.2.13
  - [x] GIF Walkthrough: ![](media.gif)
  - [x] Steps to recreate: 
    - Create a page and press "Add Media"
    - Click on "Create Audio Playlist" and select this file below.
    ```
    https://www.securify.nl/advisory/SFY20160742/xss.mp3
    ```
  - [x] Affected source code:
    - [Link 3](https://github.com/WordPress/WordPress/commit/28f838ca3ee205b6f39cd2bf23eb4e5f52796bd7)


## Resources

- [WordPress Source Browser](https://core.trac.wordpress.org/browser/)
- [WordPress Developer Reference](https://developer.wordpress.org/reference/)

GIFs created with [LiceCap](http://www.cockos.com/licecap/).


## License

    Copyright [2020] [Yu Bin Liu]

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

        http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.
