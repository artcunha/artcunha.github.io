---
layout: post
title:  "Spider-Man: Across the Spider-Verse"
date:   2023-05-06 15:39:40
preview: /assets/img/spider_thumbnail.png
category: [professional, techart]
---

<!-- ![Picture 1](/assets/img/across_spiderverse.jpg) -->
![Picture 1](/assets/img/AcrossTheSpiderVerse_1.gif)


# FX Reel
I worked for over 2 years on Spider-verse, from right before animation started, until shipping weeks before release. While most of that time was in Maya developing animation tools, I also got the chance to work in Houdini as part of the FX department. This involved shots with a mix of procedural and hand-drawn effects which you can check here. 
<div style="padding:56.25% 0 0 0;position:relative;"><iframe src="https://player.vimeo.com/video/844417966?title=0&byline=0&portrait=0&speed=0&badge=0&autopause=0&player_id=0&app_id=58479/embed" allow="autoplay; fullscreen; picture-in-picture" allowfullscreen frameborder="0" style="position:absolute;top:0;left:0;width:100%;height:100%;"></iframe>
</div>
 

# Tool Development

## Inklines Tool

<img src="/assets/img/spiderverse_inklines_01.jpg" alt="drawing" width="720" />

My longest assignment was to redesign and maintain one of the main animation tools of the project. This was done through extense collaboration with the Anim Leads, and although we signed on a new workflow early on, there was a lot of new features and polishing required as the team grew to 200+ users. \
Given the multiple types of lines and ways of drawing, the tool had to serve as a rig picker, a scene manager and a toolbar all in one. So it was important to create a flexible experience that would allow the artists to draw freely and only have more advanced options show when they need them.  

<!-- ### Data types -->

<blockquote class="twitter-tweet" data-lang="en"><p lang="en" dir="ltr">To ensure the anim team had an intuitive way to draw on their work no matter their preferred work flow, we built two ways to draw: <br><br>1: The spline-based Ink Line Tool. Upgraded from the first film. <br><br>2: A new pipeline to Blender for hand-drawn sketching.<a href="https://twitter.com/hashtag/AcrossTheSpiderVerse?src=hash&amp;ref_src=twsrc%5Etfw">#AcrossTheSpiderVerse</a> <a href="https://t.co/PatbdfOaKH">pic.twitter.com/PatbdfOaKH</a></p>&mdash; Nick Kondo 近藤 (@NickTyson) <a href="https://twitter.com/NickTyson/status/1667345951122669570?ref_src=twsrc%5Etfw">June 10, 2023</a></blockquote> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

The first movie lines were just a static nurbs bind to some clusters. We changed that to a new dynamic spline based approach that allowed us to add or remove controllers. Although I was able to repurpose the custom node from the The Sea Beast ropes, [there's a great post from Cole O'Brien breaking down how to do this with vanilla maya nodes](https://coleobrien.medium.com/matrix-splines-in-maya-ec17f3b3741). On top of this, I had to figure out some logic to dynamically recreate these while preserving the curvature and tangents with the minimum ammount of controls for any custom "baked" curve, whether that was drawn, from a model or imported from Blender.

We also pushed a lot for a better viewport drawing experience. As I was already familiar with making custom [Context Commands](https://github.com/artcunha/keychain/tree/main?tab=readme-ov-file#tracer), I wrote some projection options to get the points from screen space into different planes and normals based on the type of selection. There was as constant back and forth between artists who preffered the spline rig approach, the viewport drawing or just foregoing everything to frame by frame in Blender. We had to accomodate every option and constantly make sure those all related back to the same pipeline for the back-end.\ 

That standard in rendering was crucial since FX also had their own Linework team, [and the question of who does what is in fact something we often get asked.](https://beforesandafters.com/2023/06/17/the-across-the-spider-verse-spider-punk-character-hobie-was-animated-with-different-frame-rates-for-different-parts-of-his-own-body-and-accessories/#:~:text=b%26a%3A%20I%20wanted%20to%20also%20ask%20you%20about%20line%20work%2C%20which%20of%20course%20is%20something%20achieved%20in%20the%20first%20film%2C%20and%20in%20some%20other%20Imageworks%20projects%20as%20well.%20What%20were%20the%20challenges%20of%20solving%20line%20work%20on%20this%20film%20in%20an%2C%20I%20don%E2%80%99t%20want%20to%20say%20%E2%80%98automated%E2%80%99%20way%2C%20but%20to%20make%20it%20as%20automated%20as%20possible%3F)
But as the FX department got flooded by the final deadline, that pipeline allowed animators to take *some* of the load out of the smaller Houdini team.    

<!-- ### Modular Tooling -->

<!-- <img src="/assets/img/spiderverse_inklines_01.jpg" alt="drawing" width="720" /> -->
![Picture 2](/assets/img/spiderverse_inklines_03.jpg)
{:.image-caption}
*The lines weren't just for flashy smears, they could also be drawn or constrained directly on the surface for performance, and then be exported across different shots for continuity.*



## Clonestamps - Smear Tool
![Picture 2](/assets/img/spiderverse_clonestamp_05.jpg)

My first project on the show was to rethink our body smears (also known as "multiples") workflow. Some of the main goals were:
* Optimizing the idle time that took to load our assets.
* Re-writing the api to be more modular and scalable.
* Redesigning the UI and selection methods to keep artists in their flow, without disruption.

![Picture 2](/assets/img/spiderverse_clonestamp_06.jpg)

I pitched a new selection system that accommodated a variety of ways to automatically split the mesh. This system proved to be very flexible for artists, allowing them to use it in different ways without overcrowding the UI with options. Later, the tool had to account for things like variants, groom, and cfx meshes. The new API allowed us to implement various updates requested by downstream departments, which were seamless to the artists.


## RnD and Explorations
<!-- ![Picture 2](/assets/img/AcrossTheSpiderVerse_2.gif) -->
Due to the ever changing scope of the project, there was a lot of tech-art work that didn't make the cut. We were lucky to have a Pipeline Supervisor that would constantly ask us to chime in and pitch solutions, these were some of my favorites I got to mockup.  

###  Procedural Punk Cutout
![Picture 2](/assets/img/punk.gif)
 \
After the first animation tests, it was clear how much the cutout would play into Hobie's character. The idea was a decimated, inverse-hull cage wrapped to the rig and displaced by a noise plugged to his stepping. The script could also generate these cages for any other characters or props on the fly when needed for other characters or prop interaction. The end solution was way more elegant.

<blockquote class="twitter-tweet"><p lang="en" dir="ltr">Here&#39;s a (recreated) diagram of how the 2D elements are set up in one of my Maya scenes for my Hobie shots! Normally, you would do this in post with compositing software, but since we needed to have all the animation represented for approval in playblast, this is what we did... <a href="https://t.co/mSmhZQlkOV">pic.twitter.com/mSmhZQlkOV</a></p>&mdash; Li Wen Toh (@LiWenToh) <a href="https://twitter.com/LiWenToh/status/1666652467306860544?ref_src=twsrc%5Etfw">June 8, 2023</a></blockquote> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>


### Stylized Viewport Shader
Due to the variety of rendering styles on the movie and the complexity of our final look-of-picture pipeline, we also experimented with different ways of representing those looks inside the Maya viewport. It was important to visualize how lighting and shading could drive the performances. That meant that characters from different universes like Ben Reilly had their own independent light logic. To achieve this, I helped the team by mocking up a custom viewport shader that could also be used for characters like Peni or Hobie. 

<blockquote class="twitter-tweet" data-lang="en"><p lang="en" dir="ltr">Ben Reilly. Direct homage to the inking style of Tom Lyle and Steve Butler. Really had fun drawing in this style and all those muscles. Those drawings were the base for the CG team to nail to render look. 3D model by <a href="https://twitter.com/winanimata?ref_src=twsrc%5Etfw">@winanimata</a> <a href="https://twitter.com/hashtag/AcrossTheSpiderVerse?src=hash&amp;ref_src=twsrc%5Etfw">#AcrossTheSpiderVerse</a> <a href="https://t.co/eUu2sskHuz">pic.twitter.com/eUu2sskHuz</a></p>&mdash; Aymeric Kevin (@AYMRC) <a href="https://twitter.com/AYMRC/status/1672688219295555585?ref_src=twsrc%5Etfw">June 24, 2023</a></blockquote> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

This great target from Aymeric explained the overall logic, which ends up being very similar to a Phong shader with some clamping and remapping on the dot-product. It was also heavily inspired on [TF2's classic shader](https://steamcdn-a.akamaihd.net/apps/valve/2007/NPAR07_IllustrativeRenderingInTeamFortress2.pdf). 
The final shader consisted of a diffuse, specular and a fresnel/rim component with color outputs.

After the proof of concept, this - along with other Ben Reilly specific setups - was made into its own tool by Alan Zheng.

###  Functional Portals 
We tried a miriad of approaches during production from custom deformers to Houdini Engine and OpenGL Shaders. Early on I tried Bifrost on a two sided portal setup that would flatten the geometry and copy the mesh to the other side with a "travel time" offset exposed. This wasn't developed further as the logic of portals changed a lot and anim would often need to mockup a lot of things in the hackiest, fastest way possible. That in itself is a great summary of the inherit challenge of developing tech and standardadizing  workflows for a project like this, sometimes we really do need to step back and just let artists do their own thing.

![Picture 2](/assets/img/spiderverse_portals.jpg)

