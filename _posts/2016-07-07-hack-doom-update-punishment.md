---
layout: post
title: Hack Doom Update - Punishment
author: Foxx
tags:
 - games
 - development
 - hacking
---
Moving right along, [Hack Doom](https://github.com/frozenfoxx/hack-doom) now supports "punishment" spawning.  This means that if you try to submit an incorrect flag *or* somehow try to submit one that's already solved then the game will immediately spawn an extra monster wave.  This will either happen in the Area a Core Challenge belongs to __or__ if it is an Edge Challenge it will pick a random Area.

Why do this?  First it's fun, as more ways for the game to interact with the players is usually a good thing.  Second though is a more creative method of discouraging brute force attacks.  If the Control team tries to just spam their way to a flag then they're going to get the Marines killed.
Beta progress report:

- Need more challenges/levels.
- Need to dynamically change the colors of the buttons based on realtime database info over the websocket.
- Sectioning out the buttons out per area container to make the interface look nicer.
- Lock down locked and solved challenges.
- Config file for variables for startup (location of Zandronum executable, Doom wad, etc).
- Hook those configuration file variables from the environment so they can be dynamically set if desired.
- Make a logo with the AmazDoom fonts.
