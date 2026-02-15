---
layout: post
title: "Men in Black: Most Wanted"
author: "Jonathan Hughes"
categories: publishedgames
tags: [publishedgames]
image: /mib/MIBMostWantedKeyArt.png
---

<div class="center">
Engine: Unity<br/>  
Platform: Meta Quest 2/3/S<br/>
<a href="https://www.meta.com/en-gb/experiences/men-in-black-most-wanted/31400148706295734/" target="_blank">Meta Store Link</a>
</div>

<div class="center">
<iframe width="560" height="315" src="https://www.youtube.com/embed/HGjPsFGyl8c?si=i5Vrh-Kd9_lMK2Rm" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
</div>

Main responsibilities:

- Valuable prototyping of gameplay mechanics, dialogue system and inventory early on in the project.
- Developed Bystander AI and exposure system.
- Implemented and helped design hidden in plain sight gameplay.
- Developed "leech" type enemy AI from prototype to final version.
- Developed Boss AI for Big Bug, First iteration of "Craig" boss AI and further work on "Yarl" final boss AI.
- Performance optimisation and general bug-fixing.

![Men In Black:Most Wanted](/assets/img/mib/MIBMostWanted_Screenshots_01.png)

I joined the project not too long after its start so I have worked through and contributed to the initial vertical slice milestone, through to alpha and the final release.

My initial time was spent prototyping a variety of gameplay mechanics and systems used in the game, some of which underwent further iteration and made it into the published game. I helped added features to the pistol and the magnet gun (that would go on to become the magnet gloves) and made the first iteration of the heal spray. I worked on the initial dialogue system that had branching paths, and a scanner-based mini-game that would allow the player to discover the NPC's alignment and the correct path through the branching dialogue. Tied to this was the triggering of follow-on behaviour for the AI, such as unlocking a door for the player if they navigate their dialogue correctly. This work was later folded into the Utility AI system as AI Tasks.

After some time working on gameplay mechanics and prototyping, I moved to the AI team and helped build out the newly adopted Utility AI system for our AI which was replacing earlier alternatives that I did help prototype. Along with writing more general code to be used in agent behaviours and considerations, I mostly working on the human bystander AI and a number of bosses in the game, the Big Bug and Craig in particular.

Working closely with design and animation, I expanded the human NPC behaviour that would respond to the player's actions like using MIB gadgets or weapons, or trespassing where they weren't supposed to be. This formed a pillar of the game in the form of "hidden in plain sight (HIPS)" gameplay where how well the player keeps their activities from the general public will have an impact on their mission score. If NPCs became suspicious of the player then they would need to have their memory wiped with the franchise's famous neuralyzer before the player could continue. I helped rework this exposure mechanic and the NPC's behaviour when they were cautious (Would follow the player making it harder for them to perform their agent duties) to panicked, where NPCs would run away and hide.

![Men in Black: Most Wanted](/assets/img/mib/MIBMostWanted_Screenshots_02.png)

I worked on the *Leech* enemy AI from prototype to final form. This is a special enemy type that can jump at the player and latch on to the player, creating a fun VR interaction of pulling the leeches off and throwing them away. These jump and latch behaviours needed to be coded up to work alongside the standard Utility AI decisions and behaviours set up for the leech.  
There were also two other leech variants: The timebomb leech that would start a countdown to explode once latched to the player, and the sleeper leech, a leech that was too large to latch on to the player so would just slam into the player but would start asleep encouraging the player to sneak past else risk waking them up.

For Craig, the giant leech boss, I quickly iterated its behaviour and repositioning as the player moves through the sewer sequence. Working with design, we quickly iterated the introduction and progression through the physical space which has largely remained unchanged.

My proudest work is on the bug boss. A fan favourite of the original film and I really wanted to do it justice in the game. The boss sequence went through a number of iterations but still felt quite lacklustre. With the boss arena being staged in a nightclub I pushed for the boss fight to make use of the environment, and we arrived at a responsive dancefloor that changed to reflect the current state of the boss. A notable feature is the dance floor activating as the bug reveals itself and jumps down from the ceiling. With additional work to codify distinct phases with each new phase providing an escalation in the attacks the Big Bug has become a standout of the game.

![Men in Black: Most Wanted](/assets/img/mib/MIBMostWanted_Screenshots_05.png)

Towards the end of the project I was involved in the normal bug-fixing that happens to improve the quality of the game and remove problematic edge cases. I was also involved in optimising the performance of the game. This mostly involved ensuring all meshes that could be culled were included in view volumes and view volumes were properly configured so that it would be possible to cull out all unneeded parts of the levels that were not viewable by the player. This optimisation work also involved using the profiler in editor play mode and with local builds to identify the causes of dips in performance, and then apply fixes whether that be moving vfx/shaders to the bootstrap scene to prewarm them, or to rewrite costly calculations.  
Overall, a really enjoyable project where I've learnt so much.

---