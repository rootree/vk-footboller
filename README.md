# VK Footboller
VK Footboller is a football manager for social networks (Facebook, VKontakte, etc.)

## Content

1. Overview
2. Architecture
3. Game rules


## Overview

VK Footboller is a football manager for social networks like Facebook, Odnoklassniki, VKontakte, etc. A main idea of this game is to give friends in a social network an opportunity to play with each other, organize their own football teams, to be involved in championships in universities, cities, or countries.

This game can be adapted for different social networks. Right now you can find this game only in VKontakte's, but to launch the game on a new social network is very easy, you need to create a new API adapter for the social network with the same Interface that VKontakte has.

In order to see a working version of the game you need an account in VKontakte (a link on the game https://vk.com/app2014049_4778426). On this moment, 220 000 players are installed the game in VKontakte.

## Architecture

There are four main elements in the game:

1. [Preloader] (https://github.com/rootree/vk-footboller-preloader)
2. [Client] (https://github.com/rootree/vk-footboller-client)
3. [Server] (https://github.com/rootree/vk-footboller-server)
4. [CMS] (https://github.com/rootree/vk-footboller-content-system)

### Preloader

When a user opens the game in a social network, first will be loaded the preloader. The preloader is a small application, that checks that a user has all permissions to play in the game (get list of friends, permission to post on the wall, etc.). If a user doesn't have enough privileges in this case will be shown a window with the settings of the application where a user can change all necessary settings and privileges. If everything is OK with settings and privileges, the preloader will start loading the main application and its resources.

### Client

All interaction with a user happens in the client. The client has lots of windows, about them will be explained in the Game Rules section. The client communicates with the server each time when a user commits some actions (changes in a team, buying a new football player, a new message on a friend's wall).

### Server

The server serves for three main goals:

1. saves all changes in a user's profile
2. communicates with a social network via API
3. validates all input from the client

### CMS

In CMS a moderator can easily update all content in the game. Can be changed:

- football players
- coaches
- stadiums
- sponsor companies
- teams

For example, if you want to add a new football player, you should upload his avatar and his photo on the sports ground, then setup his parameters (type, level, price, etc.).

Then, when all changes are made in the CMS, will be generated an update package for the client and for the server, and when the game will be deployed the package will be rollout.


## Game rules

After the preloader window: 

![Preloader](https://github.com/rootree/vk-footboller/blob/master/IMG/preloader.png?raw=true "Preloader window")

Users will see the main screen of the game:

![Main screen](https://github.com/rootree/vk-footboller/blob/master/IMG/main.jpg?raw=true "Main screen")

On the main screen there are several options:

1. Change a logo of a user's team
2. Players in the team
3. Shop of football players
4. Sponsors list
5. Competitions
6. List of friends and their teams
7. User's stadion

### User's football players

![Players](https://github.com/rootree/vk-footboller/blob/master/IMG/my_team.png?raw=true "Players")

On this screen a user can define a main list of players. Each player has a specific role:

- forward
- quarterback
- linebacker
- goalkeeper

The role can influence on behavior of the team, either the team makes a lot of goals or can better defend itself. On this screen a user can increase parameters of the players, sell them, or send them to the reserve.

### The Shop of football players 

![Shop](https://github.com/rootree/vk-footboller/blob/master/IMG/shop.jpg?raw=true "Shop")

In the shop a user can buy players and coaches, then on the team screen a user can change the team players.

### Sponsors

![Sponsors](https://github.com/rootree/vk-footboller/blob/master/IMG/sponsor.png?raw=true "Sponsors")

On the sponsors' screen a user can choose sponsors which will support the team. A sponsor can have an effect on the rewards which the user can get in the end of each competition.

### Tour selection

When a user has a full team (11 football players), he/she can play with other users or can take participation in championships.

![Tour selection](https://github.com/rootree/vk-footboller/blob/master/IMG/tour_selection.jpg?raw=true "Tour selection")

There are three type of competitions

1. Match against another user in a social network
2. Match against a real team
3. Participation in a championship

#### Match against another user

A user can choose with whom he/she wants to play

![Choose competitor](https://github.com/rootree/vk-footboller/blob/master/IMG/choose_competitor.jpg?raw=true "Choose competitor")

When user has chosen a competitor, will be shown several screens about the process of the game, and in the end will be shown the game result.

The screen when user has won

![Win](https://github.com/rootree/vk-footboller/blob/master/IMG/win.jpg?raw=true "Win")

Or, will be shown the screen of defeat 

![Win](https://github.com/rootree/vk-footboller/blob/master/IMG/lose.png?raw=true "Win")

After the match a user can see detailed statistics of the match.

![Match statistics](https://github.com/rootree/vk-footboller/blob/master/IMG/result_of_match.png?raw=true "Match statistics")

#### Match against real teams

This competition against predefined teams.

#### Participation in championships

For the each game, between players in a social network, players get some amount of points. If a player has enough points he/she can participate in championships. Championships are conducted once a week. There are four type of area for championships:

- Social network
- Country
- City
- University

Results of championships are being made automatically based on the players' teams. Than more powerful the team then higher place the user will get.

![Match statistics](https://github.com/rootree/vk-footboller/blob/master/IMG/tour.jpg?raw=true "Match statistics")

If a user gets the first, the second, or the third place he/she will be informed about it and he/she will get additional points, which can be exchanged on the new football players or on a new stadium for the team. Everyone in the game will be able to see the winners for one week until the next championships.

![Match statistics](https://github.com/rootree/vk-footboller/blob/master/IMG/tour_win.png?raw=true "Match statistics")

All participants can see detailed statistics of the championships.

![Match statistics](https://github.com/rootree/vk-footboller/blob/master/IMG/gourp_table.png?raw=true "Match statistics")
