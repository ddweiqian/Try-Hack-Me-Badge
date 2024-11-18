
# Threat Hunting Introduction

Threat hunting is an approach to finding cyber security threats where there’s an active effort done to look for signs of malicious activity. In its most basic form, that is the definition of Threat Hunting; however, in order for us to really understand what it entails as well as what its actual role is in the organisation, we will start by contrasting it with Incident Response.

# Threat Hunting in Contrast with Incident Response

Incident Response (IR) is innately reactive. The action, or “response”, is triggered by an initial notification or alert. This initial notification is first triaged, then analysed, and when enough pieces of evidence point to malicious activity, it is deemed an incident that needs to be responded to and dealt with accordingly.

More information about Incident Response, particularly the initial stages of it, is discussed in the Preparation Room of the IR Module.

Threat Hunting, on the other hand, is innately proactive. There is no actual ‘trigger’ that would mobilise a hunt, except for the pursuit of building the strength of the organisation’s security posture, guided by Threat Intelligence.

A stark contrast can be seen here - while both are guided by the goal of ensuring the security of the organisation, the forces that drive the reactive and proactive nature of Incident Response and Threat Hunting, respectively, hardly share the same direction. This is further steered by the specific objectives that each aims to achieve.

Reactive Approach	Proactive Approach
Incident Response	Threat Hunting
Triggered by an initial notification / alert	Active search for suspicious events that can become incidents
Guided by the initial scope of the incident	Guided by Threat Intelligence
"There's a threat that needs to be dealt with now."	"There might be a threat that we don't know yet."
Usually, organisations start doing threat hunts when there’s already an established IR process as well as detection mechanisms in place, but they think that incidents aren’t being detected early enough. In the case of advanced threats, or even well-made red team exercises, there will always exist ways to go through your organisation undetected.

Threat Hunting aims to bridge this gap, constantly finding ways to add and improve the current detection mechanisms in place so that future similar bad behaviour will automatically be detected immediately. More so, during that process, detected threats go immediately to the Incident Response team. The trigger for their mobilisation are the findings from the Threat Hunt, and consequent findings from the IR process may steer the Threat Hunting team to further find bad behaviour.

This classic example shows the beauty of the synergy between two seemingly different approaches to ensuring one specific goal is met - strengthening the organisation’s security posture.

Synergy Diagram Between IR and Threat Hunting
