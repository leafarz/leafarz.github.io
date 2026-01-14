---
title: UE Sandbox
description: Personal project serving as a sandbox for anything programming / Unreal Engine related.
order: 99
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
      1
    </div>
    <div class="project-info-item">
      <div class="text-muted">Joined</div>
      Start of Development
    </div>
  </div>
</div>


<h1>Info</h1>

<b>UE Sandbox</b> is a sandbox project for anything programming / Unreal Engine related. The main purpose of this project is for experimentation and learning.

<h4>Links</h4>
GitHub Repo: <a href="https://github.com/leafarz/ueSandbox" target="_blank" rel="noopener noreferrer">https://github.com/leafarz/ueSandbox</a>

<h1>Contributions</h1>
The project was developed by me. Each feature contains their own levels.

- [Convolution Kernels](#convolution-kernels)
- [Disintegration](#disintegration)
- [Distance Field](#distance-field)
- [Gerstner Wave](#gerstner-wave)
- [Glass Materials](#glass-materials)
- [Jump Flood Algorithm](#jump-flood-algorithm)
- [Paint Tech Demo (Unfinished Swan inspired)](#paint-tech-demo-unfinished-swan-inspired)
- [Pulse Effect Material](#pulse-effect-material)
- [Random Splats](#random-splats)
- [Snow Trail](#snow-trail)
- [Toon / Cel shading](#toon--cel-shading)
- [Wet Surface Material](#wet-surface-material)



## Convolution Kernels
<div class="row">
  <div class="col-md-6">
    <img src="https://media.githubusercontent.com/media/leafarz/resources/master/ueSandbox_06.gif">
  </div>
  <div class="col-md-6">
    <p>These are a post process materials that use different convolution kernels.</p>
    <p>
      There are 4 shown here from left to right:
      <br>1. Gaussian Blur
      <br>2. Ridge Detection
      <br>3. Sharpen
      <br>4. Sobel
    </p>
  </div>
</div>


## Disintegration
<div class="row">
  <div class="col-md-6">
    <p>This is a surface material that uses a gradient noise with 2 cutoff values. One value is for the bright emissive effect and the other one for masking out the surface.</p>
  </div>
  <div class="col-md-6">
    <img src="https://media.githubusercontent.com/media/leafarz/resources/master/ueSandbox_07.gif">
  </div>
</div>

## Distance Field
<div class="row">
  <div class="col-md-6">
    <img src="https://media.githubusercontent.com/media/leafarz/resources/master/ueSandbox_02.gif">
  </div>
  <div class="col-md-6">
    <p>This is a surface material that uses distance fields to check the surroundings. It adds to world position offset if near another object.</p>
  </div>
</div>

## Gerstner Wave
<div class="row">
  <div class="col-md-6">
    <p>This gerstner wave is a surface material based on an implementation I tried out from <a href="https://developer.nvidia.com/gpugems/gpugems/part-i-natural-effects/chapter-1-effective-water-simulation-physical-models" target="_blank" rel="noopener noreferrer">Nvidia GPU gems</a>.</p>
    <p>It combines multiple sin and cos functions with varying wavelengths, amplitudes, rates, directions, etc to produce this wavelike motion.</p>
  </div>
  <div class="col-md-6">
    <img src="https://media.githubusercontent.com/media/leafarz/resources/master/ueSandbox_03.gif">
  </div>
</div>

## Glass Materials
<div class="row">
  <div class="col-md-6">
    <img src="https://media.githubusercontent.com/media/leafarz/resources/master/ueSandbox_10.jpg">
  </div>
  <div class="col-md-6">
    <p>These are surface materials to showcase different glass-like effects.</p>
    <p>The one on the left uses thin translucent shading model which requires Unreal's experimental EnableOrderIndependentTransparency feature. The one on the right uses dithering. The one at the back uses the standard Translucent blend mode.</p>
  </div>
</div>

## Jump Flood Algorithm
<div class="row">
  <div class="col-md-6">
    <p>This is a surface material that uses the jump flood algorithm using to fill the surrounding areas iteratively up until a certain point. I tested this to try out very thick outlines.</p>
  </div>
  <div class="col-md-6">
    <img src="https://media.githubusercontent.com/media/leafarz/resources/master/ueSandbox_11.png">
  </div>
</div>

## Paint Tech Demo (Unfinished Swan inspired)
<div class="row">
  <div class="col-md-6">
    <img src="https://media.githubusercontent.com/media/leafarz/resources/master/ueSandbox_12.gif">
  </div>
  <div class="col-md-6">
    <p>This is a surface material that uses a mask render target to display it over the surface of the object. In this case we just show it as black.</p>
    <p>When the bullet collides with the object's surface, it tries to get the impact UV. The brush texture is drawn into the mask using the UV to position it correctly on the surface</p>
  </div>
</div>

## Pulse Effect Material
<div class="row">
  <div class="col-md-6">
    <p>This is a post process material which aims to experiment on arrays in materials. There are no array nodes in the material editor so what I did here is I put the location into a render target as location (rgb) per pixel and used it as a buffer. I pass that buffer to the material so the material can process the data and display accordingly.</p>
  </div>
  <div class="col-md-6">
    <img src="https://media.githubusercontent.com/media/leafarz/resources/master/ueSandbox_04.gif">
  </div>
</div>

## Random Splats
<div class="row">
  <div class="col-md-6">
    <img src="https://media.githubusercontent.com/media/leafarz/resources/master/ueSandbox_09.jpg">
  </div>
  <div class="col-md-6">
    <p>This is a surface material that manipulates the UV to display a single texture multiple times.</p>
    <p>For each cell, a random location and rotation is used to display the texture. It then samples the neighbor cell's UV to draw the continuation of the texture especially if it gets cut.</p>
  </div>
</div>

## Snow Trail
<div class="row">
  <div class="col-md-6">
    <p>This is a surface material that is similar to <a href="#paint-tech-demo-unfinished-swan-inspired" target="_blank" rel="noopener noreferrer">Paint Tech Demo Section</a>.</p>
    <p>The same logic is used: getting the UV where the foot is location and draw a brush texture to the mask. This time the mask is used to offset the floor geometry and also to blend between the snow and soil texture (might be difficult to see) when the offset gets low enough.</p>
  </div>
  <div class="col-md-6">
    <img src="https://media.githubusercontent.com/media/leafarz/resources/master/ueSandbox_01.gif">
  </div>
</div>

## Toon / Cel shading
<div class="row">
  <div class="col-md-6">
    <img src="https://media.githubusercontent.com/media/leafarz/resources/master/ueSandbox_05.png">
  </div>
  <div class="col-md-6">
    <p>This is a surface material created to experiment with a toon shading effect. It uses a common implementation which shows flat colors based on bands and with added specular highlight.</p>
  </div>
</div>

## Wet Surface Material
<div class="row">
  <div class="col-md-6">
    <p>This is a surface material to experiment with the SingleLayerWater shading material. The water waves came from the idea from the <a href="#gerstner-wave" target="_blank" rel="noopener noreferrer">Gertner Wave Section</a> but with a very simplified version.</p>
    <p>To achieve the wet effect in the material, I sampled the wave position using the pixel’s world X and Y on the wall but using the Time minus 1s.</p>
    <p>The resulting Z (height) value from sampling is used as a mask. If the world location of the pixel is lower than the Z, it is rendered as wet.</p>
  </div>
  <div class="col-md-6">
    <img src="https://media.githubusercontent.com/media/leafarz/resources/master/ueSandbox_08.gif">
  </div>
</div>


