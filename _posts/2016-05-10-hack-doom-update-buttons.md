---
layout: post
title: Hack Doom Update - Buttons
author: Foxx
tags:
 - games
 - development
 - hacking
---
It's been quiet, but there's been some awesome progress on [Hack Doom](https://github.com/frozenfoxx/hack-doom).  There's been a shift in functionality in the backend but the short of it is that I've solved the "multiple" and "unpredictable" command sending issues.  More importantly I've also with the help of quote managed to get buttons working for raising/lowering Hacklifts, opening Hackdoors, and so forth!  This is *awesome* stuff that paves the way towards the final stretch of the project.

As it stands now, you can click on some checkboxes to raise and lower Hacklifts and open Hackdoors in the level.I still need to write up a method that will take the doom_log output of secrets being found, players dying, etc and use it to signal challenges being unlocked and so forth, but that can come after making the boxes for the challenges.  The other big change is that the actual code for doing the commands down to Certain no longer reside in the Channel.  Instead the Channel (RoomChannel in this case) sends a string to the CertainController.update() function which executes the command.  This solves a number of issues but most importantly means that when a Gloom user clicks a button, *one* command gets sent to the game.  Because of the way the websockets work, when I was sending this as an update to everyone you got multiple clients sending the command, which created unpredictable behavior.  This also means that, for the moment, I'm not creating a log of everything that gets sent.  As is seen in the code this is easy to add back in, but I think I can wait until the game actually has a functional prototype before worrying about the logging.

The DoomChannel is still making logs in the DoomLog model over a websocket for real-time.  This seems pretty effective and with some tweaking I believe we can have it trigger changes in the RoomChannel.  In the previous setup, Messages would be rendered in real-time as they were created.  I think I can do something similar only instead of rendering I'd have it pass the string received to a function in RoomController (or possibly RoomChannel) that alters the rendered layout.

Overall progress report:

- Two example challenges are now up and cover both downloadable types and basic web page types.
- hackdoom.pk3 Assets file for Doom compiled with source available under *assets/*.
- hackdoom001 prototype level almost complete.  Needs a nice little stimpack in the first secret area and needs the name set, but is otherwise complete with properties YAML to boot.
- Certain wrapper is done!
- Move to Zandronum completed, only thing that hurts is that when running *pukename* it complains to players that the server might be cheating.  Looking into ways to resolve this.
- Gloom is well underway.  Successfully launches and communicates with Certain, has clickable buttons for Hacklifts and Hackdoors, and those buttons actually send reliable, correct commands back down to Certain.
- More sample CTF challenges need to be written.
