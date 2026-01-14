---
title: MaaS Studio
description: An application to be the producer of your own digital space for an immersive experience.
order: 4
---
<div class="project-info-container">
  <div class="project-info-grid">
    <div class="project-info-item">
      <div class="text-muted">Role</div>
      Lead Software Engineer
    </div>
    <div class="project-info-item">
      <div class="text-muted">Game Engine</div>
      Unreal Engine
    </div>
    <div class="project-info-item">
      <div class="text-muted">Programmers</div>
      6
    </div>
    <div class="project-info-item">
      <div class="text-muted">Joined</div>
      Mid project
    </div>
  </div>
</div>

<h1>Info</h1>
<b>MaaS Studio</b> is a project used to convert your environment into an immersive experience stage production.

There are multiple components for as far as the user is concerned:
1. The plugin used along with your UE project
2. The MaaS Studio application

The application has 2 windows when opened. One is the screen and the other one was full of controls, kind of like a mixer with lots of switches.


<h1>Contributions</h1>

- [Management / Lead](#management--lead)
- [Core Framework](#core-framework)
    - [Local Messaging Server](#local-messaging-server)
    - [Loading External Packages](#loading-external-packages)
    - [Serialization](#serialization)
- [Tools](#tools)
    - [Build Tool](#build-tool)
    - [Build Pipeline](#build-pipeline)


## Management / Lead
Being a lead engineer requires doing decision making on technical directions for the app, management, lots of documentations, flowcharts and also training the engineers.


## Core Framework
Since the project started as a POC, the state of project the was not designed to be scalable which was the gradually improved over time since requirements kept coming in.


#### Local Messaging Server
There was a requirement to add some communication system to the app from external. A few of them were from a launchpad hardware and an external application that the other team made. So I implemented a messaging server via websocket to communicate with external.


#### Loading External Packages
This involves loading an external package file into MaaS Studio application. There were a lot of considerations when I did this feature like encryption, integrity of the package being loaded, consistency of the level when loaded, etc. There were a couple of guidelines that I documented for the team. The plan was to eliminate those as the development went on.


#### Serialization
I added our custom serializer/deserializer so that the user can edit the save file. This was a requirement. This serializer/deserializer was also used for the messaging server from the [Local Messaging Server](#local-messaging-server) section. I just added mappers to translate their message into our app's format.


## Tools

#### Build Tool
The custom build tool is a one click button which involves using Unreal's build pipeline and a few more extra steps after like unpacking and repacking the pak file among other things. This is an editor tool used in Unreal to build instead of using Unreal's default "Package Project".

The main executable is built from C#.


#### Build Pipeline
I developed our build pipeline using Jenkins. This also uses the build tool from the [Build Tool](#build-tool) section and it also automates upload to our cloud storage.

Once the build process is done, the user can see the environment in the MaaS Studio application, download it and run the level realtime.

