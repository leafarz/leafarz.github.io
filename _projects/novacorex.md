---
title: NovacoreX
description: Competitive arena FPS inspired by classic shooters.
order: 2
---
<div class="project-info-container">
  <div class="project-info-grid">
    <div class="project-info-item">
      <div class="text-muted">Role</div>
      Game Developer
    </div>
    <div class="project-info-item">
      <div class="text-muted">Game Engine</div>
      Unreal Engine
    </div>
    <div class="project-info-item">
      <div class="text-muted">Programmers</div>
      3
    </div>
    <div class="project-info-item">
      <div class="text-muted">Joined</div>
      Mid project
    </div>
  </div>
</div>

<h1>Info</h1>
NovacoreX is a competitive arena FPS which aims to bring back nostalgic gameplay with precise mechanics. The game is built with Unreal Engine.

<h4>Links</h4>
Website: <a href="https://www.novacore.tech/" target="_blank" rel="noopener noreferrer">https://www.novacore.tech/</a>

<h1>Contributions</h1>

- [Animation](#animation)
    - [Setup Character and Camera to be True FPS](#setup-character-and-camera-to-be-true-fps)
    - [Integrating Animations](#integrating-animations)
    - [Connect the Animation System to the Gameplay Ability System](#connect-the-animation-system-to-the-gameplay-ability-system)
    - [Bug Fixes](#bug-fixes)


## Animation
I joined the team mid development and there's already a basic working animation similar to the FPS template of Unreal.


#### Setup Character and Camera to be True FPS
The game started with an FPS setup and I was tasked to make it to a True FPS. 


#### Integrating Animations
Main part of this is updating the Animation Blueprint implementation to utilize blending of animations, blend spaces and montages. Adding procedural aim and recoil and IK is also added.


#### Connect the Animation System to the Gameplay Ability System
I updated the core framework for the animation to utilize GAS and be more scalable. I also introduced tags for the character state and and removed some repetitive implementations.

After the rework, it became easier for us to add new equipment without the need of adding new code. We just create new data assets, add the list of states and animations.


#### Bug Fixes
I still contributed to bug fixes regarding gameplay and replication.
