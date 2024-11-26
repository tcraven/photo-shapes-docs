---
layout: page
title: Motivation
parent: More Information
nav_order: 1
permalink: /more-info/motivation/
---

# Motivation

During my career break in 2024, I wanted to focus on my personal projects. I love model
railways, and decided to build a layout in my basement. I want to recreate
a real-life railway station location as accurately as possible in model form, but the
only information I have is a collection of old photographs. I want to create models of
the station buildings with correct dimensions and proportions.

Focusing on the buildings, the problem I want to solve is:
            
>   Given a set of photographs of a
>   building taken for various viewpoints, accurately derive the shape and dimensions of
>   the building, and create a 3D model

I searched for existing software tools with the capability to model shapes from
photographs, but I wasn't able to find anything that matched my requirements. I
decided to go ahead and create the tools myself.

{%
    include image.html
    src="/assets/images/more-info/stokesley-photo-model-1.jpg"
    caption="
        <b>Left:</b> A photograph of Stokesley Station near Middlesbrough, UK, taken in 1954.
        <b>Right:</b> My laser cut card model of the station building in OO scale (1:76.2).
        I used Photo Shapes to determine accurate building dimensions from photographs.
    "
%}

## Existing Tools

Before embarking on my Photo Shapes project, I considered the using the following software tools.

### SketchUp Match Photo

Back in the early 2000s I used a 3D design software called [SketchUp](https://www.sketchup.com/en){:target="_blank"}.
It still exists today, and is a great
application for 3D modeling. It has a unique feature called Match Photo, that allows the
user to create 3D models by tracing lines over photographs.

Here are two YouTube videos that demonstrate the process:

1. [Creating Models from Multiple Photos in Match Photo in SketchUp](https://www.youtube.com/watch?v=ogGlGiu5VBM){:target="_blank"}
1. [SketchUp Training Series: Match Photo Part 2](https://www.youtube.com/watch?v=gX4C9To9Oiw){:target="_blank"}

{%
    include image.html
    src="/assets/images/more-info/sketchup-screenshots.jpg"
    caption="
        SketchUp user interface, taken from the second video above.
        <b>Left:</b> Lining up axis lines to determine the orientation and field of view
        of the camera.
        <b>Right:</b> Tracing out the shape of the building along the x, y and z axes
        to create the 3D model.
    "
%}

I attempted to use SketchUp Match Photo myself, and found that it had several limitations:

1.  For each photograph, the user must manually line up axis lines to determine the
    orientation and field of view of the perspective camera. The camera view is very
    sensitive to small changes in the positions of the axis lines, and it is difficult
    to line everything up perfectly.
1.  As the user adds more photographs, it becomes increasingly difficult to line up new
    photographs with the existing 3D model that was drawn from the first photograph. This
    is because variations in building dimensions that are not noticeable from a particular
    viewpoint in one photograph can be significant from a different viewpoint in another
    photograph.
1.  In order to get an accurate model, the user has to swap back and forth between multiple
    photographs, making small adjustments to sizes and shapes of the 3D model and also
    adjusting the camera perspectives to try to get everything to line up.
1.  If you watch the videos, you can hear the presenters acknowledging some of these
    problems as they demonstrate the functionality. In the first video, the presenter
    actually gives up when he finds that the model doesn't match the second photo properly!


### Photogrammetry, NeRFs, and Gaussian Splats

This [article](https://www.spatial.capital/blog-posts/scene-representation){:target="_blank"}
gives a good overview of these 3D reconstruction technologies.

Unfortunately, they are not suitable for my use case for the following reasons:

1.  Many images are required to produce accurate 3D models. These techniques require
    a minimum of hundreds of images taken from many different angles to achieve a
    good level of accuracy. For my model railway buildings, I have between
    one and twenty photographs to work with per building.
1.  The generated models tend to have a wobbly appearance, rather than flat surfaces.
    For my application - buildings with relatively simple geometric shapes - this is
    not ideal. I would likely have to process the model after it is generated to
    clean it up in order for it to be useful as a guide for a physical model.


## Conclusion

Having considered the options, I felt I needed a technique that fell somewhere in the middle
ground between the fully manual SketchUp approach, and the fully automated but data-hungry
photogrammetry approach. I wanted an application that worked in a similar way to SketchUp,
but automated the difficult and tedious positioning of the cameras and adjustment
of the model dimensions.

I came up with the following idea: If I draw lines on photographs along the edges of walls,
roofs, windows, doors, chimneys, can I use optimization to derive the position, orientation,
and field of view of the camera? Furthermore, given several photos, can I derive the
optimal dimensions of a building such that the dimensions cause each photo view to match up
as closely as possible with the 3D model?

The answer, it turns out, is yes, and this is how Photo Shapes works.
