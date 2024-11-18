
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

How you approach a task would usually dictate how successful you will be. It’s easy to rely on the most cutting-edge pieces of technology being offered out there, but across the industry, people would always be the most important part of any security team. And so, while thinking of equipping ourselves with the best tools is important, investing time (and probably money) in learning the proper mindset is as significant. 

What's the basis for our hunt?

It is imperative that we start our hunt with leads comprised of accurate pieces of information such as known relevant malware as well as trusted Threat Intelligence. Through leads, we give threat hunters better chances of achieving amazing things, from easy wins like looking for malicious binaries to more complex hunting projects like finding patterns of activity of certain groups that target organisations similar to us or industries we’re part of.

Threat Intelligence

Since we’re talking about dictating the direction of a hunt, it’s essential that we arm ourselves with critical information that will let us know more about the threat(s) that we may be dealing with. Understanding the bad that we may be dealing with is akin to knowing how they might behave within our environment, possibly allowing us to narrow down our search to specific sweet spots such as specific pieces of data they might be interested in, or even knowing which groups or APTs might be particularly interested in targeting us.

Unique Threat Intelligence

Intelligence on threats that you are able to develop internally is a very valuable asset to have. Not many organisations have the kind of intrusion experience that would allow them to study and develop usable intelligence from said intrusion and even fewer have the capability of developing it internally. Furthermore, intelligence of this kind may have the characteristic of being ultimately unique to your organisation.

Indicators of Compromise (IOCs) specifically documented on previous intrusions would be the most obvious and straightforward example for this one. IOCs immediately give value not only to your threat hunters but also to your detection mechanism, as they’re actual traces of an adversary. Through this, re-intrusions of that specific adversary or other adversaries that employ the same tactics would be easier to spot.

Threat Intelligence Feeds

As touched upon above, not a lot of organisations are capable of developing valuable and actionable Threat Intelligence internally. While a lot of organisations have their fair share of intrusions, not everyone has that kind of experience under their belt which allows them a front-row seat to a specific adversary’s IOCs, among others. More so, it involves a lot of money, skill, and effort to be able to become an efficient Threat Intelligence producer.

It is not the end for the rest of us, as we can learn from other Threat Intelligence producers via Threat Intelligence feeds. There exist intelligence feeds that are both readily and publicly available. One of the most popular examples of this one is the MISP, an open-source Threat Intelligence and sharing platform. You may learn more about MISP here.

On the other hand, there are also paid resources that specialise in producing intelligence, some of which are capable of creating tailored intelligence for your organisation. Some examples of this are Recorded Future and ReliaQuest. These kinds of services are not cheap, and gaining a license would typically cost an arm; however, in the hands of a capable Threat Intelligence analyst, the insights that you would be able to gain would be extraordinary.

General Hunting Guide	Examples
Unique Threat Intelligence	Indicators of Compromise
Threat Intelligence Feeds	
MISP

Recorded Future

Digital Shadows
