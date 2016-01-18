---
layout: post
title: Hack Doom Update - Challenge Example
author: Foxx
tags:
 - games
 - development
 - hacking
---
Fresh update on [Hack Doom](https://github.com/frozenfoxx/hack-doom), there's now an example challenge in the repo and a new _challenges_ directory!  You can see it now at [challenges/enhance](https://github.com/frozenfoxx/hack-doom/tree/master/challenges/enhance).  It's a simple one but it gets the idea rolling.  In this case this is a quick downloadable challenge.  The _content_ directory will be hosted directly so players will open the challenge in a new tab and click to download the file.  The _info.yaml_ is read by the _Gloom_ server to fill out the various challenge information including the name, suggested difficulty, and most importantly the flag among other things.  I'm working on a good example for a web challenge but this will cover quite a few types of challenges.

Have one to submit?  Great!  Issue a pull request and I'll get it added!  _Hack Doom_ will work best when there's a nice, large pool of example challenges for people to play with and figure out how to design their own!  On a side note a workaround's been found for the _Zandronum_ server complaining about the "cheating." It's just a single line in the code, so I don't think it'd be too bad to make a patch file and build from source.  Monitoring for ACTUAL cheating will be a different matter but I don't think that's important for version 1 since frankly getting it off the ground at all is kind of the goal at this point.

On the slightly more important news, it's been decided that unfortunatly the _Gloom_ web server page, which not super-complicated, is going to need to be done with AJAX.  I know, I'm not a fan of it either, but due to using websockets it's necessary.  The reason?  You need to be able to alter the page contents from a continuous model update __without__ doing a page refresh.  If you do a page refresh, it restarts the websocket and blows up the server.  The alternative is to have a server that connects to the websocket server and that's just even more awful.  Unfortunately this means it's pretty far beyond my design abilities as I'm really not a web dev and unfamiliar with doing this.  As I've talked to a few it sounds pretty doable and not very difficult but is definitely not something I can do on my own.  SO!  Wanna help?  GREAT!  Let me know and we can get something designed and up!

It's not all bad though.  _Certain_ now has a websocket option!  And it launches _websocketd_!  And...well, seems to work!  Frankly that's pretty awesome and a BIG part done.  Now I just need to clean up the output and find a good way to test input over the websocket.  It's not in the repo but I've got a quick-n-diry websocket test page that tests output and frankly it works wonderfully.

Overall progress report:

- One example challenge is now up and covers downloadable types in terms of format.
- hackdoom.pk3 Assets file for Doom compiled with source available under assets/
- hackdoom001 prototype level almost complete.  Needs a nice little stimpack in the first secret area and needs the name set, but is otherwise complete with properties YAML to boot
- Certain wrapper is almost done.  Allows you to launch with a map set, registers valid commands on STDIN and translates them to Doom, and now can launch a websocket.
- Move to Zandronum completed, only thing that hurts is that when running *pukename* it complains to players that the server might be cheating.  Looking into ways to resolve this.
- Gloom hasn't been started yet.  AJAX requirement is going to stall progress until I find a web dev to help build it.
- Prototype and more sample CTF challenges not written.  Waiting for Certain to be finished first.
