# Identify & Remove Suspicious Browser Extensions

**Prepared by:** <span style="color:#00ff66; font-weight:800; font-family:'Hack', 'DejaVu Sans Mono', monospace;background:#000">SAGAR RATHOD</span>

**Date:** October 2, 2025

---

## Objective
Learn to spot and remove potentially harmful browser extensions. This task is based on recent 2025 findings of malicious extensions (notably the *RedDirection* campaign) that affected millions of Chrome/Edge users, as well as fraudulent Firefox wallet add-ons.

---

## Tools Used
- Google Chrome (tested via `chrome://extensions/`)  
- Mozilla Firefox (tested via `about:addons`)  
- Vendor threat intelligence reports (Koi Security, Malwarebytes, BleepingComputer, Mozilla advisories)

---

## Suspicious Extensions Found (RedDirection Campaign Examples)

| Extension name (as installed) | Browser | Publisher / Source | Why suspicious | Evidence / Source | Action Taken |
|-------------------------------|----------|-------------------|----------------|------------------|--------------|
| Emoji keyboard online         | Chrome   | Unknown            | Part of RedDirection malicious cluster | Koi Security Report (Jul 2025) [^1] | Removed |
| Free Weather Forecast         | Chrome   | Unknown            | Reported in RedDirection with tracking behavior | Koi Security Report (Jul 2025) [^1] | Removed |
| Video Speed Controller — Video manager | Chrome | Unknown | Abused update mechanism to hijack sessions | Koi Security Report (Jul 2025) [^1] | Removed |
| Unlock Discord — VPN Proxy    | Chrome/Edge | Unknown | Impersonates VPN tool, exfiltrated data | Koi Security Report (Jul 2025) [^1] | Removed |
| Dark Theme — Dark Reader for Chrome | Chrome | Unknown | Fake clone of legitimate Dark Reader extension | Malwarebytes Summary (Jul 2025) [^2] | Removed |
| Volume Max — Ultimate Sound Booster | Chrome | Unknown | Granted excessive permissions, redirected tabs | BleepingComputer Report (Jul 2025) [^3] | Removed |

---

## Analysis of Malicious Behaviors
- **Excessive permissions:** extensions demanded the ability to read/change all data on sites.  
- **Silent tracking:** collected URLs and browsing activity.  
- **Update abuse:** legitimate at first, malicious payload delivered via later updates.  
- **Impersonation:** mimicked known extensions with slightly altered names.  

These behaviors are consistent with the *RedDirection* campaign and Firefox wallet impersonator campaigns.  

---

## Remediation Steps Taken
1. Opened extension manager in Chrome/Firefox.  
2. Cross-checked installed extension IDs with Koi Security published IOCs.  
3. Removed identified suspicious extensions.  
4. Cleared browser cookies/cache.  
5. Ran AV scan and rotated credentials for sensitive accounts.  

---

## Preventive Recommendations
- Adopt **allowlist-only extension policy** in enterprise settings.  
- Regularly audit installed extensions and match against published threat IOCs.  
- Educate users to avoid “too good to be true” tools (free VPNs, boosters, coupon add-ons).  
- Monitor vendor advisories (Google/Microsoft/Mozilla + security researchers).  

---

## References
[^1]: [Koi Security (2025)](https://www.koi.security/blog/google-and-microsoft-trusted-them-2-3-million-users-installed-them-they-were-malware): *RedDirection Browser Extension Campaign*. [Report]  
[^2]: [Malwarebytes Labs (2025)](https://www.malwarebytes.com/blog/news/2025/07/millions-of-people-spied-on-by-malicious-browser-extensions-in-chrome-and-edge): *Millions of people spied on by malicious browser extensions in Chrome and Edge*.  
[^3]: [BleepingComputer (2025)](https://www.bleepingcomputer.com/news/security/malicious-chrome-extensions-with-17m-installs-found-on-web-store/): *Malicious Chrome extensions with 1.7M installs found on Web Store*.  

---