---
layout: post
title: Hack Doom Update - Certain Output
author: Foxx
tags:
 - games
 - development
 - hacking
---
The *Certain* wrapper for [Hack Doom](https://github.com/frozenfoxx/hack-doom) has been cleaned up and is now feature complete unless I uncover some extra functionality we need.  The latest edits will now only send output that matches recognized game commands (like players joining, hackswitches being activated, etc).  This means the *Certain* wrapper will start up *Zandronum*, start up a websocket server via *websocketd*, engage or disengage verbose modes, and finally but most importantly take server commands and output a recognized subset of server output.  This is awesome and means *Certain* is ready for prime-time testing!

So, what's left?  *Gloom* really, and that's about it before we can really begin testing!  Naturally all pull requests are welcome, there will be a new *gloom* subdirectory in its own branch for working on the *Gloom* project.  Unless I receive a better suggestion I'm going to try and do this in *Rails* simply because a lot of very similar and successful CTF dashboards have been done in it, it's in Ruby, and it's very popular.  I'm thinking an active view and active model with a good set of controllers to handle passing data around should finish this off.  Naturally the first version's going to be pretty ugly, but that's okay as long as it works.

Overall progress report:

- Two example challenges are now up and cover both downloadable types and basic web page types.
- hackdoom.pk3 Assets file for Doom compiled with source available under *assets/*.
- hackdoom001 prototype level almost complete.  Needs a nice little stimpack in the first secret area and needs the name set, but is otherwise complete with properties YAML to boot.
- Certain wrapper is done!
- Move to Zandronum completed, only thing that hurts is that when running *pukename* it complains to players that the server might be cheating.  Looking into ways to resolve this.
- Gloom hasn't been started yet.  AJAX requirement is going to stall progress until I find a web dev to help build it.
- More sample CTF challenges need to be written.
