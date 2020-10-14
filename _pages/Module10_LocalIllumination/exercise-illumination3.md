---
layout: exercise_javascript_shader
permalink: "Module10/ClassExercise"
title: "CS 476: Computer Graphics - Phong Shading"
excerpt: "CS 476: Computer Graphics - Phong Shading"

info:
  prev: "./Video2"
  points: 2
  instructions: "Move the code for Phong illumination in the vertex shader over to the fragment shader.  You create varying attributes for intersection, normal, and color"
  goals:
    - Explore how to convert Gouraud shading into Phong shading by moving the appropriate code over from the vertex shader to the fragment shader

processor:  
  correctfeedback: "Correct!!" 
  incorrectfeedback: "Try again"
  submitformlink: false
  feedbackprocess: | 
    let correctStr = "";

  correctcheck: correctStr


vert:
  isreadonly: false
  code: |
        precision mediump float;
        #define MAX_LIGHTS 10
        struct Light {
            vec3 pos;
            vec3 color;
            vec3 atten;
        };

        // Material properties
        uniform vec3 uKa; // Ambient color for material
        uniform vec3 uKd; // Diffuse color for material
        uniform vec3 uKs; // Specular color for material
        uniform float uShininess; // Specular exponent for material

        // Transformation/projection matrices
        uniform mat4 uMVMatrix;
        uniform mat4 uPMatrix;
        uniform mat4 tMatrix;
        uniform mat3 uNMatrix;

        // Light properties
        uniform int numLights;
        uniform Light lights[MAX_LIGHTS];

        // Camera properties
        uniform vec3 uEye;

        // Per-vertex attributes
        attribute vec3 vPos;
        attribute vec3 vNormal;
        attribute vec3 vColor;


        // Stuff to send to fragment shader
        varying vec3 color;

        void main(void) {
            // Transformed position of vertex in homogenous coordinates
            vec4 tpos = tMatrix*vec4(vPos, 1.0); 
            // Transformed normal of vertex
            vec3 NT = normalize(uNMatrix*vNormal); 
            // Viewing window position, taking into consideration the camera
            gl_Position = uPMatrix*uMVMatrix*tpos; 


            vec3 LPos = lights[0].pos; // Position of light
            vec3 VPos = tpos.xyz; // Position of the vertex in world coordinates

            // Diffuse coefficient
            vec3 LVec = normalize(LPos-VPos); // Unit vector from vertex to light
            float kdCoeff = dot(NT, LVec);
            if (kdCoeff < 0.0) {
                kdCoeff = 0.0;
            }

            // Specular coefficient
            vec3 dh = -reflect(LVec, NT);
            vec3 h = normalize(uEye-VPos);
            float ksCoeff = dot(h, dh);
            if (ksCoeff < 0.0) {
              ksCoeff = 0.0;
            }
            ksCoeff = pow(ksCoeff, uShininess);

            color = uKa + lights[0].color*(kdCoeff*uKd*vColor + ksCoeff*uKs);
        }



frag:
  isreadonly: true
  code: |
        precision mediump float;
        varying vec3 color;

        void main(void) {
            gl_FragColor = vec4(color, 1.0);
        }

scene:
  isreadonly: true
  code: |
        {
            "name":"localilluminationscene",
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
                    "pos": [-0.02,4.02,4.65],
                    "rot": [0.20,0.02,0.00,0.98]
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
                    "transform":[2, 0, 0, -2.5,
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