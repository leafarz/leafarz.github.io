---
title: AltspaceVR Games
description: AltspaceVR is a VR app which can view web apps both 2d and 3d. These web apps are what I worked on.
order: 7
---
<div class="project-info-container">
  <div class="project-info-grid">
    <div class="project-info-item">
      <div class="text-muted">Role</div>
      Senior Game Developer
    </div>
    <div class="project-info-item">
      <div class="text-muted">Library</div>
      three.js
    </div>
    <div class="project-info-item">
      <div class="text-muted">Programmers</div>
      2
    </div>
    <div class="project-info-item">
      <div class="text-muted">Joined</div>
      Start of Development
    </div>
  </div>
</div>


<h1>Info</h1>
AltspaceVR is a VR app made from Unity. You can view websites in 3d (if supported) or 2d which a large screen will appear. This can be seen by everyone within the area.

There are a couple of projects that I worked on for the AltspaceVR platform. These games were developed in separate timelines.
<h5>1. Dungeons & Dragons</h5>
<div class="row">
  <div class="col-md-6">
    <figure>
      <iframe src="https://www.youtube.com/embed/jP2VM-7NW54?start=60" frameborder="0" allowfullscreen style="aspect-ratio: 16/9; width:100%; height:100%"></iframe>
      <div class="caption">Gameplay video by @silverzodiac1102</div>
    </figure>
  </div>
  <div class="col-md-6">
    <figure>
      <iframe src="https://www.youtube.com/embed/hL2ySQ6TS-Q" frameborder="0" allowfullscreen style="aspect-ratio: 16/9; width:100%; height:100%"></iframe>
      <div class="caption">Gameplay video by @baxorn</div>
    </figure>
  </div>
</div>

<h5>2. Boss Monsters</h5>
<figure>
  <iframe src="https://www.youtube.com/embed/bP0l6_J_swI" frameborder="0" allowfullscreen style="aspect-ratio: 16/9; width:100%; height:100%"></iframe>
  <div class="caption">Gameplay video by @HarrisD214</div>
</figure>

<h5>3. Love Letter</h5>
<figure>
  <iframe src="https://www.youtube.com/embed/KYxx2g8h8LM" frameborder="0" allowfullscreen style="aspect-ratio: 16/9; width:100%; height:100%"></iframe>
  <div class="caption">Gameplay video by @xkitox</div>
</figure>

<h5>4. Poker</h5>
<figure>
  <iframe src="https://www.youtube.com/embed/jQCdYzLqdq4" frameborder="0" allowfullscreen style="aspect-ratio: 16/9; width:100%; height:100%"></iframe>
  <div class="caption">Gameplay video by @Stuangel</div>
</figure>


<h4>Links</h4>
Steam: <a href="https://store.steampowered.com/app/407060/AltspaceVR/" target="_blank" rel="noopener noreferrer">https://store.steampowered.com/app/407060/AltspaceVR/</a>


<h1>Contributions</h1>
For Dungeons & Dragons, I mostly worked on the core framework and slowly moved to implementing gameplay after, especially on the next projects.

- [Core Framework](#core-framework)
    - [Interaction](#interaction)
    - [Network](#network)
    - [Resource Management](#resource-management)
    - [Interpolators](#interpolators)


## Core Framework
We used Three.js is a rendering library for JS and Cannon.js for physics. As we progress through the projects, I improved the core framework over time.

#### Interaction
I implemented the basic interactions with the scene game objects for our games which are mouse down, mouse up, drag and hover events using raycasts.

#### Network
I implemented our network framework using firebase. I implemented syncing of the object's states and update accordingly in client side.

#### Resource Management
I also implemented our async resource loading and pooling for the project. This includes 3d assets, shaders and materials and textures.

#### Interpolators
These are similar to Unreal Engine's Timeline node where it invokes a function asynchronously to update transformations over time like move to, rotate, scale, etc. This was used in most movements in the game.
