---
layout: post
title: "2D Dungeon Procedural Generation"
author: "Jonathan Hughes"
categories: experiments
tags: [experiments]
image: /dungeonprocgen/dungeon-gen-top-level.png
---

<div class="center">
Engine: Unity<br/>  
Platform: PC
</div>

<div class="center">
<iframe width="560" height="315" src="https://www.youtube.com/embed/ZXlZ4LY0Rhg?si=y0faria5n7OldD4y" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
</div>

At Coatsink we have self-dev days, a couple days each month where we are free to experiment with game ideas, learn new skills etc. During some of my self-dev days I decided I would like to try and emulate the generated dungeon room layout I'd seen in the Rogue Legacy games. In Rogue Legacy, it would use a pool of room layouts, each room having a number of exits but what exits were available would differ on each run. I wanted to make a system that would use a pool of rooms but vary what exits would be used.  
Each room details all of its available exits and are added as prefabs made available to the dungeon generation.​

The basic algorithm:
- Begin with the starting room and add all of its exits to a list.
- Pick an exit from the list and randomly pick a new room with a corresponding exit that can be placed without overlapping any other existing rooms. If an overlap is found, pick a new random room.
- Once a new room has been added, add all of its available exits to the exits list.
- Repeat this process until the required number of rooms is met.
- Block off any outstanding open exits to complete the generation.

![An Example Room Generation](/assets/img/dungeonprocgen/an-example-room-generation.png)

I added special unique rooms to the generation. These are rooms that there would be a limited number of, e.g. a shop and added some rudimentary means of determining when a special room should be selected over a standard room. It is likely that we would not want special rooms to appear immediately after the start but because they would be a requirement for a successful generation, the likelihood of picking a special room is increased each time a special room is not picked until it becomes a certainty, and will be added next by the algorithm.

Finally I added a simple character controller so I can move between the rooms during play mode plus some cinemachine scripts to follow the player and switch to the new room upon entering it. With the time available we added some simple game mechanics: the boss room is locked and cannot be entered without finding a key that is spawned in a random non-special room. Once the key is found, the boss room can be entered but the doors lock after entry and would only unlock once the boss has been defeated as an example of what could be done.

---
