# DDos Attack Scenario - NIST 800-61 Incident Report

![image](https://github.com/user-attachments/assets/f6d4e55f-7a71-4b35-9fd7-d192f22ebf35)

# Project Overview
As a cybersecurity analyst, I was tasked with using this security event (see Scenario Section below) to create a plan to improve the company’s network security. 

I used the NIST CSF 800-61 framework to analyze and respond the network incident. I made recommendations on improving the organizations security posture based on the insights gained from my investigation.

#  Scenario

You are a cybersecurity analyst working for MediaMarketing.com - a multimedia company that offers web design services, graphic design, and social media marketing solutions to small businesses. The organization recently experienced a DDoS attack, which compromised the internal network for 3 hours until it was resolved.

During the attack, the organization’s network services suddenly stopped responding due to an incoming flood of ICMP packets. Normal internal network traffic could not access any network resources.

The incident management team responded by blocking incoming ICMP packets, stopping all non-critical network services offline, and restoring critical network services.

The company’s cybersecurity team then investigated the security event. They found that a malicious actor had sent a flood of ICMP pings into the company’s network through an unconfigured firewall. This vulnerability allowed the malicious attacker to overwhelm the company’s network through a distributed denial of service (DDoS) attack.

# Incident Response Report

### 1. Executive Summaray
This morning ( 2025-03-22 6:30am ) several of our associates reported to the help desk that they could not access their network drives, they could not print to network printers and could not access the R&D database application. Our main company website also started to give customers connection time out errors. This incident has stopped all work in our company for two hours as well as resulted in the loss of all sales for 3 hour time period. 

The network team investigated the incident and from the analysis of the WireShark and NMap logs it appears that several of our DNS servers experienced a Distributed Denial-of-Service (DDoS) attack because of ICMP packet flooding overwhelming the network. 

The incident management team responded to this attack by blocking all incoming ICMP packets and stopping all non-critical network services.

 A subsequent investigation revealed an unconfigured firewall as the main erability. To prevent future occurrences, firewall rules were updated, source IP verification was implemented, and network monitoring and IDS/IPS solutions were deployed.



### 2. Identify
During routine operations, the IT team observed a sudden and complete network service outage. Employees reported being unable to access internal resources. Upon investigation using the WireShark packet sniffing tool, excessive ICMP packet traffic was detected, indicating a possible DDoS attack. The cybersecurity team confirmed that an external malicious actor had exploited an unconfigured Network Security Group (NSG) firewall to launch the attack.



### 3. Protect
Prior to the attack, MediaMarketing.com had implemented general cybersecurity measures, including firewalls and basic traffic monitoring. However, the firewall was not configured to limit ICMP traffic, leaving the network erable to exploitation. Additionally, no intrusion detection or prevention systems (IDS/IPS) were in place to proactively monitor and mitigate such attacks. There was no systematic schedule to monitor and triage network logs 



### 4. Detect
The cybersecurity team identified the attack through:

- Unusual network slowness.
- A surge in ICMP packet traffic flooding the network.
- Logs showing excessive incoming ICMP requests from multiple spoofed IP addresses.
- The lack of proactive monitoring tools contributed to a delayed detection of the attack.

### 5. Respond

Upon confirming the DDoS attack, the incident response team took the following immediate actions:

- Blocked all incoming ICMP packets to mitigate the flood.
- Shut down non-critical network services to conserve resources.
- Restored essential network services to resume critical business operations.
- Investigated and identified the attack vector as an unconfigured firewall.


### 6. Recover
To strengthen the network against future attacks, the following measures were implemented:

- A new firewall rule limiting the rate of incoming ICMP packets.
- Source IP verification to filter out spoofed addresses.
- Deployment of network monitoring tools to detect abnormal traffic patterns.
- Installation of an IDS/IPS system to filter and mitigate malicious ICMP traffic.
- The introduction of a SOAR tool (Microsoft Sentinel) to monitor and provide automatic responses to spikes in ICMP traffic
- A scheduled reporting system of network log reivews
- The introduction of a Vulnerablity scanning tool (Tenable Nessus) to run periodic scans on the network and endpoint devices.

The above measures were tested and validated to ensure ongoing network resilience.

### 7. Lessons Learned

1. Proactive Security Measures: Unconfigured firewall settings created a critical vulnerability. Regular security audits and firewall rule assessments are essential.

2. Network Traffic Monitoring: The absence of proactive traffic monitoring delayed detection. Implementing continuous monitoring tools ensures early identification of anomalies.

3. Incident Response Readiness: The response team effectively mitigated the attack, but a pre-established DDoS mitigation plan would have reduced response time.

4. Employee Awareness: Educating IT staff about network security best practices and proactive threat mitigation can help prevent future attacks.

Moving forward, MediaMarketing.com will conduct regular security assessments, implement stricter firewall rules, and continuously update security protocols to safeguard against similar incidents.
