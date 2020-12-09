---
layout: page
title: Voyage 
genre: Document
permalink: /VoyageDesignDoc/
---

<center>  <h4>Design Document for:</h4><h1 style="font-size:50px;">Voyage </h1><h4>by Jingyu Zhuang (zhuanj2@rpi.edu)</h4></center>

  

# Table of Contents

- [Table of Contents](#table-of-contents)
- [Game Overview](#game-overview)
- [Game Philosophy](#game-philosophy)
  - [Why Create this game](#why-create-this-game)
  - [Immediate and Long Term Projected SocioCultural Project Impact](#immediate-and-long-term-projected-sociocultural-project-impact)
  - [Predecessor or previous games/distinctive factors in this genre](#predecessor-or-previous-gamesdistinctive-factors-in-this-genre)
  - [Target Audience](#target-audience)
- [Common Questions](#common-questions)
  - [What is the Game](#what-is-the-game)
        - [Where Does the Game Take Place?](#where-does-the-game-take-place)
        - [What Do the Players Do?](#what-do-the-players-do)
        - [How Many Characters are There?](#how-many-characters-are-there)
        - [What is the Main Focus?](#what-is-the-main-focus)
        - [What’s Different?](#whats-different)
- [Design History](#design-history)
  - [Version 1.0](#version-10)
        - [Version 1.1](#version-11)
        - [Version 1.2](#version-12)
        - [Version 1.3](#version-13)
- [Feature Set](#feature-set)
  - [General Features](#general-features)
        - [Multiplayer Features](#multiplayer-features)
        - [Gameplay](#gameplay)
- [User Interface](#user-interface)
  - [Overview](#overview)
        - [Login](#login)
        - [In Game](#in-game)
- [Multiplayer Game](#multiplayer-game)
  - [Overview](#overview)
  - [Max Players](#max-players)
  - [Servers](#servers)
  - [Database](#database)


# Game Overview
Voyage is a virtual travel experience. It simulates the entire Earth with Google Map geo-data and presents it to players as a huge Multiplayer Sandbox Open World.

It is also a shared environment. Players get to meet each other in this game, share their journey and make their own marks in the world. Their creations will be in this world forever, not only seen by all the other players traveling to the place, but also lighting up the region.

The project is founded on September 2020 during the global pandemic and the goal is to give players positive energy and a sense of hope.

# Game Philosophy
### Why Create this game
In 2020, The spread of the global pandemic has forced everyone to go into lockdown and self-quarantine. While everyone is trapped by the endless growing number of infections, I decided to start this video game project for people to hangout in a virtual space. 
### Immediate and Long Term Projected SocioCultural Project Impact
The immediate goal of the project is to bring people positive energy and a sense of hope during the 2020 COVID-19 Pandemic. The long term objective is to build a spiritual connection between people around the globe regardless of their culture and ethnic.
### Predecessor or previous games/distinctive factors in this genre
[Where on Google Earth is Carmen Sandiego?](https://experiments.withgoogle.com/where-on-earth)

[Sky: Children of the Light](https://thatskygame.com/)

[Death Stranding](https://store.steampowered.com/app/1190460/DEATH_STRANDING/)

[Ingress](https://www.ingress.com/)
### Target Audience
**Literally everyone!** The intention is to build a virtual shared environment that everyone can have fun in and take care of.

# Common Questions
### What is the Game
It is a multiplayer sandbox openworld simulating the true-to-size real world.
### Where Does the Game Take Place?
The game takes place at any where on the Earth. Players simply choose their desired coordinate and start traveling.
### What Do the Players Do?
Explore the world and leave their marks. Meet other players and travel together.
### How Many Characters are There?
Just one.
### What is the Main Focus?
The initial focus is for people to have a virtual hangout experience during the pandemic. And as the project progresses it slowly transformed to a multiplayer social experience to connect people together.
### What’s Different?
The project is experimental mainly because its use of Realtime Geodata. The entire world is procedurally generated simulating the entire planet.

# Design History
### Version 1.0
Version 1.0 includes a complete single-player travel experience. It has:

1.Procedurally generated world with Google Map Geodata.

2.Magic cube at landed region for players to explore and activate to revitalize the world.

### Version 1.1
Version 1.1 includes a Semi-multiplayer update. It has:

1.A creation system allowing players to plant flowers and trees in the world.

2.A online server and database syncing creations and presents them to all other players.

### Version 1.2
Version 1.2 includes a Multiplayer update. It has:

1.An account system holding all player datas.

2.A real time multiplayer server, players can now meet each other and travel together.

### Version 1.3
Version 1.3 includes a big UI update. It has:

1.A complete UI system including all systems(Creation, Stats, Menus, Maps, etc).

2.A minimap giving players a top down view of the surrounding.

# Feature Set
### General Features
Huge World

3D Graphics

User Generating Contents
### Multiplayer Features
Real Time Multiplayer

Everyone Shares the Same World
### Gameplay
Creation

Traveling

# User Interface
### Overview
To start the game players need to go through a seperate starter page with a login page and an embedded map. In game UI System are contained inside a UI wheel system

### Login

<img src="/img/GoogleMapUI.gif" alt="1" class="center" width="800"/>

### In Game

<img src="/img/PlantTree.gif" alt="1" class="center" width="800"/>


# Multiplayer Game

<img src="/img/MultiPlayer.gif" alt="1" class="center" width="800"/>

### Overview
The game supports real time multiplayer and every player shares the same world. It also has a cloud database to hold all players' creations and present them to all other players.

### Max Players
To have the ideal experience, the server can hold up to 200 players at maximum.

### Servers
The servers adopts a classic Client-Server model, because of the potential large number of players in the same world. With the Client-Server architecture players latency would not affect each other.

### Database
The cloud database stores all information including all creations and all player accounts. The database also keeps track of all acitve players in the world.

