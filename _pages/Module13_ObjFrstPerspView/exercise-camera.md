---
layout: exercise_javascript_viewing
permalink: "Module13/ClassExercise"
title: "CS 476: Computer Graphics - Camera Viewing Exercise"
excerpt: "CS 476: Computer Graphics - Camera Viewing Exercise"

info:
  instructions: "Fill in the matrix that moves the world according to where a camera is looking."
  goals:
    - Explore parts of the object-first pipeline in code
    - Implement camera viewing matrices using homogenous coordinates

processor:  
  correctfeedback: "Correct!!" 
  incorrectfeedback: "Try again"
  submitformlink: false
  feedbackprocess: | 
    let correctStr = "";

  correctcheck: correctStr
  incorrectchecks:
    - incorrectcheck: noTanStr
      feedback: "Try again.  It looks like you're not scaling down the x and the y components by the tangent of the fields of view over 2"

jseditor:
  isreadonly: false
  code: |
        scene.camera.getMVMatrix = function() {
            let right = this.right;
            let up = this.up;
            let eye = this.pos;
            let matrix = glMatrix.mat4.create();
            // TODO: Fill this in
            return matrix;
        }




scene:
  isreadonly: true
  code: |
        {
            "name":"objectfirsttester",
            "materials":{
                "green":{
                    "ka":[0.0, 0.4, 0.0],
                    "kd":[0.0, 1.0, 0.0],
                    "ks":[0.8, 0.0, 0.0],
                    "shininess":10
                },
                "grayblueshine":{
                    "kd":[0.5, 0.5, 0.5],
                    "ka":[0.1, 0.1, 0.1],
                    "ks":[0.0, 0.0, 1.0]
                },
                "yellow":{
                    "kd":[0.5, 0.5, 0.2],
                    "ka":[0.3, 0.3, 0.0],
                    "ks":[1.0, 1.0, 0.0],
                    "shininess":5
                }
            },

            "lights":[
                {
                    "pos":[0, 2, 0],
                    "color":[1, 1, 1]
                }
            ],
            
            "cameras":[
                {
                    "pos": [1.3, 4.3, 9],
                    "rot": [0, 0, 0, 1]
                }
            ],
            
            "children":[
                {
                    "transform":[20, 0, 0, 0,
                                0, 20, 0, 0,
                                0, 0, 20, 0,
                                0, 0, 0, 1],
                    "shapes":[
                        {
                        "type":"mesh",
                        "filename":"../assets/js/ggslac/meshes/square.off",
                        "material":"green"
                        }
                    ]
                },

                {
                    "shapes":[
                        {
                            "type":"sphere",
                            "radius":0.5,
                            "center":[-3, 0, 3]
                        }
                    ]
                },

                {
                    "transform":[2, 0, 0, -2,
                                0, 2, 0, 1,
                                0, 0, 2, 0,
                                0, 0, 0, 1],
                    "shapes":[
                        {
                        "type":"mesh",
                        "filename":"../assets/js/ggslac/meshes/homer.off",
                        "material":"yellow"
                        }
                    ]
                },

                {
                    "transform":[1, 0, 0, 3,
                                0, 0, 1, 2,
                                0, -1, 0, -1,
                                0, 0, 0, 1],
                    "shapes":[
                        {
                        "type":"mesh",
                        "filename":"../assets/js/ggslac/meshes/dinopet.off",
                        "material":"grayblueshine"
                        }
                    ]
                },

                {
                    "transform":[2, 0, 0, 0,
                                0, 1, 0, 0,
                                0, 0, 1, 0,
                                0, 0, 0, 1],
                    "shapes":[
                        {
                            "type":"sphere",
                            "radius":0.5,
                            "center":[0, 0, -10],
                            "material":"green"
                        }
                    ]
                }
            ]
        }
---