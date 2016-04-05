---
layout: post
title: Hack Doom Update - Certain Input
author: Foxx
tags:
 - games
 - development
 - hacking
---
__LOTS__ of progress on [Hack Doom](https://github.com/frozenfoxx/hack-doom) this month.  The big news is that finally after lots of hard work the *Gloom* webserver is getting worked on and almost ready to be off the ground.  It currently doesn't resemble the intended interface but backend work is proceeding well and the major components are getting completed.

Naturally first there's some big changes.  For one thing while we're still using websockets we'll no longer be using *websocketd*.  However this isn't a bad thing, this is actually a good thing as I've got a much tighter way to hook *Certain* up to *Gloom*.  This also means that there's on less dependency, so hooray for that.  What is this better way?  Using our next new addition, *Rails 5*!  Yes, it's still in beta which has not made development easy due to lack of tutorials or very helpful information on application writing with it.  However it also has a critical component needed for *Hack Doom*:  ActionCable.  ActionCable is Rails' new built-in method for handling websockets and generally it's pretty awesome, if a little confusing.

So how is *Certain* being bootstrapped?  With Rails 5 and ActionCable there's these things called *Channels.*  Channels are very similar to Controllers but are expected to be very long-lived and most importantly can send and receive data from websocket streams.  I couldn't make websocketd and ActionCable play nice so I created a new Channel that bootstraps up *Certain* and voila, all good to go.  No separate launcher, no hooking together web technologies that may not play nice with each other, just straight-up simply wrapping it up within the Rails app.

How's it work?  Well, that's been difficult but now that I'm getting somewhere the answer is:  great!  Currently you can from the *Gloom Chat* endpoint actually send messages that are received and interpreted by *Certain*.  I DID have the messages emitted back into the *Gloom Chat* endpoint but unfortunately that caused a runaway spam condition since the new input would trigger a send which would trigger and input and so forth.  At the moment it just dumps the output to the console, but this will be reworked for various endpoints.

What this means is that *Gloom* is __very__ successfully wrapping up *Certain*, can communicate with it in full, all handled by standard Rails 5 components.  This is fantastic progress and means we're within sight of the first, full prototype server.  As always pull requests are appreciated, but I wanted to give a special thanks to CyberNigma, Sarif, and hdm for helping me diagnose some issues and get me thinking in a new direction!

Overall progress report:

- Two example challenges are now up and cover both downloadable types and basic web page types.
- hackdoom.pk3 Assets file for Doom compiled with source available under *assets/*.
- hackdoom001 prototype level almost complete.  Needs a nice little stimpack in the first secret area and needs the name set, but is otherwise complete with properties YAML to boot.
- Certain wrapper is done!
- Move to Zandronum completed, only thing that hurts is that when running *pukename* it complains to players that the server might be cheating.  Looking into ways to resolve this.
- Gloom has been started.  AJAX requirement is going to be a bit of a pain, but plenty of work can now proceed.  Successfully launches and communicates with Certain, the most critcial and difficult part.
- More sample CTF challenges need to be written.
