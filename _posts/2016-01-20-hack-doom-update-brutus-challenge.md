---
layout: post
title: Hack Doom Update - Brutus Challenge
author: Foxx
tags:
 - games
 - development
 - hacking
---
Small update on [Hack Doom](https://github.com/frozenfoxx/hack-doom), there's a new example challenge, "[brutus](https://github.com/frozenfoxx/hack-doom/tree/master/challenges/brutus)." It's another simple one but it showcases a different way to do challenges, in this case with a direct web page.  Since the content of the challenge is the ciphertext itself a simple _index.html_ in the _content_ directory is sufficient.  The _Gloom_ webserver will simply pick it up and display the directory contents, which in this case will simply showcase the page.  There's a LOT of challenges that can be done this way, usually trivia or things that require looking something up outside of the gameserver so hopefully this helps get some of those submissions going!

Overall progress report:

- Two example challenges are now up and cover both downloadable types and basic web page types.
- hackdoom.pk3 Assets file for Doom compiled with source available under assets/
- hackdoom001 prototype level almost complete.  Needs a nice little stimpack in the first secret area and needs the name set, but is otherwise complete with properties YAML to boot
- Certain wrapper is almost done.  Allows you to launch with a map set, registers valid commands on STDIN and translates them to Doom, and now can launch a websocket.
- Move to Zandronum completed, only thing that hurts is that when running *pukename* it complains to players that the server might be cheating.  Looking into ways to resolve this.
- Gloom hasn't been started yet.  AJAX requirement is going to stall progress until I find a web dev to help build it.
- Prototype and more sample CTF challenges not written.  Waiting for Certain to be finished first.
