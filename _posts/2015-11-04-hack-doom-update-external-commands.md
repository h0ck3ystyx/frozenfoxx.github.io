---
layout: post
title: Hack Doom Update - External Commands
author: Foxx
tags:
 - games
 - development
 - hacking
---
Just a quick update on [Hack Doom](https://github.com/frozenfoxx/hack-doom), I've reached a major milestone, External Commands in the Certain wrapper are complete!  Naturally it's always possible to add more commands later but now you can successfully start up Certain, have it open Hackdoors, spawn enemies, and otherwise perform all functions on a game of Hack doom that would come from the Gloom webserver!

It was a little painful but eventually I settled down on a Thread-based mechanism instead of a Celluloid one.  Why?  Had code that worked, simple as that.  Celluloid's awesome no doubt but this simply worked better.  If you have a better idea as to how to handle simultaneous streaming input/output then by all means submit a pull request.  I'm sorry there's still no formal test cases but to be fair I'm not 100% certain HOW you'd test this since it requires a running game.  At the moment my own test-cases straight-up invoke Certain with the right options so if there's a good idea out there of how to handle this please submit a pull request.

Anyway, that's a big chunk of Hack Doom's functionality done.  Here's currently where we stand:

- hackdoom.pk3 Assets file for Doom compiled with source available under assets/
- hackdoom001 prototype level almost complete.  Needs a nice little stimpack in the first secret area and needs the name set, but is otherwise complete with properties YAML to boot
- Certain wrapper is half-implemented.  Allows you to launch with a map set, registers valid commands on STDIN and translates them to Doom.
- Move to Zandronum completed, only thing that hurts is that when running *pukename* it complains to players that the server might be cheating.  Looking into ways to resolve this.
- Gloom hasn't been started yet.  Waiting for Certain to be finished first.  Should be a pretty straightforward Rails app.
- Prototype and sample CTF challenges not written.  Waiting for Certain to be finished first.

That's all for now, thanks for reading!  The project is coming along nicely and I hope to have more updates for you soon.
