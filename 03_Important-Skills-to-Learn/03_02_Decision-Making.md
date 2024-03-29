# Decision Making

An architect needs to be able to take decisions and guide projects or the entire organization into the right direction.

* Know what is important: Do not waste time with unimportant decisions or activities. Learn what is important. To my knowledge there is not a book which has these information. My personal favorites are these 2 characteristics which I usually consider when evaluating if something is important or not:

    * Conceptional Integrity: If you decide to do it in one way, stick to it, even if it is sometimes better to do it differently. Usually, this leads to a more straightforward overall concept, eases comprehensibility and eases maintenance.

    * Uniformity: If you for example define and apply naming conventions it is not about upper- or lowercase, but to have it applied everywhere in the same way.


* Prioritize: Some decisions are highly critical. If they are not taken early enough workarounds are build up which are often unlikely to be removed later and are a nightmare for maintenance, or worse, developers simply stop working until a decision is taken. In such situations it is sometimes even better to go with a “bad” decision instead of having no decision. But before it comes to this situation, consider prioritizing upcoming decisions. There are different ways to do so. I suggest having a look at the Weighted Shortest Job First (WSJF) model which is widely used within agile software development. Especially the measures time criticality and risk reduction are critical to estimate the priority of architecture decisions.

* Know your competence: Do not decide things which are not in your competence. This is critical as it may ruin your position as architect significantly if not considered. To avoid this, clarify with your peers which responsibilities you have and what is part of your role. If there are more than one architect, then you should respect the level of architecture in which you are currently deployed. As an lower level architect you better come up with suggestions for higher level architecture instead of decisions. Further, I recommend checking critical decisions always with a peer.

* Evaluate multiple options: Always lay out more than one option if it comes to decisions. In the majority of the cases I was involved in, there was more than one possible (good) option. Going with only one option is bad in two respects: First, it seems that you did not do your job properly and secondly it impedes making proper decisions. By defining measures, options can be compared based on facts instead of gut feelings, e.g. license costs or maturity. This usually leads to better and more sustainable decisions. Further, it eases to sell the decision to different stakeholders. Besides, if you do not have evaluated options properly you may miss arguments when it comes to discussions.