# Recon - Bug Bounty First Step

## What is Recon?
Target pathi information collect panrathu than recon. Hacking ku munnadi recon strong ah irukanum da.

## Subdomain Discovery
subfinder -d target.com
assetfinder --subs-only target.com
amass enum -d target.com
findomain -t target.com

## Live Hosts Check
cat subdomains.txt | httpx
httpx -l subdomains.txt -status-code

## Port Scanning
naabu -host target.com
nmap -sC -sV target.com

## Wayback & JS Files
waybackurls target.com
cat subdomains.txt | waybackurls | grep .js
gau target.com

## Tools List
- subfinder, assetfinder, amass, httpx, naabu, nuclei, waybackurls, gau

## Google Dorks
site:target.com
site:target.com filetype:pdf
inurl:admin site:target.com

## Checklist
- [ ] Subdomains found?
- [ ] Live hosts checked?
- [ ] Ports scanned?
- [ ] Wayback data collected?
- [ ] JS files analyzed?

---
Made by Madhan - Trichy
