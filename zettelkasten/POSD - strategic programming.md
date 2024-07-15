---
tags:
  - software-design
parent: "[[POSD - strategic vs tactical programming]]"
aliases:
  - strategic programming
type: reference
---
the first step towards becoming a good software designer is to realize that working code isn't enough it's not acceptable to introduce unnecessary complexities in order to finish your current task faster.
the most important thing is the long-term structure of the system. most of the code in any system is written by extending the existing code base, so your most important job as a developer is to facilitate those future extensions. thus you should not think of working code as your primary goal, though of course, your code must work your primary goal must be to produce a great design. which also happens to work this is strategic programming.

## strategic programming investment types
- some of the investments will be proactive. for example, it is worth taking a little extra time to find a simple design for each new class rather than implementing the first idea that comes to mind try a couple of alternative designs and pick the cleanest one.
- other investments will be reactive. No matter how much you invest upfront there will inevitably be mistakes in your design decisions. overtime these mistakes will become obvious. when you discover a design problem don't just ignore it or patch around it; take a little extra time to fix it. if you program strategically you will continually make small improvements to the system design. this is the opposite of tactical programming. where you are continually adding small bits of complexity that cause problems in the future.
## how much to invest?
- what is the right amount of investment? A huge up-front investment such as trying to design the entire system won't be effective. this is the waterfall method, and we know it doesn't work. the ideal design tends to emerge in bits and pieces, as you get to experience the system thus, the best approach is to make lots of small investments on a continual basis. I suggest spending about 10-20% of your total development time on investments this amount is small enough that it won't impact your schedules significantly but large enough to produce significant benefits over time.
- your initial project will thus take 10-20% longer than it would in a purely tactical approach. that extra time will result in a better software design and you will start experiencing the benefits within a few months. it won't be long before you are developing at least 10-20% faster than you would if you had programmed tactically. At this point your investments become free. the benefits from your past investments will save enough time to cover the cost of future investments you will quickly recover the cost of the initial investment.
