---
tags:
  - SRE
related: "[[observability]]"
type:
  - fleeting
---
the problem with building new features quickly is that there's often a strong negative correlation between development velocity and system reliability.

it's all too common for a reliability deficit caused by the focus on features to be noticed only when it causes widespread complaints via social media and then dealt with reactively in great haste.

A missed reliability target signal when too many things users care about have been broken by excessive development velocity 

the important question is How fast is "too fast"?
or how do you balance the risk to reliability from changing a system with the requirement to build new features for that system?

Measuring SLO Performance gives a real-time indication of the reliability cost of the new features,  if everyone agrees the SLO represents the point at which you are no longer meeting the expectation of your users then broadly speaking being within SLO is a signal that you can move faster without causing those users pain, on the other hand burning most or in the worst cases multiple of your error budget means you have to lift your foot off the accelerator.

you can plan proactively by estimating risks to your reliability from the rollout of new features in terms of time to detection, time to resolution, and impact percentage this allows you to gauge the potential amount of error budget that each risk might consume.