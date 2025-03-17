---
title: Home
layout: home
nav_order: 1
toc: true
toc_sticky: true
---

# Super Mario Bros. Introduction

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

<img src="assets/images/mario/mario-meme.png" alt="Mario Meme" class="centered-img" style="max-width: 40%; height: auto;">


# Key Elements of the Game

First, we will introduce several key elements of the game that we will use
in our proofs. 

## Mario's Forms

Mario has different forms that impact his abilities:

- **Normal Mario**: The default form with basic movement and jumping.
- **Super Mario**: Gained by collecting a **Super Mushroom** <img src="assets/images/mario/mushroom.png" alt="Super Mushroom" width="20">, allowing Mario to break bricks.
- **Invincible Mario**: Temporarily obtained by collecting a **Super Star** <img src="assets/images/mario/star.png" alt="Super Star" width="20">, making Mario immune to enemies and hazards.

<img src="assets/images/mario/mario-forms.png" alt="Mario Forms" class="centered-img" style="max-width: 100%; height: auto;">

## Basic Environment Elements

Several types of blocks and structures shape the levels in *Super Mario Bros.*:

- **Normal Blocks** <img src="assets/images/mario/normal-block.png" alt="Normal Block" width="20"> : Static, inert blocks that Mario can stand on.
- **Item Blocks** <img src="assets/images/mario/item-block.png" alt="Item Block" width="20">: Contain power-ups such as **Super Mushrooms** or **Super Stars**, which are released when hit from below.
- **Bricks** <img src="assets/images/mario/brick.jpg" alt="Brick" width="20">: Can be destroyed by **Super Mario** when hit from below.
- **Pipes** <img src="assets/images/mario/pipe.png" alt="Pipe" width="20">: Transport Mario between different sections of a level.

To simplify our problem, we also allow the use of **palace switches** <img src="assets/images/mario/palace-switch.png" alt="Normal Block" width="20">: 

- When Mario activates a **Palace Switch**, it transforms solid blocks of a matching color into transparent blocks.
- This allows Mario to access previously blocked paths and continue progressing through the level.

<img src="assets/images/mario/palace-switch-mechanics.png" alt="Palace switch mechanics" class="centered-img" style="max-width: 60%; height: auto;">

# Problem Formulation

## The $\textsc{3SAT}$ Problem

Before we define the Super Mario problem, let's introduce (or review) the 3-satisfiability ($\textsc{3SAT}$) problem. 

- A **Boolean formula** is a mathematical expression consisting of Boolean variables (taking values `true` or `false`), 
logical operators (AND ($\wedge$), OR ($\vee$), NOT ($\neg$)) and parentheses for grouping. It evaluates to either `true` or `false` based on variable assignment.
- A Boolean formula is **satisfiable** is there exists an assignment to the variables such that the formula evaluates to be true. 
- A **literal** is a Boolean variable or a negated Boolean variable, as in $x$ or $\neg x$.
- A **clause** is a *disjunction* ($\vee$) of several literals.
- A Boolean formula is in **conjunctive normal form** (CNF) is it is a *conjunction* ($\wedge$) of several clauses.
- A **3 CNF formula** is a CNF formula that has exactly *three* literals per clause. For example, 
$$\phi = (x_1 \vee x_3 \vee \neg x_4) \wedge (\neg x_2 \vee x_3 \vee \neg x_5)$$
is a satisfiable 3CNF formula. One true assignment is $x_1 = $ `true` and $x_2 = x_3 = x_4 = x_5 =$ `false`.

The $\textsc{3SAT}$ problem is defined to be the set of satisfiable 3CNF formula:
$$\textsc{3SAT} = \{\phi: \text{$\phi$ is a satisfiable 3CNF formula}\}$$

