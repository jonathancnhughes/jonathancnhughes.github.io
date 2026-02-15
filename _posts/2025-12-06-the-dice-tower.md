---
layout: post
title: "The Dice Tower"
author: "Jonathan Hughes"
categories: gamejam
tags: [gamejam]
image: /dicetower/TheDiceTower.png
---

<div class="center">
Engine: Unity<br/>  
Platform: PC (Playable in desktop browser)
</div>
<div class="center">
<iframe frameborder="0" src="https://itch.io/embed/1617860?linkback=true" width="552" height="167"><a href="https://jflex.itch.io/the-dice-tower">The Dice Tower by jflex, CountingWithTeeth, SoooSquishy, class WilliamFox : GameplayProgrammer</a></iframe>
</div>

This game was our submission for the GMTK Game Jam 2022. The game jam lasted 48 hours and the theme was "Roll the Dice". I was in a team of four but this time I was not the sole developer and was joined by another programmer Will. Whilst I have been using github as source control for all game jam games previously, it was a necessity for both programmers to work seamlessly on the project.

We had a brief brainstorming session of how to implement something to the theme and I suggested a mechanic where you roll a number of dice and where they settled would determine where you and enemies spawned. The number of dice, and challenge, would increase with each level and adding in a reroll feature and we had a simple arcade-y score attack game we felt we could implement in the short time given.

With the two programmers, we split the work up such that I would handle the overall architecture, the dice rolling and general project management, and Will would handle the player movement and enemy logic.  
I created separate branches for us to work on and managed merging them into the main branch and building the project for testing and submission.

![Dice Tower Combat](/assets/img/dicetower/dice-tower-in-play.png)

The dice were effectively cubes that were given a small force in a random direction plus gravity enabled to have them fall to the arena below. I added logic to re-activate any dice that were cocked or landed on another dice until all dice were flat at rest. From there, the dice would determine spawn locations for the 2D player sprite, enemy sprites and any treasure sprites that were rolled.  
If I was to do the dice rolling mechanic again I would perhaps have set result positions and have the dice move and animate into position.​

![Dice in Play](/assets/img/dicetower/dice-tower-diceplay.png)

The GMTK Game Jams are always popular, this jam in particular has over 6,000 entries. That being said a lot of our feedback was really positive and we were rated in the top 12% so we didn't get featured on the YouTube channel but I think there's a really cool game here with a bit more polish and further exploration into the mechanics.



---
