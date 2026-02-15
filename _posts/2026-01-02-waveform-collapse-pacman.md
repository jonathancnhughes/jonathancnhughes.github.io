---
layout: post
title: "Waveform Collapse Pacman"
author: "Jonathan Hughes"
categories: experiments
tags: [experiments]
image: /pacman/itch-cover.png
---

<div class="center">
Engine: Unity<br/>  
Platform: PC (Playable in Browser)
</div>

<div class="center">
<iframe frameborder="0" src="https://itch.io/embed/4270587?linkback=true" width="552" height="167"><a href="https://jflex.itch.io/waveformcollapse-pacman">Waveform Collapse Pacman by jflex</a></iframe>
</div>

An experiment implementing the waveform collapse algorithm to generate Pacman levels. I've always be interested in procedural generation and wanted to build something using the type of generation for 
More information about what the waveform collapse algorithm is and how it works can be found [here](https://en.wikipedia.org/wiki/Model_synthesis){:target="_blank}

![Pacman Gif](/assets/img/pacman/GenerateGrid.gif)

Generation Steps:
- Set the desired height and width and also pick a palette, then click "Generate" to generate the pacman level.
- Before the waveform collapse algorithm can run, the grid is updated to make room for the ghost box in the center of the grid and a tunnel on the left hand-side. Currently only one tunnel is ever added half-way up the height of the grid. A possible extension is to randomly add one or two, depending on if the desired height of the grid will accommodate them.
- The left half of the level will be generated using the waveform collapse algorithm. Cells will show the possible number of tiles that could fit. As the algorithm runs the possibilities reduce as the grid is filled in. The algorithm starts with the cell with the lowest possibility of tile options and picks one at random. By setting a tile this has a direct effect on the cell's neighbours and will reduce what possibilities that the cell's neighbours can be. This is repeated until either the algorithm reaches a cell that has no possibilities or the left half of the grid is complete.  
- If the algorithm cannot place a valid tile it will restart. After each tile is placed, the grid is checked that each tile is reachable via a breadth first search. If the newly placed tile creates a situation where not all tiles can be reached, the algorithm will restart.
- If the left half of the grid is proved to be valid it will then be mirrored to the right hand side of the grid. Each tile on the left is iterated over and its mirrored tile is placed.
- Once the grid's tiles have been completed, the grid needs to be finalised by adding the border to the tiles on the outside of the grid. This is done with a maze-following algorithm that starts in the bottom left corner and walks the perimeter counter-clockwise by keeping the outside of the grid to the right of the direction it walks.
- Once the outside border has been added, the sprites for the ghost box are updated to finish the grid.

![Pacman 1](/assets/img/pacman/itch1.png)

---
