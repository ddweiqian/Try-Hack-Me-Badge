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

# Threat Hunting Process

## What Do We Hunt For? 

The direction of a hunt is determined by what we aim to find. Throughout the process, the threat hunter continually refers back to this question to gather evidence that answers it.

While the following examples fall under the broad topic of Threat Intelligence previously discussed, they are significant enough to highlight separately. They focus on types of intelligence that provide immediate value to the hunt and are direct, specific, and actionable when found.

## Known Relevant Malware

The internet is full of known malware samples, many of which have publicly available analyses. By examining your organization, identifying relevant threat actors, and searching for traces of their malware, you can leverage this intelligence. Although this example is general, identifying what is relevant to your organization narrows down the samples to hunt for within your visibility scope.

A live malware repository example is [theZoo](https://github.com/ytisf/theZoo), where you can experiment with live malware and understand its behavior in specific environments. Additionally, malware characteristics and analyses are frequently published, such as in [Trend Micro’s Threat Encyclopedia](https://www.trendmicro.com/vinfo/us/threat-encyclopedia).

## Attack Residues

Attack residues are useful starting points, especially if you suspect an attack has already occurred. Combined with good Threat Intelligence, it’s as simple as checking off a list of attack residues within your environment. The challenge lies in distinguishing attack residues from normal behavior, especially with advanced adversaries who clean up after themselves or employ stealthy tactics.

Overall, it’s a solid approach to cover our bases, catching an attacker’s mistake once while they need to be flawless in their actions.

## Known Vulnerabilities of Products/Applications Being Used

Threat actors often find vulnerabilities and misconfigurations in the products and applications used by their target organization. Known vulnerabilities should be actively hunted and patched to prevent exploitation. During this process, you might catch a threat actor exploiting your vulnerable assets, addressing two issues at once.

The organization must be vigilant for zero-day vulnerability announcements affecting their assets. 

1. Immediate checks should include verifying the current version's vulnerability and
2. searching for traces of exploitation using historical data.
   
These hunts help ensure all assets are up-to-date with security standards while checking for past vulnerabilities.

![image](https://github.com/user-attachments/assets/e643ac4e-45a2-4340-bff7-fc9d307d7b52)

The discussion above covers common threat hunt targets but is not exhaustive. While it offers a good starting point, each organization has its own unique traits and specific factors that must be considered when undertaking a hunting task or project.

## How Do We Hunt for It?
After reviewing the information, factors, and other elements, we should have a clear understanding of the target of our hunt. With this in mind, the next logical question is, “How do we hunt for it?”

This section will not delve into hunting theories and specific techniques, which will be covered later. Instead, we'll focus on the foundational elements that drive these theories and techniques.

## Attack Signatures and IOCs
Once we've identified the target, it's crucial to define specific and actionable identifiers, such as Attack Signatures and Indicators of Compromise (IOCs), to recognize the target immediately. By distilling the "whats" of the hunt into Attack Signatures and IOCs, we can compare this information with our historical data to identify relevant malware, attack residues, and exploited vulnerabilities. Understanding the environment’s normal behavior helps in recognizing anomalies in logs when a vulnerability has been exploited.

## Logical Queries
Certain hunting tasks are best approached with logical queries. For example, hunting for assets with known vulnerabilities involves characterizing the vulnerable assets using specific identifiers like application versions. This allows us to craft logical queries that filter for these identifiers, providing straightforward results that directly improve the organization’s security posture.

## Patterns of Activity
When we narrow down the focus to specific threats, such as relevant threat actors, the next step is to identify their behavior patterns. The MITRE ATT&CK Matrix is an invaluable resource for understanding these patterns and can be particularly useful in this context.


