---
layout: exercise_javascript
permalink: /VPNCheckJS
title: "CS476: Checking Module Backend Connection"
excerpt: "CS476: Checking Module Backend Connection"
canvasasmtid: "95313"
canvaspoints: "2"

info:
  instructions: "Students will be completing online, interactive pre-class modules to learn topics before class.  Part of these modules will involve completing small code exercises live in the browser to check comprehension.  In order to get credit for completing these exercises correctly, students must either be on campus, or they must be connected to the Ursinus VPN.  If you are off campus, please follow the directions at <a href = \"https://www.ursinus.edu/live/files/3555-uc-vpn\">this link</a> to setup the VPN on your machine (If you have an operating system other than Mac or Windows, please contact me and I can help you).  Once you are either on campus or connected to the VPN, enter your netid and hit the \"run\" button below.  If everything is as it should be, you will get an e-mail confirming your submission, and you will automatically receive 2 points on Canvas.  Otherwise, after about a minute, you will receive a popup error that you are unable to connect."
  goals:
    - To configure the VPN on your machine for future exercises
    
processor:  
  correctfeedback: "Attempting to connect to the VPN.  You should receive an e-mail shortly if it worked" 
  incorrectfeedback: "Try again"
  submitformlink: false
  feedbackprocess: | 
    var pos = feedbackString.trim();
  correctcheck: |
    true
 
files:

  - filename: "Student Code"
    name: tester
    ismain: false
    isreadonly: false
    isvisible: true
    code: | 
        function printHello() {
          console.log("Hello world!");
        }  

  - filename: "Test Block"
    ismain: true
    name: main
    isreadonly: true
    isvisible: true
    code: |
        printHello();
        
---
