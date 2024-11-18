# Core Concept

## Threat Hunting Introduction

Threat hunting involves proactively searching for cybersecurity threats by actively seeking out indications of malicious activities. This is the core definition of threat hunting. However, to fully grasp its scope and significance within an organization, it's essential to compare it with Incident Response.

## Threat Hunting in Contrast with Incident Response

Incident Response (IR) is inherently reactive. Actions or “responses” are initiated by an initial notification or alert, which is first triaged and analyzed. Once sufficient evidence of malicious activity is gathered, it is classified as an incident that needs to be addressed.

Conversely, Threat Hunting is inherently proactive. There is no specific ‘trigger’ for a hunt; rather, it is driven by the goal of strengthening the organization’s security posture, guided by Threat Intelligence.

A stark contrast can be seen here - While both aim to secure the organization, their driving forces and objectives differ significantly—Incident Response reacts to alerts, whereas Threat Hunting proactively seeks potential threats.

![image](https://github.com/user-attachments/assets/c6543baf-65e8-4fdb-9b8f-604c69b5e8df)

Organizations typically begin threat hunting when they already have an Incident Response (IR) process and detection mechanisms in place but believe incidents are not being identified quickly enough. Even with advanced threats or sophisticated red team exercises, there will always be ways for attackers to bypass detection.

Threat hunting aims to close this gap by continually enhancing and improving existing detection mechanisms to ensure future similar malicious activities are detected immediately. During this process, any identified threats are promptly reported to the IR team. The findings from threat hunting trigger the IR team’s response, and subsequent findings from the IR process can guide the threat hunting team to uncover additional malicious behavior.

This example illustrates the effective synergy between these two approaches, both working towards the common goal of strengthening the organization's security posture.

![image](https://github.com/user-attachments/assets/d336241e-0afd-4ef8-be88-f7e7b1d3f0a6)

# Threat Hunting Mindset

While it's tempting to rely on the latest technology, the industry consistently values people as the most critical component of any security team. Therefore, while equipping ourselves with advanced tools is crucial, investing time (and possibly money) in developing the right mindset is equally important.

## What’s the Basis for Our Hunt?

We must begin our hunt with leads from reliable sources such as known malware and trusted Threat Intelligence. These leads increase the chances of success for threat hunters, from simple tasks like finding malicious binaries to more complex projects like identifying activity patterns of specific groups targeting organizations similar to ours.

## Threat Intelligence

To direct our hunt effectively, it's crucial to gather critical information about potential threats. Understanding these threats helps us predict their behavior in our environment, allowing us to focus our search on specific data they might target or identifying groups or APTs particularly interested in us.

## Unique Threat Intelligence

Internally developed threat intelligence is a valuable asset. Few organizations have the intrusion experience needed to develop such intelligence, making it unique to your organization. Indicators of Compromise (IOCs) from previous intrusions are a straightforward example, providing immediate value to both threat hunters and detection mechanisms.

## Threat Intelligence Feeds

Not all organizations can produce actionable Threat Intelligence internally. While many have experienced intrusions, few have the expertise to gain deep insights into adversaries. Learning from other Threat Intelligence producers through feeds is beneficial. Platforms like [MISP](https://www.misp-project.org/) offer publicly available intelligence, while paid services like [Recorded Future](https://www.recordedfuture.com/) and [ReliaQuest](https://www.reliaquest.com/blog/category/threat-intelligence/) can provide tailored intelligence, offering extraordinary insights in the hands of skilled analysts.
