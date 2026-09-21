# IDOR - Insecure Direct Object Reference

## What is IDOR?
User ID maathi paatha vere user data varuthu na athu IDOR. Access control missing da.

Example: /profile?id=100 -> un data. /profile?id=101 -> vera user data = BUG!

## Common Endpoints to Test
- /api/user/123
- /profile?id=456
- /invoice/789
- /account/1001
- /my-orders/1023

## Payloads & Tricks

### 1. Simple ID Change
/user/123 -> /user/124
/profile?user_id=100 -> 101, 102

### 2. UUID Bypass Trick
UUID ah direct ah guess panna mudiyathu, aana /api/users list la ellam IDs leak aagum. Atha eduthu use pannu.

### 3. HTTP Method Change
GET /api/user/123 - 403 Forbidden
POST /api/user/123 - 200 OK (data leak!)

### 4. Add .json extension
/api/user/123.json
/api/user/123/.json

### 5. Parameter Pollution
id=123&id=124 - second ID win pannum
id= victim_id nu maathu

## How to Test in Burp Suite
1. Request ah Repeater ku anuppu
2. ID ah 1,2,3 nu maathi paaru
3. Response la vera user email / PII irukka nu check pannu
4. Autorize extension use pannu

## Checklist for Bug Hunting
- [ ] Profile ID change panniya?
- [ ] Order ID / Invoice ID change panniya?
- [ ] Auth header remove panni try panniya?
- [ ] API v1 / v2 version check panniya?

## Real Bug Example
Trichy e-commerce site la /my-orders/1023 la 1022 pota vera user order address leak aachu da!

## Tools
- Burp Suite Autorize
- Param Miner
- HackTricks - IDOR

---
Made by Madhan - Trichy to Bugcrowd Hall of Fame!Enter## IDOR - Insecure Direct Object Reference

## What is IDOR?
User ID maathi paatha vere user data varuthu na athu IDOR. Access control missing da.

Example: /profile?id=100 -> un data. /profile?id=101 -> vera user data = BUG!

## Common Endpoints to Test
- /api/user/123
- /profile?id=456
- /invoice/789
- /account/1001
- /my-orders/1023

## Payloads & Tricks

### 1. Simple ID Change
/user/123 -> /user/124
/profile?user_id=100 -> 101, 102

### 2. UUID Bypass Trick
UUID ah direct ah guess panna mudiyathu, aana /api/users list la ellam IDs leak aagum. Atha eduthu use pannu.

### 3. HTTP Method Change
GET /api/user/123 - 403 Forbidden
POST /api/user/123 - 200 OK (data leak!)

### 4. Add .json extension
/api/user/123.json
/api/user/123/.json

### 5. Parameter Pollution
id=123&id=124 - second ID win pannum
id= victim_id nu maathu

## How to Test in Burp Suite
1. Request ah Repeater ku anuppu
2. ID ah 1,2,3 nu maathi paaru
3. Response la vera user email / PII irukka nu check pannu
4. Autorize extension use pannu

## Checklist for Bug Hunting
- [ ] Profile ID change panniya?
- [ ] Order ID / Invoice ID change panniya?
- [ ] Auth header remove panni try panniya?
- [ ] API v1 / v2 version check panniya?

## Real Bug Example
Trichy e-commerce site la /my-orders/1023 la 1022 pota vera user order address leak aachu da!

## Tools
- Burp Suite Autorize
- Param Miner
- HackTricks - IDOR

---
Made by Madhan - Trichy to Bugcrowd Hall of Fame!Enterof Fame!
