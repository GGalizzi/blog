---
layout: post
title: "Procedural world generation for a roguelike."
date: 2015-09-17 16:00:00
categories: rust roguelike gamedev
---

I've been working on my roguelike again, and I now I'm working on the world generation process.

I want this game to have a sizable amount of land, and hopefully make it interesting along the way.

I don't have that much experience with procedural generation, only some dungeon gen here and there, I also made a toy galaxy generator which I'm somewhat proud of.

The process started, like most, with some googling around, how did others generate overworld maps? I found inspiration in this [Ultima Ratio Regum's blog post](http://www.ultimaratioregum.co.uk/game/2012/05/07/map-generation-redux/). Next up is trying to make sense of how the process would start, an important part in game development I have come to always think about is to split your current goal into the smallest chunks you can possibly imagine.

And the smallest chunk I could possibly imagine was placing a single tile of grass somewhere around the middle of the (previously filled with ocean tiles) world. Next up? Well how about making that piece of land a bit chunkier? Draw a rectangle of tiles around. And like that until I started iterating land around like:

1. Pick a point roughly around the center of the world.

2. Draw an oval-like shape around that point.

3. Repeat 1-2 a few times.

4. Pick a random point anywhere in the world, and draw an oval-like shape around that point.

5. Pick more random numbers near the edges of the oval-like shapes.

6. Draw more ovals.

And like that you start getting some shapes that resemble continents, and some islands here and there.

But then I started testing it with bigger world sizes, and things got weird, the calculations start making less sense as the size gets bigger, so I started using these smaller "chunks" to generate continents, and the whole world landmass.

I'm still playing around with the values, but I can keep doing that later.

