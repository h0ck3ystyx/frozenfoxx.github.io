---
layout: post
title: Hack Doom Update - Alpha
author: Foxx
tags:
 - games
 - development
 - hacking
---
The big day has finally arrived, [Hack Doom](https://github.com/frozenfoxx/hack-doom) is finally in Alpha!  What does this mean?  Basically means that it "works" but isn't ready yet for anyone that doesn't want to get his/her hands dirty standing it up.  There are still some hardcoded variables, and the layout is still kinda fugly, but it's quite functional and you can actually play a game with it now.

What's on the road to Beta?  Features and polish primarily so the progress report part of these is going to shift to beta prep.  The Certain wrapper has been moved from a Controller to a Singleton and is working out much better now.  There's definitely some polish in terms of invoking it but this is definitely much better now and automatically happens when you hook into the "rooms" path.  The singleton also removes a number of namespacing issues that prevented spawning which now, generally, aren't an issue.

The biggest annoyance is if you already have a browser accessing the "rooms" path and restart the server it doesn't always hook back up into the websocket properly.  This means that you can try to solve a flag but nothing *actually* happens until you refresh the page.  Annoying, but not the end of the world right now since once you reload you're perfect.  The colors on the buttons also change *only* if you refresh the page instead of fully dynamically.  Once I figure that out the interface will be almost feature complete.

Beta progress report:

- Need more challenges/levels.
- Need to dynamically change the colors of the buttons based on realtime database info over the websocket.
- Sectioning out the buttons out per area container to make the interface look nicer.
- Spawn demons for submitting already-solved and locked challenges.
- Lock down locked and solved challenges.
- Config file for variables for startup (location of Zandronum executable, Doom wad, etc).
- Hook those configuration file variables from the environment so they can be dynamically set if desired.
- Make a logo with the AmazDoom fonts.
