---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: home
title: Overview
nav_order: 1
permalink: /
---

# Software For Modeling Buildings From Photographs

Photo Shapes is an application that produces accurate 3D models of
buildings from photographs.
{: .fs-6 .fw-300 }

{%
    include image.html
    src="/assets/images/overview/ps-camera-1-4.jpg"
    caption=""
%}

<iframe
    style="width:100%;height:auto;aspect-ratio:16 / 9;"
    width="560"
    height="315"
    src="https://www.youtube.com/embed/8LaIFjQw2qU?si=pzUYc1kYk86Wnsdg"
    title="YouTube video player"
    frameborder="0"
    allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
    referrerpolicy="strict-origin-when-cross-origin"
    allowfullscreen
>
</iframe>



# Key Features

**Photo-Based Modeling:**
Users upload photographs of a building taken from different viewpoints, and draw lines
along the edges of walls, roofs, windows on each photo.

**Parametric 3D Modeling:**
Users build up 3D models from a set of primitive shapes, and define the positions,
dimensions and shapes of components using mathematical expressions.

**Optimization Engine:** Photo Shapes automatically adjusts
camera position and model parameters to ensure the best possible fit between the model
and photographs, achieving highly accurate results.

**Texture Mapping:** Textures are projected from photographs onto the 3D model, and
Photo Shapes automatically chooses the best photo texture for each part of each shape.

**3D Model Export:** Models and textures can be exported in the widely supported
GLTF format, and imported into other 3D software, such as Blender.


## About This Site

Photo Shapes is a personal project developed by Tom Craven. I haven't yet
released Photo Shapes or its source code, although I do hope to do so in the
future! This website is intended to demonstrate the features of the software to
interested readers.

<!-- 
This is the base Jekyll theme. You can find out more info about customizing your Jekyll theme, as well as basic Jekyll usage documentation at [jekyllrb.com](https://jekyllrb.com/)

You can find the source code for Minima at GitHub:
[jekyll][jekyll-organization] /
[minima](https://github.com/jekyll/minima)

You can find the source code for Jekyll at GitHub:
[jekyll][jekyll-organization] /
[jekyll](https://github.com/jekyll/jekyll)


[jekyll-organization]: https://github.com/jekyll -->

