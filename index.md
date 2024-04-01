---
title: Home
layout: home
---

## Summary
Taking inspiration from Minecraft world generation, this project will procedurally generate an infinite world with
complex terrains and cities. Additionally, there will be an interactive component to it where the user can move around 
the world using the WASD keys and space bar.      
     
## Problem Description
We’re making procedural generation for cities in Unity, starting from terrain creation algorithms to the texture mapping.
        We were inspired by Minecraft and want to extend the concept of an infinite world to a city. This is a difficult problem 
         because a city has more factors to consider than Minecraft, such as water sources, road placement, urban planning 
         (ex. where to place businesses vs. homes vs. schools), etc. A key question for us is how to recreate fine-grained details
          like fire hydrants. If we’re able to solve this problem, we’ll be able to offer urban planners a quick tool to imagine 
          cities come to life.
     
## Goals and Deliverables
### Demo
 In Unity, we can have a first person camera and WASD control to move through the terrain. This will allow us to see the world 
        being generated as we move in a direction. Latency should be unnoticable for moving slowly in the world.
    
    
### Measuring Quality and Performance
  Ideally, we want to be able to smoothly transition into the newly generated terrain when moving the camera around. We can measure 
        the fps (~30-60) as new terrain is generated. It will probably slow down when generating large chunks of terrain, but ideally, the 
        simulation should run smoothly when there isn’t much generation being done. 
      
### Analysis Questions
- How realistic, random, and/or believable is the generation?
- How is the performance of the generation?
  
### What we plan to deliver
There are a few key components of our project. First, we have our procedural generation algorithm. The simplest component we will 
        implement is the terrain generator. This will work by generating a heightmap using various octaves of noise (using something like the 
        perlin or simplex algorithms). Next, we will create an algorithm (inspired by the paper linked below) which selects locations for houses, 
        paths/roads, and other city elements. A basic version of this could involve “randomly” distributing houses around the city and linking them together.
      
  The second component is our meshing algorithm, which will transform the abstract representation of our procedural generator (the heightmap and 
        locations of houses, paths, etc) into a real mesh which we can render and move around in. For example, to generate the terrain, we will sample 
        from the heightmap at uniform locations along a grid, and assign the corresponding positions to vertices of the terrain mesh. We can also apply 
        uv coordinates to map textures based on the type of terrain (dirt, stone, etc). To do the meshing, we are considering two approaches:
     
  - The first approach would be to do a minecraft-like system where the entire world is based on a cube grid.
  - The second approach would be to instead generate “smooth” meshes and use pre-made mesh assets for things like houses.
    Depending on which choice we make, we might need to implement certain optimizations (such as optimizing which faces we actually generate in the
        cube-system)
    
### What we hope to deliver
  - We would like to elevate the generation with shaders, foliage, etc. This could entail adding weather like rain or fog in our world or more complex details like grass swaying or puddles in the streets.
- We would also like to make our city generation more interesting and complex. This could include more interesting decisions about where to place houses to emulate various factors and make more realistic/interesting cities!
 - Seamless infinite generation, where we can just wander around and more terrain and cities will appear.
   
### Schedule
- Week 1: Setup Unity infrastructure and complete terrain generation algorithm
- Week 2: Complete Mesh generation and optimization, and basic city generation
- Week 3: Advanced city generation, textures, begin working on aspirational goals
- Week 4: Implement additional optimizations if needed and additional aspirational goals as time allows
      
## Resources
- [Procedural generation of semantically plausible small-scale towns](https://www.sciencedirect.com/science/article/pii/S1524070323000012)
- [Procedural Generation Outline Video](https://www.youtube.com/watch?v=XpG3YqUkCTY&ab_channel=Lejynn)
- [Unity Manual](https://docs.unity3d.com/Manual/index.html)
    

----


[Just the Docs]: https://just-the-docs.github.io/just-the-docs/
[GitHub Pages]: https://docs.github.com/en/pages
[README]: https://github.com/just-the-docs/just-the-docs-template/blob/main/README.md
[Jekyll]: https://jekyllrb.com
[GitHub Pages / Actions workflow]: https://github.blog/changelog/2022-07-27-github-pages-custom-github-actions-workflows-beta/
[use this template]: https://github.com/just-the-docs/just-the-docs-template/generate
