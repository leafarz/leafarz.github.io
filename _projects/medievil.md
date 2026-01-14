---
title: MediEvil
description: Remake of the old action-adventure game MediEvil (1998) released for the first PlayStation.
order: 5
---
<div class="project-info-container">
  <div class="project-info-grid">
    <div class="project-info-item">
      <div class="text-muted">Role</div>
      Senior Game Developer
    </div>
    <div class="project-info-item">
      <div class="text-muted">Game Engine</div>
      Unreal Engine
    </div>
    <div class="project-info-item">
      <div class="text-muted">Programmers</div>
      4
    </div>
    <div class="project-info-item">
      <div class="text-muted">Joined</div>
      Mid Development
    </div>
  </div>
</div>

<h1>Info</h1>
<iframe src="https://www.youtube.com/embed/19Dj520a3Og" frameborder="0" allowfullscreen style="aspect-ratio: 16 / 9; width:100%; height:100%">
</iframe>

<br>
<div class="row">
  <div class="col-md-6">
    <p><b>MediEvil</b> (2019) is a remake of the old action-adventure game MediEvil (1998) released for the first PlayStation.</p>
  </div>
  <div class="col-md-6">
    <figure>
      <iframe src="https://www.youtube.com/embed/By8uylNCFbg" frameborder="0" allowfullscreen style="aspect-ratio: 16/9; width:100%; height:100%"></iframe>
      <div class="caption">Gameplay video by @longplayarchive</div>
    </figure>
  </div>
</div>


<h4>Links</h4>
PlayStation Website: <a href="https://www.playstation.com/en-us/games/medievil/" target="_blank" rel="noopener noreferrer">https://www.playstation.com/en-us/games/medievil/</a>



<h1>Contributions</h1>

- [Bug Fixes and Optimization](#bug-fixes-and-optimization)
- [Dash Mechanic](#dash-mechanic)
- [Pushable Objects](#pushable-objects)
    - [Directional Objects](#directional-objects)
    - [Rotary Objects](#rotary-objects)
    - [Spline Objects](#spline-objects)
- [Waypoint (Object Interaction)](#waypoint-object-interaction)


## Bug Fixes and Optimization
I joined the project where there were a few features left needed and it was just bug fixes and optimizations until release. We optimized things which were causing low FPS from the profiler and not optimized prematurely.

<div class="row">
  <div class="col-md-6">
    <p>One specific bug I optimized involved culling this crystal in the crystal stage. It was causing very low FPS across the entire stage because it was always active and invoked a lot of physics interactions.</p>
    <p>I disabled the physics and only turn on when the player is nearby. Plus only checks a few collisions when necessary.</p>
  </div>
  <div class="col-md-6">
    <figure>
      <iframe src="https://www.youtube.com/embed/By8uylNCFbg?start=10138" frameborder="0" allowfullscreen style="aspect-ratio: 16/9; width:100%; height:100%"></iframe>
      <div class="caption">Crystal Object @ 2:48:58</div>
    </figure>
  </div>
</div>



## Dash Mechanic
The dash mechanic was my first task when I joined the team. This was needed to be almost identical, if not exact, to the old game. I went through the old code and researched that PS1 units were different so I just translated it to Unreal's units. I implemented it in the movement component.

## Pushable Objects

#### Directional Objects
<div class="row">
  <div class="col-md-6">
    <p>This type of pushable object is bidirectional wherein you can push to whichever direction, except for back.</p>
  </div>
  <div class="col-md-6">
    <figure>
      <iframe src="https://www.youtube.com/embed/By8uylNCFbg?start=5920" frameborder="0" allowfullscreen style="aspect-ratio: 16/9; width:100%; height:100%"></iframe>
      <div class="caption">Bidirectional object @ 1:38:40</div>
    </figure>
  </div>
</div>

<div class="row">
  <div class="col-md-6">
    <figure>
      <iframe src="https://www.youtube.com/embed/By8uylNCFbg?start=1853" frameborder="0" allowfullscreen style="aspect-ratio: 16/9; width:100%; height:100%"></iframe>
      <div class="caption">Unidirectional Object @ 30:53</div>
    </figure>
  </div>
  <div class="col-md-6">
    <p>This type of pushable object is unidirectional. In this example, it's one axis up until it reaches a certain distance and changes to a different axis.</p>
  </div>
</div>

#### Rotary Objects
<div class="row">
  <div class="col-md-6">
    <p>This pushable object will rotate clockwise or counter-clockwise depending on the side pushed.</p>
  </div>
  <div class="col-md-6">
    <figure>
      <iframe src="https://www.youtube.com/embed/By8uylNCFbg?start=12929" frameborder="0" allowfullscreen style="aspect-ratio: 16/9; width:100%; height:100%"></iframe>
      <div class="caption">Rotary Object @ 3:35:29</div>
    </figure>
  </div>
</div>

#### Spline Objects
<div class="row">
  <div class="col-md-6">
    <figure>
      <iframe src="https://www.youtube.com/embed/By8uylNCFbg?start=2452" frameborder="0" allowfullscreen style="aspect-ratio: 16/9; width:100%; height:100%"></iframe>
      <div class="caption">Spline Object @ 40:52</div>
    </figure>
  </div>
  <div class="col-md-6">
    <p>This is a pushable object that will follow the spline which the designers add.</p>
  </div>
</div>


## Waypoint (Object Interaction)
<div class="row">
  <div class="col-md-6">
    <p>When interacting with objects, Dan will automatically walk towards the set location before playing the montage and doing the interact logic. This was also one of the tasks I did while also considering navigation.</p>
  </div>
  <div class="col-md-6">
    <figure>
      <iframe src="https://www.youtube.com/embed/By8uylNCFbg?start=1231" frameborder="0" allowfullscreen style="aspect-ratio: 16/9; width:100%; height:100%"></iframe>
      <div class="caption">Automatically walks to the treasure chest @ 20:31</div>
    </figure>
  </div>
</div>
