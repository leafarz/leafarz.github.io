---
title: Eternal League
description: Sci-fi isometric roguelite game.
order: 3
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
      2
    </div>
    <div class="project-info-item">
      <div class="text-muted">Joined</div>
      Mid Development
    </div>
  </div>
</div>

<h1>Info</h1>
<iframe src="https://www.youtube.com/embed/y8qqFOUPx4o" frameborder="0" allowfullscreen style="aspect-ratio: 16/9; width:100%; height:100%">
</iframe>

<br>
<div class="row">
  <div class="col-md-6">
    <p><b>Eternal League</b> is a sci-fi isometric roguelite where you upgrade your character and become stronger. You play through the campaign or play in endless mode. The game is built with Unreal Engine.</p>
  </div>
  <div class="col-md-6">
    <figure>
      <iframe src="https://www.youtube.com/embed/NkHguVfurd0" frameborder="0" allowfullscreen style="aspect-ratio: 16/9; width:100%; height:100%"></iframe>
      <div class="caption">Gameplay video by @W3Gamer</div>
    </figure>
  </div>
</div>

<h4>Links</h4>
Website: <a href="https://www.eternalleague.com/" target="_blank" rel="noopener noreferrer">https://www.eternalleague.com/</a>
<br>Epic Games: <a href="https://store.epicgames.com/en-US/p/eternal-league-5e5031" target="_blank" rel="noopener noreferrer">https://store.epicgames.com/en-US/p/eternal-league-5e5031</a>
<br>Steam: <a href="https://store.steampowered.com/app/3542920/Eternal_League/" target="_blank" rel="noopener noreferrer">https://store.steampowered.com/app/3542920/Eternal_League/</a>


<h1>Contributions</h1>

- [Blockchain And Backend](#blockchain-and-backend)
- [Gameplay Features](#gameplay-features)
    - [Campaign](#campaign)
    - [Fog of War](#fog-of-war)
    - [Package Drop](#package-drop)
    - [Skill Tree](#skill-tree)
    - [Summon Allies](#summon-allies)
    - [UI And Bug Fixes](#ui-and-bug-fixes)


## Blockchain And Backend
I created the server using NestJS which is the layer between the ImmutableX and the game. I also handled setting up the the contracts, NFTs, products, metadata and everything blockchain related. In addition, I also setup the cloud database and storage needed for the game. The integration of the ImmutableX plugin and login system naturally was implemented by me.


## Gameplay Features

#### Campaign
This feature I added contains levels throughout the map UI. You need to complete the preceding levels before going to the next.

There are multiple campaigns in the game and each has a different layout.


#### Fog of War
Fog of war is also another one I added in the game. There are 2 components which are the post process and the gameplay mechanic.

The feature includes having vision of your player plus the vision of your allies. If you or your allies are hit by enemies, the enemy will also have vision as well for a duration.

There were also grass patches in the game before and that's also a few more layers considered for this feature.


#### Package Drop
This package drop is a big rocketship that lands at intervals in the game. You need to stay within the radius to get the rewards (heal, powerup, etc.). When the game still had pvp, players need to fight over it or else, you cannot claim the reward.


#### Skill Tree
The skill tree, which we call Glyph Tree in the game, is how you make your skills stronger. It can be increase damage, radius, duration, etc.


#### Summon Allies
You get gold from killing monsters and with this, you can purchase allies to summon and fight alongside you. They have a delay before dropping in the game.


#### UI And Bug Fixes
There were a couple of UIs and lots of rework in the game. The UI for the campaign, skill tree and the game hud for summoning allies were among others I developed. We use CommonUI for the UI.
