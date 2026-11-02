---
title: Steam Lobby Info Dump
draft: false
tags:
  - game-dev
date: 2026-09-17
publish: true
---
This is a random info dump of my understanding of the Facepunch Steamworks library. This is mainly used to allow for Steam integration for multiplayer games. Getting it setup is a bit of a pain due to the lack of documentation, but its pretty straightforward once you get it running. You're likely going to rely on the Steamworks official documentation, though that can get a bit confusing too.

This video largely helped me out on my setup: https://www.youtube.com/watch?v=kBgnIJUfQak&themeRefresh=1

## Random Stuff

* `SteamClient.Name` - The player's steam username
* `Lobby.members` - Fetches a list of lobby members
* `OnGameLobbyJoinRequested()` - Event called when a person joins a lobby (Ex. By going to your friends list, clicking on your friend that has a lobby, and clicking "Join Game")
* `OnRichPresenceJoinRequested()` - Supposedly called when a player accepts an invitation to a game from their friend
* Cases to consider for a lobby: Lobby created, lobby member joining, leaving lobby as host, leaving lobby as a member, joining via steam, joining via invite, disconnects