---
title: Giant Cop&colon; Justice Above All
description: Game for PS VR where you play as the giant cop and you grab criminals and put them to jail.
order: 6
---
<div class="project-info-container">
  <div class="project-info-grid">
    <div class="project-info-item">
      <div class="text-muted">Role</div>
      Senior Game Developer
    </div>
    <div class="project-info-item">
      <div class="text-muted">Game Engine</div>
      Unity
    </div>
    <div class="project-info-item">
      <div class="text-muted">Programmers</div>
      3
    </div>
    <div class="project-info-item">
      <div class="text-muted">Joined</div>
      Mid Development
    </div>
  </div>
</div>

<h1>Info</h1>
<iframe src="https://www.youtube.com/embed/hd3sDYulS7k" frameborder="0" allowfullscreen style="aspect-ratio: 16 / 9; width:100%; height:100%">
</iframe>

<br>
<div class="row">
  <div class="col-md-6">
    <p><b>Giant Cop: Justice Above All</b> is a game for PS VR where you play as the giant cop and you grab criminals and put them to jail.</p>
  </div>
  <div class="col-md-6">
    <figure>
      <iframe src="https://www.youtube.com/embed/N2fw5xv6Q64" frameborder="0" allowfullscreen style="aspect-ratio: 16/9; width:100%; height:100%"></iframe>
      <div class="caption">Gameplay video by @lionheartx10</div>
    </figure>
  </div>
</div>

<h4>Links</h4>
Steam: <a href="https://store.steampowered.com/app/451080/Giant_Cop_Justice_Above_All/" target="_blank" rel="noopener noreferrer">https://store.steampowered.com/app/451080/Giant_Cop_Justice_Above_All/</a>


<h1>Contributions</h1>

- [Bug Fixes And Optimizations](#bug-fixes-and-optimizations)
    - [Animation](#animation)


## Bug Fixes And Optimizations
I worked on this project for bug fixes and optimizations to comply with PlayStation's TRC. Performance was dipping around 35-40 FPS and this was critical especially for VR games.

#### Animation
The animation system was the main performance bottleneck, specifically for pedestrians and vehicles. They also have their own animation system so I implemented some LOD in it where the nearest ones have higher update rate than the ones farther.

After this, I added some more optimization by spreading the updates for the animations across frames so that not everything are updated in the same frame.
