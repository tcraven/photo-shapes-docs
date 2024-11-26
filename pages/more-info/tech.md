---
layout: page
title: Technical Details
parent: More Information
nav_order: 2
permalink: /more-info/tech/
---

# Technical Details

This page describes the languages and libraries that Photo Shapes uses.

Photo Shapes is a web application written in [TypeScript](https://www.typescriptlang.org/){:target="_blank"}
and [React](https://react.dev/){:target="_blank"}.
It has a small web server component written in [Python](https://www.python.org/){:target="_blank"}
and [Flask](https://flask.palletsprojects.com/en/stable/){:target="_blank"}
that mostly handles serving images and importing and exporting Photo Shapes save files.

## Web Application

**State Management:** I use [React Context](https://react.dev/learn/scaling-up-with-reducer-and-context){:target="_blank"}
combined with [Immer](https://immerjs.github.io/immer/){:target="_blank"}
for managing the state and data in the app. As the app has grown I have learned some of the
[performance implications](https://www.reddit.com/r/reactjs/comments/z4y7sj/redux_vs_context_what_exactly_does_redux/){:target="_blank"}
of using React Context, but so far I have been able to maintain a smooth user interface by
judicious use of `memo` and `useCallback` in my components.

**3D Graphics:** I use [Three.js](https://threejs.org/){:target="_blank"}
via [React Three Fiber](https://r3f.docs.pmnd.rs/getting-started/introduction){:target="_blank"}
to render all 3D graphics in the app. Three.js also provides the export to GLTF functionality.
I also use the [React Three Drei](https://github.com/pmndrs/drei){:target="_blank"}
library to draw edge lines.

**3D Camera Projection:** The optimization functionality uses Three.js to calculate the
perspective projection and map points in 3D space to points in 2D camera projection
space. This part of the code uses Three.js objects directly without rendering anything to
a canvas.

**Optimization:** I use a modified version of the Conjugate Gradient algorithm provided by the
[fmin](https://github.com/benfred/fmin){:target="_blank"}
library for optimizing both cameras and shapes. The optimization code runs in a
[web worker](https://developer.mozilla.org/en-US/docs/Web/API/Web_Workers_API/Using_web_workers){:target="_blank"},
which prevents the UI from freezing.

**Expressions:** Expression parsing and evaluation is handled by the [MathJS](https://mathjs.org/){:target="_blank"}
library.

**Lens Correction:** I use the [glslCanvas](https://github.com/patriciogonzalezvivo/glslCanvas){:target="_blank"}
library together with a custom shader to apply lens correction to photographs on a canvas.

**User Interface:** I created the majority of the user interface components and styling myself.
I used [MUI Material UI](https://mui.com/material-ui/getting-started/){:target="_blank"}
for dropdowns, sliders, and several other components. The icons are taken from
[React Icons](https://react-icons.github.io/react-icons/){:target="_blank"}.

## Web Server

Python and Flask is used to create a REST API that is used by the web application for images
and project data.


## Source Code

For now, I have decided to keep the Photo Shapes source code private. It isn't quite ready
for people to use, and hasn't been user tested. I do hope to release it in the future when
it is ready.
