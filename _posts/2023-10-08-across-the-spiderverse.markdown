---
layout: post
title:  "Spider-Man: Across the Spider-Verse"
date:   2023-05-06 15:39:40
preview: /assets/img/spider_thumbnail.png
category: [professional, techart]
---

<!-- ![Picture 1](/assets/img/across_spiderverse.jpg) -->
![Picture 1](/assets/img/AcrossTheSpiderVerse_1.gif)

# Tool Development

## Inklines Tool

I got the chance to design and write one of the main animation tools for this ambitious sequel. The goal was to be flexible, yet intuitive. It accommodated various types of line and shape geometries that were used for smears and facial accents.

<blockquote class="twitter-tweet" data-lang="en"><p lang="en" dir="ltr">To ensure the anim team had an intuitive way to draw on their work no matter their preferred work flow, we built two ways to draw: <br><br>1: The spline-based Ink Line Tool. Upgraded from the first film. <br><br>2: A new pipeline to Blender for hand-drawn sketching.<a href="https://twitter.com/hashtag/AcrossTheSpiderVerse?src=hash&amp;ref_src=twsrc%5Etfw">#AcrossTheSpiderVerse</a> <a href="https://t.co/PatbdfOaKH">pic.twitter.com/PatbdfOaKH</a></p>&mdash; Nick Kondo 近藤 (@NickTyson) <a href="https://twitter.com/NickTyson/status/1667345951122669570?ref_src=twsrc%5Etfw">June 10, 2023</a></blockquote> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>


## Clonestamps - Smear Tool
<p float="center">
<img src="/assets/img/spiderverse_clonestamp_01.png" alt="drawing"  width="360" />
<img src="/assets/img/spiderverse_clonestamp_04.png" alt="drawing"  width="360" />
</p>
My first assignment on the show was to rethink our body smears (also known as "multiples") workflow. Some of the main goals were:
* Optimizing the idle time that took to load our assets.
* Re-writing the api to be more modular and scalable.
* Redesigning the UI and selection methods to keep artists in their flow, without disruption.

<p float="left">
<img src="/assets/img/spiderverse_clonestamp_02.png" alt="drawing" width="360" />
<img src="/assets/img/spiderverse_clonestamp_03.png" alt="drawing" width="360" />
</p>

I pitched a new selection system that accommodated a variety of ways to automatically split the mesh. This system proved to be very flexible for artists, allowing them to use it in different ways without overcrowding the UI with options. Later, the tool had to account for things like variants, groom, and cfx meshes. The new API allowed us to implement various updates requested by downstream departments, which were seamless to the artists.


## Ben Reilly Real-Time Shader
<img src="/assets/img/ben_reilly.webp" alt="drawing" width="720" />

Due to the variety of rendering styles on the movie and the complexity of our final look-of-picture pipeline, we also experimented with different ways of representing those looks inside the Maya viewport. It was important for both the animators and the clients to be able to visualize how lighting and shading could influence the performances. That meant that characters like Ben Reilly needed their own independent light rig. To achieve this, I helped the team by mocking up a custom viewport shader that could potentially be re-used for characters like Peni or Hobie. 

<blockquote class="twitter-tweet" data-lang="en"><p lang="en" dir="ltr">Ben Reilly. Direct homage to the inking style of Tom Lyle and Steve Butler. Really had fun drawing in this style and all those muscles. Those drawings were the base for the CG team to nail to render look. 3D model by <a href="https://twitter.com/winanimata?ref_src=twsrc%5Etfw">@winanimata</a> <a href="https://twitter.com/hashtag/AcrossTheSpiderVerse?src=hash&amp;ref_src=twsrc%5Etfw">#AcrossTheSpiderVerse</a> <a href="https://t.co/eUu2sskHuz">pic.twitter.com/eUu2sskHuz</a></p>&mdash; Aymeric Kevin (@AYMRC) <a href="https://twitter.com/AYMRC/status/1672688219295555585?ref_src=twsrc%5Etfw">June 24, 2023</a></blockquote> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

I spent some time studying this amazing target from Aymeric, as well as this great [paper from Valve on TF2's shaders](https://steamcdn-a.akamaihd.net/apps/valve/2007/NPAR07_IllustrativeRenderingInTeamFortress2.pdf). The final shader basically consisted of a diffuse, specular and a fresnel/rim component.

After this proof of concept, the shader - along with other Ben Reilly specific workflows - was made into its own tool by the awesome Alan Zheng.

# FX Shots
Towards the end of the show, I also got to work in Houdini as part of the FX department. I was super grateful for this oppurtunity to do more hands-on shot work! 
<div style="padding:56.25% 0 0 0;position:relative;"><iframe src="https://player.vimeo.com/video/844417966?title=0&byline=0&portrait=0&speed=0&badge=0&autopause=0&player_id=0&app_id=58479/embed" allow="autoplay; fullscreen; picture-in-picture" allowfullscreen frameborder="0" style="position:absolute;top:0;left:0;width:100%;height:100%;"></iframe></div>

<!-- ![Picture 2](/assets/img/AcrossTheSpiderVerse_2.gif) -->