# VK Footboller
Football manager for social networks (Facebook, VKontakte, etc.)

## Content

1. Overview
2. Architecture
3. Game rules


## Overview

VK Footboller is a football manager for social networks like Facebook, Odnoklassniki, VKontakte, etc. Idea of this game is to give friends play with each other, organize their own football teams, to be involved in competition in their university, city, or country, discuss.

To add a new social network is a matter of using its API. Right now implemented only VKontakte's API, to add a new API is very easy step by creating a new class with the same Interface that VKontakte has.

In order to see a working version of this game you need an account in VKontakte. The link for the game is https://vk.com/app2014049_4778426. On this moment, in VKontakte there are 220 000 players.


## Architecture

There are four main elements in the game:

1. [Preloader] (https://github.com/rootree/vk-footboller-preloader)
2. [Client] (https://github.com/rootree/vk-footboller-client)
3. [Server] (https://github.com/rootree/vk-footboller-server)
4. [CMS] (https://github.com/rootree/vk-footboller-content-system)

### Preloader

When a user opens the game in a social network, first, will be loaded the preloader. The preloader is a small application, that checks that the user has all privileges to play in the game (get list of friends, permission to post on a wall, etc.). If the user doesn't have enough privileges in this case will be shown a window with settings of the application where the user can change all necessary settings and privileges. If everything is OK with settings and privileges, the preloader will start loading the main application and its resources.

### Client

All interaction with the game happen in the client. The client has a lot of windows, about them will be explained in Game rules section. The client communicate with the server each time when a user does some important for the game action (team settings, buying a new player, a new message on a friend's wall).

### Server

The server serves for three main goals:

1. tracks users progress
2. communicates with API of a social network
3. validates all input from the client

### CMS

With CMS's help it's easy to update all content in the game. By content I mean:

- football players
- coaches
- stadiums
- sponsors
- teams

For example, if you need to add a new football player, you need to upload his avatar and his photo on the sports ground, then fill in settings (type, level, price, etc.). With CMS it's really easy to do.

After when all changes are made in the CMS, will be generated an update for the client and for the server, and when the game will be deployed, users will see all new changes.


## Game rules

![Preloader](/IMG/Preloader.png?raw=true "Optional Title")
