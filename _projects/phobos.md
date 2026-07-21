---
title: Phobos
description: Story driven isometric action RPG built in Unreal Engine 5.
order: 1
---
<div class="project-info-container">
  <div class="project-info-grid">
    <div class="project-info-item">
      <div class="text-muted">Role</div>
      Co-founder
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
      Start of Development
    </div>
  </div>
</div>

<h1>Info</h1>
<figure>
  <img src="/assets/media/projects/phobos/phobos-concept.jpg" alt="">
  <div class="caption">Phobos Concept Art</div>
</figure>


<b>Phobos</b> is a story driven isometric action RPG built in Unreal Engine 5.

The game started as a game jam entry many years ago that didn't even reach development. Recently, part of the group decided to start development. On the programming side, the team consists of only two developers including me.


<h1>Contributions</h1>



- [Project Setup And Workflow](#project-setup-and-workflow)
- [Core Framework](#core-framework)
- [AI](#ai)
    - [Boss AI](#boss-ai)
    - [Enemy AI](#enemy-ai)
- [Dialog System](#dialog-system)
- [Interaction System](#interaction-system)
- [Inventory, Equipment And Loadout Systems](#inventory-equipment-and-loadout-systems)
- [Serialization, Saving and Loading](#serialization-saving-and-loading)
- [Skill Tree](#skill-tree)
- [UI](#ui)
    - [Game HUD](#game-hud)
    - [Pause Menu And Controls autoplay muted Menu](#pause-menu-and-controls-autoplay-muted-menu)
- [VFX](#vfx)
    - [Attack](#attack)
    - [Skills](#skills)
- [Others](#others)


## Project Setup And Workflow
I started the project and set the repo up along with documentation on our Wiki. These are documentations about setting the project up, systems and conventions that devs should follow for a more maintainable project.

The game is built in Unreal Engine primarily in C++. We sparingly implement in Blueprints for child classes and for a few other cases where they are more suitable.

## Core Framework
The project is structured with our core game framework built on top of Unreal's Gameplay Ability System, logging utility and base classes and functionalities for our Character. In addition, I added the game loop system which manages the flow of the game from initialization to game and to end game. Currently, our end game is just game over as the game is still being developed.


## AI
I used Unreal's State Tree for enemy AI behavior and created State Tree tasks like Move To, Play Animation, Move Around Target and Use Ability among others concerning enemy combat. I chose this to learn the new tech and it can also be used for other things beyond enemy behavior. It can run on a normal Actor and doesn't necessarily require a Pawn or AIController. We try to make abilities be used by anyone as much as possible.
<br>
<br>
#### Boss AI
This is a POC for boss AI. The intro sequence also uses State Tree which makes it very convenient.
<video src="/assets/media/projects/phobos/phobos-ai-boss.webm" width="100%" playsinline controls autoplay muted loop></video>
<br>
#### Enemy AI
Also a POC for enemy AI just so that our level is more playable.
<div class="row">
  <div class="col-md-6">
    <figure>
      <video src="/assets/media/projects/phobos/phobos-ai-enemy1.webm" width="100%" playsinline controls autoplay muted loop></video>
      <div class="caption">Enemy does basic string</div>
    </figure>
  </div>
  <div class="col-md-6">
    <figure>
      <video src="/assets/media/projects/phobos/phobos-ai-enemy2.webm" width="100%" playsinline controls autoplay muted loop></video>
      <div class="caption">Enemy does basic string + dodge and strike</div>
    </figure>
  </div>
  <div class="col-md-6">
    <figure>
      <video src="/assets/media/projects/phobos/phobos-ai-enemy3.webm" width="100%" playsinline controls autoplay muted loop></video>
      <div class="caption">Enemy circles around before basic string</div>
    </figure>
  </div>
</div>


## Dialog System
<div class="row">
  <div class="col-md-6">
    <video src="/assets/media/projects/phobos/phobos-dialog.webm" width="100%" playsinline controls autoplay muted loop></video>
  </div>
  <div class="col-md-6">
    <p>This is another one I developed that uses a State Tree since it's more flexible. We can include any State Tree task in between the dialog if needed. Example is adding camera angles during the dialog sequence.</p>
  </div>
</div>


## Interaction System
<div class="row">
  <div class="col-md-6">
    <p>The interaction system is also another system I developed for the project. Interactables are composed of Interactable Actions, which can be added as needed. Each action implements its own logic.</p>
    <p>
      In this example, the Interactable object (blue cube) has 2 actions executed in order:
      <br>1. Display the pause menu widget (just for demonstration purposes)
      <br>2. Make the camera focus on the BP_Actor_InteractTrigger (white cube)
    </p>
  </div>
  <div class="col-md-6">
    <img src="/assets/media/projects/phobos/phobos-interaction-sample.jpg" alt="">
  </div>
</div>
<br>
<video src="/assets/media/projects/phobos/phobos-interaction-sample.webm" width="100%" playsinline controls autoplay muted loop></video>
<br>
<div class="row">
  <div class="col-md-6">
    <video src="/assets/media/projects/phobos/phobos-interaction.webm" width="100%" playsinline controls autoplay muted loop></video>
  </div>
  <div class="col-md-6">
    <p>The Interaction also has other actions as well. Another action executes a State tree which can be a dialog sequence as you will see on the third object interacted in the video.</p>
    <p>This approach makes it easier to build interactables by plugging in actions.</p>
  </div>
</div>


## Inventory, Equipment And Loadout Systems
<div class="row">
  <div class="col-md-6">
    <p>The items currently are the Potions (red box) and let's call the other one Power. You can equip 2 powers in your loadout (blue box).</p>
    <p>Potions are the typical usable and equippable items. Powers are items that contain multiple abilities once equipped.</p>
    <p>You have 2 loadouts that you can cycle through. This switches to the set of abilities from your next loadout.</p>
  </div>
  <div class="col-md-6">
    <img src="/assets/media/projects/phobos/phobos-inventory.jpg" alt="">
  </div>
</div>
<br>
<figure>
  <video src="/assets/media/projects/phobos/phobos-loadout.webm" width="100%" playsinline controls autoplay muted loop></video>
  <div class="caption">Showcase of switching loadouts</div>
</figure>


## Serialization, Saving and Loading
In this example shows the following:
1. Display skill tree with no skill points available
2. Gain skill points oby interacting with the interactable object
3. Spend the (3) skill points
4. Save
5. Restart the game (stopping and playing in editor)
6. Load the updated state of the interactable and skill tree

<video src="/assets/media/projects/phobos/phobos-serialization.webm" width="100%" playsinline controls autoplay muted loop></video>


## Skill Tree
For the skill tree, I developed a plugin that I've been improving over time. It consists of a custom data asset and an editor tool that can modify the asset. Once a node is activated, it executes the logic in its inherited node class. In this case, it applies a GameplayEffect.

This screenshot from the editor corresponds to the left skill tree shown in the 2 videos right after.

<figure>
  <img src="/assets/media/projects/phobos/phobos-skilltree.jpg" alt="">
  <div class="caption">Skill Tree Editor Tool</div>
</figure>

<div class="row">
  <div class="col-md-6">
    <figure>
      <video src="/assets/media/projects/phobos/phobos-skilltree-noupgrades.webm" width="100%" playsinline controls autoplay muted loop></video>
      <div class="caption">Without Upgrades</div>
    </figure>
  </div>
  <div class="col-md-6">
    <figure>
      <video src="/assets/media/projects/phobos/phobos-skilltree-withupgrades.webm" width="100%" playsinline controls autoplay muted loop></video>
      <div class="caption">With Upgrades</div>
    </figure>
  </div>
</div>


## UI
I used the CommonUI plugin to develop our UI with full gamepad support. Input is also managed when switching between the game and the UI menus.

#### Game HUD

Contains: 
1. Health bar (bottom-left)
2. Hotbar (bottom-mid)
3. Loadout (bottom-right)
4. Stamina bar (orange bar)
5. Dodge roll indicator (yellow dot below the character).

<img src="/assets/media/projects/phobos/phobos-hud.jpg" alt="">


#### Pause Menu And Controls autoplay muted Menu

In this example shows the following:
1. Displays the context switch of keyboard to gamepad input
2. Changes the input prompts depending on the input of the user
3. Pause menu and controls autoplay muted menu
4. Changing input binds

<video src="/assets/media/projects/phobos/phobos-ui.webm" width="100%" playsinline controls autoplay muted loop></video>


## VFX
We used a plugin initially from fab but I'm gradually replacing it one by one. We are targeting a toon-shaded visual style and will continue improving it over time.

#### Attack
<div class="row">
  <div class="col-md-6">
    <figure>
      <video src="/assets/media/projects/phobos/phobos-string-1-1.webm" width="100%" playsinline controls autoplay muted loop></video>
      <div class="caption">Attack 1-1</div>
    </figure>
  </div>
  <div class="col-md-6">
    <figure>
      <video src="/assets/media/projects/phobos/phobos-string-1-2.webm" width="100%" playsinline controls autoplay muted loop></video>
      <div class="caption">Attack 1-2</div>
    </figure>
  </div>
  <div class="col-md-6">
    <figure>
      <video src="/assets/media/projects/phobos/phobos-string-1-3.webm" width="100%" playsinline controls autoplay muted loop></video>
      <div class="caption">Attack 1-3</div>
    </figure>
  </div>
  <div class="col-md-6">
    <figure>
      <video src="/assets/media/projects/phobos/phobos-string-1-4.webm" width="100%" playsinline controls autoplay muted loop></video>
      <div class="caption">Attack 1-4</div>
    </figure>
  </div>
  <div class="col-md-6">
    <figure>
      <video src="/assets/media/projects/phobos/phobos-string-2-1.webm" width="100%" playsinline controls autoplay muted loop></video>
      <div class="caption">Attack 2-1</div>
    </figure>
  </div>
  <div class="col-md-6">
    <figure>
      <video src="/assets/media/projects/phobos/phobos-string-2-2.webm" width="100%" playsinline controls autoplay muted loop></video>
      <div class="caption">Attack 2-2</div>
    </figure>
  </div>
  <div class="col-md-6">
    <figure>
      <video src="/assets/media/projects/phobos/phobos-string-2-3.webm" width="100%" playsinline controls autoplay muted loop></video>
      <div class="caption">Attack 2-3</div>
    </figure>
  </div>
  <div class="col-md-6">
    <figure>
      <video src="/assets/media/projects/phobos/phobos-string-2-4.webm" width="100%" playsinline controls autoplay muted loop></video>
      <div class="caption">Attack 2-4</div>
    </figure>
  </div>
</div>

#### Skills
<div class="row">
  <div class="col-md-6">
    <figure>
      <video src="/assets/media/projects/phobos/phobos-skill-1-4.webm" width="100%" playsinline controls autoplay muted loop></video>
      <div class="caption">Skill 1-4</div>
    </figure>
  </div>
  <div class="col-md-6">
    <figure>
      <video src="/assets/media/projects/phobos/phobos-skill-2-2.webm" width="100%" playsinline controls autoplay muted loop></video>
      <div class="caption">Skill 2-2</div>
    </figure>
  </div>
  <div class="col-md-6">
    <figure>
      <video src="/assets/media/projects/phobos/phobos-skill-2-4.webm" width="100%" playsinline controls autoplay muted loop></video>
      <div class="caption">Skill 2-4</div>
    </figure>
  </div>
</div>

## Others
- Audio
- Camera System
- Full Gamepad Support
- Quest System
- UI
-   Settings
