# steps for recon

**discovering ip space**
- https://bgp.he.net
- whois -h whois.cymru.com $(dig +short tesla.com)
- amass intel -org tesla 
- amass intel -asn 394161
- ripe: https://apps.db.ripe.net/db-web-ui/fulltextsearch
- arin: http://whois.arin.net/ui/query.do
- shodan: shodan.io
------------
**discovering new targets (brand and tld)**
- acquisitions: www.crunchbase.com
- reverse whois: amass intel -d tesla.com -whois
- builtwith
- google dorks: intext:"Copyright © tesla motors" , intext:"Copyright (c) tesla motors"
- shodan dorks
------------
**subdomain enumeration**
- amass enum -d teslamotors.com -ip
- subfinder -d teslamotors.com -silent
- dns brute forcing
------------
**fingerprinting**
- builtwith: connected websites
- wappalyzer: cms
- whatweb tesla.com
- find open ports using: masscan -p1-65535 $(dig +short tesla.com) --rate 10000
- fingerprint using: nmap -sV -p <ports from masscan> tesla.com
- aquatone
- wayback enumeration
------------
**dorking**
- easy shodan dorks
- github dorks
- censys dorks
- google dorks
-----------
**content discovering**
- burp suite crawler
- linkfinder
- jsparser
- gobuster dir -u https://www.tesla.com -w <wordlist> 
- recursebuster -u https://www.tesla.com -w <wordlist> 
- echo www.tesla.com | otxurls
- echo www.tesla.com | waybackurls
**parameter discovery**
- Parameter Bruting (also API fuzzing)
- parameth
-----------
**automation**
- lazyrecon
-----------
**resources**
  - https://github.com/bugcrowd/bugcrowd_university/blob/master/Recon%20and%20Discovery/Bugcrowd%20University%20-%20Recon%20%26%20Discovery.pdf
  - https://owasp.org/www-chapter-coimbatore/assets/files/Lets%20Recon.pdf
