---
layout: post
title: "The \"45 Minutes LÖVE Tutorial\" Extended"
categories: tutorial
tags: love tutorial
---

## Intro

For the tutorial, look <a href="https://love2d.org/forums/viewtopic.php?f=5&t=8447">here</a> or <a href="http://cupm.net/public/love2dtutorial/">here</a>.

I'm extending the tutorial by providing some additional code. It felt unnatural and limited only being able to move at the bottom of the screen. I wanted to extend the functionality of the ship so you can move around the entire map.

## Just add

```
if love.keyboard.isDown("up") then
game.playery = game.playery - 100*dt*3
end
```

```
if love.keyboard.isDown("down") then
game.playery = gameplayery + 100*dt*3
end
```

## Final note

Scale is equal to 4 and the default value set by the tutorial. For my game I used 3. You can assign it to whatever you want (well, almost, depends).

Another thing, if you want to increase the difficulty, have the user put in a number then have that number equal to game.enemy_rate. Anything more than 2 but less than 15 is good. You could fill the screen but that's completely pointless.

Where you put these code, of course depends on how you structured your code. If you followed the tutorial, it should be obvious where they go.

I can't think of anything else to add to the game except more level, more enemies, etc. That also shouldn't be hard to do on your own.
