# Penetration Testing Report — Footprinting & Network Scanning

**Pentester:** SHOMARI ISMAIL  
**Program/Batch:** B082-Networkwalks  
**Date:** 17 August 2026  
**Modules:** W2-PM1, W2-PM4, W2-PM5  
**Phases:** Phase 1 — Reconnaissance & Footprinting; Phase 2 — Scanning & Network Discovery

## 1. Liability Disclaimer

The supplied report states that the activities were performed on systems/devices where permission was secured and on devices/systems owned by the author, for education and research purposes.

## 2. Introduction

The report covers footprinting the `networkwalks.com` domain using WHOIS, WhatWeb, nslookup, curl, wafw00f, and DNSRecon; scanning the author's local network with Zenmap; and using theHarvester for organization-related email discovery.

## 3. Tools Used

- Kali Linux
- WHOIS
- WhatWeb
- nslookup
- curl -I
- wafw00f
- DNSRecon
- Zenmap (Nmap GUI)
- ifconfig
- theHarvester

## 4. Activities Performed

### 4.1 Footprinting & Reconnaissance

The report records WHOIS information including GoDaddy as registrar and HostGator name servers. WhatWeb identified web technologies including Apache, WordPress, WordPress Download Manager, jQuery, Bootstrap, and an IP address. nslookup resolved the documented domain to `192.232.216.135`.

Curl was used to inspect HTTP response headers. The report records a WordPress redirect and headers including `Server: Apache`, `X-Redirect-By`, and cache/security-related headers.

Wafw00f identified ModSecurity (SpiderLabs) as the WAF.

DNSRecon was used to enumerate DNS records including NS, MX, SPF/TXT and SRV-related information.

### 4.2 Network Scanning with Zenmap

The report states that `ifconfig` was used to identify the local IP/subnet and Zenmap was then used for a Ping Scan.

Documented live hosts:

- `10.0.0.1`
- `10.0.0.2`

A network topology was generated and saved as a PDF.

### 4.3 theHarvester

The report documents an email/sub-domain gathering exercise and records three discovered email addresses. Because this repository is intended for public GitHub use, those addresses are deliberately not reproduced here.

## 5. Risk Analysis

The report rates WHOIS exposure as Low, technology/version fingerprinting as Medium, HTTP header exposure as Medium, WAF detection as Low/positive control, DNS enumeration as Low–Medium, local LAN discovery as Medium in local context, and email enumeration as Medium–High.

The report's overall conclusion is that the findings did not directly compromise the target; instead, combined reconnaissance information could give an attacker a useful starting point for later attack stages.

## 6. Recommendations

1. Reduce unnecessary version disclosure.
2. Minimize exposed HTTP headers.
3. Maintain SPF/DKIM/DMARC correctly.
4. Reduce publicly harvestable email addresses where possible.
5. Maintain and periodically test WAF configuration.
6. Segment and monitor LAN environments.
7. Perform periodic footprinting reviews.

## 7. Evidence

Screenshots and the Zenmap topology output should be stored in the `evidence/` directory.
