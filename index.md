---
title: Home
layout: home
---

# Super Mario Bros.

Super Mario Bros. is a classic platform game developed by Nintendo in 1985. 
The game follows **Mario**, an Italian plumber, on his quest to rescue 
**Princess Peach** from the villainous **Bowser**. Along the way, 
Mario must navigate challenging levels filled with obstacles, enemies, 
and power-ups.

Beyond its status as an iconic video game, Super Mario Bros. has been studied in 
computational complexity theory. In this discussion, we will explore how certain 
level configurations in the game can be used to encode logical constraints, 
ultimately proving that determining whether a given level is passable is an 
**NP-hard** problem.

<img src="assets/images/mario/mario-meme.png" alt="Mario Forms" style="max-width: 100%; height: auto;">


## Key Elements of the Game

Mario has different forms that impact his abilities:

- **Normal Mario**: The default form with basic movement and jumping.
- **Super Mario**: Gained by collecting a **Super Mushroom**, allowing Mario to break bricks.
- **Invincible Mario**: Temporarily obtained by collecting a **Super Star**, making Mario immune to enemies and hazards.

<img src="assets/images/mario/mario-forms.png" alt="Mario Forms" style="max-width: 100%; height: auto;">

### Basic Environment Elements

Several types of blocks and structures shape the levels in *Super Mario Bros.*:

- **Normal Blocks** <img src="assets/images/mario/normal-block.png" alt="Normal Block" width="20"> : Static, inert blocks that Mario can stand on.
- **Item Blocks** <img src="assets/images/mario/item-block.png" alt="Item Block" width="20">: Contain power-ups such as **Super Mushrooms** or **Super Stars**, which are released when hit from below.
- **Bricks** <img src="assets/images/mario/brick.jpg" alt="Brick" width="20">: Can be destroyed by **Super Mario** when hit from below.
- **Pipes** <img src="assets/images/mario/pipe.png" alt="Pipe" width="20">: Transport Mario between different sections of a level.

To simplify our problem, we allow the use of **palace switches** <img src="assets/images/mario/palace-switch.png" alt="Normal Block" width="20">: 

<img src="assets/images/mario/palace-switch-mechanics.png" alt="Palace switch mechanics" style="max-width: 100%; height: auto;">









