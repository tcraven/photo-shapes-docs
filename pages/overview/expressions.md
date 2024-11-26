---
layout: page
title: Expressions
parent: Overview
nav_order: 5
permalink: /overview/expressions/
---

# Expressions

Photo Shapes has an expression system that allows the user to specify shape position,
rotation and parameters using mathematical formulas. This system is powerful because
it means that the relationships between shapes are defined mathematically, which
allows Photo Shapes to directly perform numerical optimization to achieve the
best possible fit between shapes and photographs.

User-defined expressions live on Shape Group objects in the shape tree. Child shapes
can refer to expression symbols from their parent shapes and ancestors, resulting in
a convenient scoping system that allows both shapes and expressions to be organized
logically.

{%
    include image.html
    src="/assets/images/overview/ps-opt-shapes-4.jpg"
    caption=""
%}
