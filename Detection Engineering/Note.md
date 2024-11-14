# Introduction

please paraphrase the following: Detection engineering is an important role and task for a security analyst. It involves developing processes that will guide you as an analyst to identify threats, detect them through rules and processes, and fine-tune the process as the landscape changes. Learning Objectives Understand what Detection Engineering is. Understand the Detection Engineering Lifecycle. Identify various frameworks used in Detection Engineering.
Detection engineering plays a crucial role for security analysts. It entails creating processes that help analysts identify threats, detect them using specific rules and procedures, and continuously refine these processes as the threat landscape evolves.

## Learning Objectives:

Grasp the concept of Detection Engineering.

Comprehend the Detection Engineering Lifecycle.

Recognize various frameworks utilized in Detection Engineering.

# What is Detection Engineering?

## Detection Engineering

Cybersecurity is rapidly advancing due to technological progress. As a result, adversary actions are also evolving, making cyber attacks increasingly frequent and sophisticated, challenging security teams to keep up. Therefore, new mindsets and practices are essential for security teams to match adversaries' pace. This is where detection engineering plays a crucial role.

Detection engineering involves continuously developing and operating threat intelligence analytics to detect potentially malicious activities or misconfigurations in your environment. It demands a cultural shift, requiring all security teams and management to align in building robust, threat-informed defense systems.

## Detection Types

Threat detection can be categorized into two main perspectives, each with two subcategories:

**Environment-based Detection**: This focuses on changes within an environment, based on predefined configurations and baseline activities. It includes:

1. Configuration Detection

2. Modelling

**Threat-based Detection**: This targets elements related to adversary activities, such as tactics, tools, and artifacts that reveal their actions. It comprises:

1. Indicators

2. Threat Behaviour Detections

### Configuration Detection

This detection method utilizes existing knowledge of the environment and infrastructure to pinpoint misalignments. It spans multiple domains, such as network, asset, and identity.

Configuration detection offers several benefits and faces certain challenges:

![image](https://github.com/user-attachments/assets/859acf35-be58-4ec0-914c-be72f41ca5ca)

### Modelling

This threat detection method involves setting up baseline operations and activities, and then noting any deviations. The core idea is that malicious activity can be distinguished from benign activity.

This approach entails creating an asset or activity profile that captures baseline events, time frames, and data thresholds. An in-depth exploration of baselining will be covered in the next task.

The benefits and challenges of this detection method include:

![image](https://github.com/user-attachments/assets/b0ae2406-c806-4fb6-8fed-2eee8b6a0ebe)

### Indicator Detection

Indicators are bits of information that provide context and state of an element or entity. There are **good** indicators, which identify legitimate activities or resources (like those in whitelists), and **bad** indicators, which pinpoint suspicious or malicious resources (such as blacklists or malware IPs).

Indicators of Compromise (IOCs) are often derived from investigations into malicious activities. By observing and analyzing these threat activities, analysts can develop detections using these identified indicators and adjust them as adversarial tactics evolve.

This detection method comes with its own set of benefits and challenges:

![image](https://github.com/user-attachments/assets/9b217261-20c5-47fb-bce8-4d6328d501d3)

### Threat Behaviour Detection

This method involves analysts examining an adversary's Tactics, Techniques, and Procedures (TTPs) to detect attacks, rather than relying solely on specific indicators. This approach enhances scalability in detection efforts.

By focusing on threat behaviour detection, analysts can more efficiently respond to threats and mitigate them without spending excessive time and resources on understanding the triggers for alerts. Additionally, this detection method can be integrated with established workflows and playbooks, providing best practices to follow during investigations.

This detection method also comes with its own set of benefits and challenges:

![image](https://github.com/user-attachments/assets/cd5eb584-b5f5-4d95-a8f5-5957cf3f2cf2)

Combining these forms of detection results in more robust defence systems. For example, model-based detection can be strengthened with expert-led configuration detection to reduce the chances of having false positives throwing alerts.

## Detection as Code (DaC)

Detection as Code is an organized method for creating detection systems by using best practices from software engineering. This approach treats detection processes and logic as code, enabling scalability to adapt to evolving environments and adversary tactics.

DaC introduces a code-centric workflow that integrates essential elements from Continuous Integration/Continuous Development (CI/CD) workflows, such as:

**Version Control**: Many SIEMs and EDR products lack the ability to track changes to alerts and their definitions. Incorporating version control allows for quick review, testing, and accountability of detection rules and processes, leading to higher-quality detections.

**Automation Workflows**: Adopting CI/CD workflows facilitates automated detection testing, enabling swift transitions and production deployments.

Detection as Code offers several advantages:

**Customizable and Flexible Detections**: Utilizing common languages for detections, like Sigma and YARA, allows DaC to be vendor-neutral and deployable across various SIEM, EDR, and XDR solutions.

**Test-Driven Development**: Quality testing of detection code helps identify blind spots and false positives early in the process, enhancing detection effectiveness. This approach also improves detection quality and ensures thorough documentation.

**Team Collaboration**: CI/CD workflows reduce isolation between security teams and promote collaboration through the coding process.

**Code Reusability**: As detection patterns develop, engineers can reuse code for similar functions across different detections, accelerating the detection process by avoiding the need to start from scratch.
