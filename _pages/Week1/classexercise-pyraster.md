---
layout: exercise
permalink: "Week1/PyRaster"
title: "CS 477 Week 1: Rasterization Exercise"
excerpt: "CS 477 Week 1: Rasterization Exercise"
language: "pyodide"

info:
  comments: "true"
  instructions: "<p></p>"
  packages: "numpy,matplotlib"
  goals:
    - To implement rasterization algorithms for simple geometric shapes by directly manipulating pixels
    
processor:  
  correctfeedback: "Correct!!" 
  incorrectfeedback: "Picture rendered!"
  submitformlink: false
  feedbackprocess: | 
    let imageRef = "";
    let zeroRef = "";
  correctcheck: |
    pyodide.globals.get("img_str") == imageRef

files:
  - filename: "student.py"
    name: driver
    ismain: false
    isreadonly: false
    isvisible: true
    code: | 
          import matplotlib.pyplot as plt
          import numpy as np

          def draw_rect(img, x, y, w, h, color):
              """
              Draw a solid rectangle of a particular color

              Parameters
              ----------
              img: ndarray(height, width, 3)
                  Image to which to draw the rectangle
              x: int
                  x coordinate of the upper left of the rectangle
              y: int
                  y coordinate of the upper left of the rectangle
              w: int
                  Width of the rectangle
              h: int
                  Height of the rectangle
              color: list of [int, int, int]
                  Color to draw
              """
              img_height = img.shape[0]
              img_width  = img.shape[1]
              color = np.array(color, dtype=np.uint8)
              ## TODO: Fill this in
              

          def draw_circle(img, cx, cy, r, color):
              """
              Draw a solid disc of a particular color

              Parameters
              ----------
              img: ndarray(height, width, 3)
                  Image to which to draw the rectangle
              cx: float
                  x coordinate of the center of the disc
              cy: float
                  y coordinate of the center of the disc
              r: float
                  Radius of disc
              color: list of [int, int, int]
                  Color to draw
              """
              ## TODO: Fill this in
              pass

          
          width = 400
          height = 400
          I = np.zeros((height, width, 3), dtype=np.uint8)
          ## Draw a little face (you can make this anything you want!)
          draw_rect(I, 100, 100, 200, 200, [255, 255, 0])
          draw_rect(I, 140, 150, 40, 40, [0, 0, 255])
          draw_rect(I, 220, 150, 40, 40, [0, 0, 255])
          draw_rect(I, 150, 250, 100, 20, [255, 0, 0])

          



  - filename: "main.py"
    ismain: true
    name: main
    isreadonly: true
    isvisible: true
    code: |
        plt.figure(figsize=(6, 6), dpi=100)
        plt.imshow(I, interpolation='none')
        plt.axis("off")
        save_figure_js()
        
openFilesOnLoad: ["main.py", "student.py"]
---
