- analysis of data and information using tools and techniques to generate meaningful patterns to mitigate against potential risks associated with existing or emerging threats
- classifications:
	- Strategic Intel : high level intel that looks into the the org's threat landscape
	- technical intel : examines evidence and artifacts of attack. incident response team can use this intel to create a baseline of attack surface to analyse and develop defense mechanism
	- Tactical Intel : Assesses adversary's  tactics, techniques and procedures(TTP). this intel can strengthen security controls and address vulnerabilities through real time investigations
	- operational intel : assesses an adversaries specific motives and intention to perform attack. security teams may use this intel to identify the threat actors in the org's
- most common threat intelligence is technical intel -- this is mainly known as IOC(Indicator of compromise) - based threat intelligence
- there are 2 types of people - consumers and producers
- Producers - gather, analyze and distribute threat intelligence data to others and for themselves. can be cybersecurity vendors, researchers, etc.. they collect data through various methods and techniques, most common is honeypot.
- Consumers - these are people who consume data that are produced by producers. these group use this info to identify vulnerabilities on their org's, prevent and detect the vulnerabilities in the IOCs, incident response can be faster

Types of IOCs that are commonly distinguished in threat intelligence:
- Domains : URLs used for hosting malicious files, C2 programs or email to spam
- IP Addresses : Commonly attacks are attributed from this IP addresses

Domain blocking through DNS Sinkhole
- this mitigates connections to a malicious domain
- this is done by redirecting all the malicious DNS request to a DNS sinkhole

Detection capabilities:
- IP Address : connection to firewall logs wherein the direction of the connection 
	- Egress(in to out of org's) - to malicious IP execution of potential malware, thus communicating with malicious IP
	- Ingress(out to in of org's) - intrusion attempt from malicious actors
- URL : Connection via proxy logs wherein the HTTP method indicates the nature:
	- HTTP GET - potential download of malicious file or access to phishing website
	- HTTP POST - potential submission of credentials or exfiltration of stolen creds.
- Domains : Malicious domains in DNS logs indicate below malicious activity:
	- the domain hosts malware or additional files for his execution chain.
	- the domain is phishing website
	- domain used for C2(remote connection-reverse shell) connection
- some prevention technique can be used for detection:
	- DNS sinkhole : domains resolving a loopback may indicate a connection to malicious domain listed in sinkhole
	- Firewall IP blocking : blocked connections from and to a malicious IP address may indicate malicious activity
	- Proxy blocking : Blocked web connection may indicate malicious attempt to access malware or trying to access to phishing site
	- Mail gateway blocking : emails blocked based on the emails sender may indicate a spam or attempt from a malicious sender

Sigma Rules
- it is an open source generic signature language to describe log events in structured format.
- allows quick sharing of detection methods by security analysts

ElastAlert
- opensource framework on alerting anomalies, spikes, or other patterns of interest found in data stored in elastalert
- can be used to alert to various external services like email, pagerduty etc..