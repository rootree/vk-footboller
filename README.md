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

After preloader window: 

![Preloader](https://github.com/rootree/vk-footboller/blob/master/IMG/preloader.png?raw=true "Preloader window")

Users will be the main screen of the game:

![Main screen](https://github.com/rootree/vk-footboller/blob/master/IMG/main.jpg?raw=true "Main screen")

On the main screen there are several options:

1. Change logo of users team
2. Players in the team
3. Shop of football players
4. Sponsors list
5. Competitions
6. List of friends and their teams
7. User's stadion

### User's football players

![Players](https://github.com/rootree/vk-footboller/blob/master/IMG/my_team.png?raw=true "Players")

On this screen the user can define main players. Each player has a specific type:

- forward
- quarterback
- linebacker
- goalkeeper

The type influences on behavior of the team, either the team makes a lot of goals or can defend itself. On this screen the user can increase parameters of the players, sell them, or send them to the reserve.

### Football players shop

![Shop](https://github.com/rootree/vk-footboller/blob/master/IMG/shop.jpg?raw=true "Shop")

In the shop a user can buy players and coaches, then in the team window the user can change the team players.

### Sponsors

![Sponsors](https://github.com/rootree/vk-footboller/blob/master/IMG/sponsor.png?raw=true "Sponsors")

On the sponsors screen a user can choose sponsors which will support user's team (multiplicator on results of the matches)

### Tour selection

When a user has 11 players in his team, he can play with other users or can take part in championship.

![Tour selection](https://github.com/rootree/vk-footboller/blob/master/IMG/tour_selection.jpg?raw=true "Tour selection")

There are three type of competitions

1. Match against another user in a social network
2. Match against a real team
3. Participation in a championship

#### Match against another user

A user can choose another user to play against his team

![Choose competitor](https://github.com/rootree/vk-footboller/blob/master/IMG/choose_competitor.jpg?raw=true "Choose competitor")

After when user has chosen a competitor, will be shown several windows about the process of the game, and in the end of the game will be a game result.

A window when user wins

![Win](https://github.com/rootree/vk-footboller/blob/master/IMG/win.jpg?raw=true "Win")

Otherwise

![Win](https://github.com/rootree/vk-footboller/blob/master/IMG/lose.png?raw=true "Win")

After the match a user can see detailed match statistics.

![Match statistics](https://github.com/rootree/vk-footboller/blob/master/IMG/result_of_match.png?raw=true "Match statistics")

#### Match against a real team

This competition against predefined teams.

#### Participation in a championship

To be continued ...