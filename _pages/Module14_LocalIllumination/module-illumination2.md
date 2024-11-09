---
layout: module
permalink: Module14_LocalIllumination/Video2
title: "CS 476: Computer Graphics - Module 14 Part 2"
excerpt: "CS 476: Computer Graphics - Module 14 Part 2"

info:
  next: "./Exercise2"
  prev: "./Exercise1"
  
---

Please watch the video below, and click the next button once you have finished.

<iframe width="560" height="315" src="https://www.youtube.com/embed/GNqWEcjLMRY" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

<h1>Notes</h1>
<img src = "../images/Unit4/Phong.svg">

<h1>The reflect() function in GLSL</h1>
<p>
Below is a video I made that derive what the <code><a href = "https://www.khronos.org/registry/OpenGL-Refpages/gl4/html/reflect.xhtml">reflect()</a></code> method in glsl does
</p>

<iframe width="560" height="315" src="https://www.youtube.com/embed/-4U8oLgrE9U?si=9tZS8kR73Dnb77HR" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

<p>
But we have to be careful when using this exact method for the specular reflection, because it actually gives the negative direction of what we want.  This is because both of the vectors we construct are heading away from point of intersection, as shown in the image below:
</p>

<img src = "../images/Unit4/reflectfn.svg">