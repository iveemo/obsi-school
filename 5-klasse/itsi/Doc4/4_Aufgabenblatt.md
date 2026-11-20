---
tags:
  - itsi
  - 5te_klasse
created: 2026-11-20T20:57:14+01:00
modified: 2026-11-20T22:45:14+01:00
---
Honestly ka wie du die ppt dann gestaltest aba die die 4# header sind nur unterpunkte heißt die kannst du entweder das alls zweite folie nach den 3# header machen oder eif nur erwähnen (bei card testing ig kanns eif dar stehn und ich sag dann was gemeint ist). sonst lass ich dir den freirum wie du denkst dass es am besten ist

Bei C2 kannst du (wenn du willst) wieder eine art diagram machen (flowchart oder tree oder sowas) damit mans halt nacheinander erklären kann und weills ja genau die selbe info wie aus "credential phishing" und "supply chain" ist musst du es nicht doppelt hinschreiben sondern ich erwähne dann eif auf welchen von den vorhin genannten sachen das jz zutrifft
## Reconstruction of the Attack Sequence
Explain either the Cyber ​​Kill Chain model or the MITRE-ATT&CK model and assign each step of the timeline from your briefing to the appropriate phase. Briefly justify your assignment. 
## Malware and Attacker Infrastructure
Identify and name at least ==🟢two malware components or types from the report== and ==🟢justify your classification based on the described behaviors==. Explain the ==🟢role of an attacker-controlled server (C2 server)== in the described sequence.
### credential phishing
internal login website clone received on work email to retreive credentials lacking 2FA

#### data harvester
event listener on the input fields of the checkout form  
- \#cc-number \#cc-expiry \#cc-cvv (aka card details) 
and transmits their content to https://cdn-assets-secure.net/collect using fetch()
#### scan detection
Code checks via navigator.userAgent for automated test browser: suppresses the transmission to evade security scanners. (da halt vlt mit graphen/flowcharts zeigen wo die karten-daten durchfließen und ich erklär den ablauf dann)
(sowas ähnlich wie hier maybe https://www.cloudflare.com/img/learning/security/threats/phishing-attack/diagram-phishing-attack.png)
### supply chain
with the credentials the attacker logs into CMS and ships a slightly edited `adwise-tracker.js` snippet as a planned update to mutliple vendors (including Alpenzuckerl)
#### card testing
Initially, isolated, small test transactions (< 5 EUR)
checking the validity of stolen card data before the actual misuse.
### Command & Control (C2)
(nur ne erklärung für dich) (eig nur ne wiederholung von vorhin)
- initial compromise
a successful phishing attack, exploiting vulnerabilities, or the installation of malware through infected files or links. Malicious software, often referred to as a “bot” or “agent,” is installed on the victim’s device, allowing the threat actor to gain control.
- Callback Mechanism
Once the agent is installed, it establishes a connection to the C2 server. This connection is often referred to as a ‘callback’.
- Command and Control Channel
The C2 channel is the communication link between the compromised device (or file .js) and the C2 server. It is essential for issuing commands, receiving instructions, and exfiltrating data. To evade detection, C2 traffic is often obfuscated by encrypting or encoding the data being transmitted.
- Data Exfiltration (amost same as C2 Channel kinda confusing ik)
C2 servers facilitate data exfiltration by instructing the compromised device to send specific data to the server. This data can include stolen credentials, sensitive documents, or other valuable information.
- Evasion Techniques (self explenatory)

(jetzt info für ppt)

Initial control: Attacker has permanent access to the CMS (aquired credentials)

callback mechanism: sends data to a C2 server (https://cdn-assets-secure.net/collect) this uses a known skimming dommain that got mentioned in 2 other, unrelated incident reports

C2 Channel/Data Exfiltration: in `fetch()` to know where to send the data/event listener on the input fields and `fetch()` to the C2 server

Evasion Techniques: navigator.userAgent checks for for automated test browser and suppresses the transmission to evade security scanners.

source: https://www.sentinelone.com/cybersecurity-101/threat-intelligence/what-are-command-control-c2-servers/