---
layout: module
permalink: ModuleX_LocalIllumination/Video2
title: "CS 476: Computer Graphics - Module 10 Part 2"
excerpt: "CS 476: Computer Graphics - Module 10 Part 2"

info:
  next: "./Exercise2"
  prev: "./Exercise1"
  
---

Please watch the video below, and click the next button once you have finished.

<iframe width="560" height="315" src="https://www.youtube.com/embed/GNqWEcjLMRY" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

<h1>Notes</h1>
<img src = "../images/Unit2/Phong.svg">

<h1>The reflect() function in GLSL</h1>
<p>
One thing I didn't mention in the video is that there's a built-in function in GLSL called <a href = "https://www.khronos.org/registry/OpenGL-Refpages/gl4/html/reflect.xhtml">reflect()</a> to do reflections.  But we have to be careful when using it for specular, because it actually gives the wrong reflection.  The image below shows how:
</p>

<img src = "../images/Unit2/reflectfn.svg">