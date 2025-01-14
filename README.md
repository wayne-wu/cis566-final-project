# Interactive Dance Projection with TouchDesigner

## Introduction

Generative art that are interactive is something I have always loved, especially since visiting large scale exhibitions by studios like [teamLab](https://www.teamlab.art/) and [Moment Factory](https://momentfactory.com/home). While the main purpose of computer graphics is to generate beautiful images, these visual experiences can be greatly elevated by integrating sensors and input systems to involve the audience in the art form. Recently, I have been playing around with [TouchDesigner](https://derivative.ca/) and the LeapMotion controller to create interactive art using hand motions. However, these experiences are thus far limiting in space. It is now time for me scale it to the next level both in terms of display output and the input system.

The theme of this project focuses on two important interests of mine: **dancing** and **fashion**. I recently discovered the music genre of **Deep House**, which is both a type of [dance](https://www.youtube.com/watch?v=PbSv9doE9IY&ab_channel=MOVEDanceStudio) as well as the genre heavily used in the fashion industry for fashion runways or stores like ZARA. For example, [check this song out](https://www.youtube.com/watch?v=KD3sOUxKp9g&ab_channel=MelomaniacRDV) to get a sense of the vibe. My plan is to integrate these two elements into my work as I design the overall audience experience and the visuals.

## Goal

The goal of this project is to create an audio-and-motion-reactive visualization of Deep House music. Specifically, there are a few core objectives that I would like to meet:

* The visuals react to a playlist of Deep House music coherently. The overall mood established should follow the beats and pace of the music.
* The project will be rendered in real-time at an interactive rate (minimum 30 fps).
* The audience can interact with the visualizer by moving their bodies and dancing to the music.
* The project can be scaled to a larger environment, ideally displayed using a projector and have multiple people interact with it at the same time.
* The visuals must be polished with fine-tuned color schemes that feel in place with the overall theme of the project.
* BONUS: Install the project somewhere on campus for people to actually interact with, and record a video showing this.

**The above goals are dependent on my ability to source the hardware.*

## Inspiration & References

- [TouchDesigner Artist: Bileam Tschepe](https://www.instagram.com/elekktronaut/) - he has lots of cool patterns created in TouchDesigner that would go well with Deep House.
- [Universe of Water Particles - teamLab](https://www.teamlab.art/ew/waterparticles-transcending_superblue/superbluemiami/) - one of my favorite pieces from teamLab. Love the use of lines as waterfall. The color contrast between the waterfall and the flowers also works very well.
- [TouchDesigner: Popping Dance w/ Particles](https://www.youtube.com/watch?v=oSPbZISVjRM) - an example of the type of interactivity that's possible with TouchDesigner.
- [TouchDesigner: Audio-Reactive Voronoi](https://www.youtube.com/watch?v=tQp2osjgfYE&ab_channel=VJHellstoneLiveVisuals) - the type of background visuals that would be good for this project. Nothing too complex.
- [Taipei Fashion Week SS22 - Ultra Combos (Only available in Chinese)](https://ultracombos.com/SS22-Taipei-Fashion-Week-SS22) - love the aesthetics of the background for this fashion show. 

## Specification

This project will be implemented using **TouchDesigner** simplifying technical implementations. The inputs to the system will be a depth sensor camera such as ZED Mini or Kinect, as well as audio signals from the music. These signals will be used to drive the various parameters of the visualization.

The visualizer can be broken down into multiple visual layers which are composited together. Specifically there are four layers that are included in the project:

1. **Background Layer**: this layer will be the background for the final render. It will include procedurally generated patterns that are relatively simple, such that they do not overpower the foreground elements. These patterns will be **audio-reactive**.

2. **Interaction Layer**: this layer will contain procedural elements that are **motion-reactive** thus making it interactive. For example, a particle system can be included that are reactive to the motion of the audience. This should be the primary focus of the art for the audience.

3. **Reprojection Layer (Stretch Goal)**: this layer is optional and will only be implemented if time permits. It will contain a stylized reprojection of the actor. This layer allows a clearer indication of where the actors are. This reprojection layer can be **audio-reactive**.

4. **Post-processing Layer**: this layer is for enhancing the visuals by applying post-processing effects to the previous layers. This layer is crucial in achieving the desired look, feel and mood.

Finally, the composited render will be displayed using a projector.

## Techniques

The project will explore many common procedural techniques, including but not limited to the following:

* **Particles Simulation** - particle systems will be used to add interactivity to the scene, and/or as an decorative element. These systems will be driven by custom forces that are guided by noise functions and input signals. The GPU-based particle systems will be used in TouchDesigner in order to meet the real-time requirement.
* **Procedural Patterns** - procedural patterns will be generated using noise and toolbox functions along with basic geometric shapes. The idea is to generate a simple audio-reactive background that complements the main interactive layer.
* **Optical Flow** - optical flow is a common technique used in TouchDesigner with a camera to affect the image output. The motion between frames captured from the camera will be converted to velocity signals that can drive other parameters in the scene.
* **Noise and Toolbox Functions will be used everywhere!**
* **Post-processing Techniques** - bloom effect, blur, feedback, distortion and edge detection will be experimented with to enhance the visuals.
* **Coloring** - a specific color palette will be selected that best describes the theme of the project. This is all about making it look pretty!

## Design

![diagram](imgs/diagram.png)

## Timeline

### Week 1 (11/09-11/16)
* Establish the color tone
* Curate the playlist to go with the visualizer
* Source the required hardware
* Create a simple audio-reactive pattern for the background layer
* Create a simple motion-reactive visual using the webcam for the interaction layer

### Week 2 (11/16-11/23)
* Fine tune the shape for the background layer
* Connect the depth sensor to the interaction layer and finalize the experience
* Add in post-processing layer

*(Will not be working from 11/23-11/28)*

### Week 3 (11/28-12/05)
* If time permitting, implement a simple reprojection layer
* Color grading and parameters tuning
* Install the project somewhere on campus

# Milestone 1 Update

For Milestone 1, I experimented with various procedural patterns in order to find one that works best with the vibe of the music as the background layer. Below are some of the patterns that I was able to create following Bileam Tschepe's awesome tutorials. These patterns are currently all just black and white. The color and composition mode will be determined in the next milestone.

| *[Tile Pattern](https://www.youtube.com/watch?v=gXUWcYZ8hqQ&ab_channel=bileamtschepe%28elekktronaut%29)*  | *[Texture Instancing](https://www.youtube.com/watch?v=uFFXUPP0cyg&ab_channel=bileamtschepe%28elekktronaut%29)* |
| ------------- | ------------- |
| ![pattern1](imgs/pattern1.gif)  | ![pattern2](imgs/pattern2.gif) |

| *[Texture Feedback](https://www.youtube.com/watch?v=NMvx_icZUhY&t=266s&ab_channel=bileamtschepe%28elekktronaut%29)*  | *[Line Feedback](https://www.youtube.com/watch?v=zCNREVDLVo8&ab_channel=bileamtschepe%28elekktronaut%29)* |
| ------------- | ------------- |
| ![pattern1](imgs/pattern3.gif)  | ![pattern2](imgs/pattern4.gif) |

Additionally, I have also tested out the optical flow tool inside TouchDesigner by feeding in a [house dance video](https://www.youtube.com/watch?v=VEE5qqDPVGY&ab_channel=JardySantiago) for testing. This particular video works well because the camera is static, and the framing of the actor is similar to how I would set up my camera sensor. Theoretically, I should be able to just swap the footage with a camera input later on and everything should work accordingly. 

By processing the optical flow data using a feedback loop, we can get a smoothly motion-blurred silhouette of the actor. Finally, optical flow is then used to drive a simple particle system as shown below. The result is very promising as I may potentially not have to get a depth sensor camera and can drive everything using just a webcam.

![opticalflow](imgs/opticalflow.gif)

Finally, if we composite one of the audio-reactive patterns with the interaction layer, we can get something interesting like this:

![compose](imgs/compose.gif)

However, I'm still not happy with the overall look. I do have patterns that I can work with but none of them really speaks with the music. Therefore, I may take or discard elements from each pattern to create something more original and interesting. Moreover, I'm also not satisfied with the color tone. There are some interesting color palettes [here](https://www.shutterstock.com/blog/10-color-palettes-and-patterns-inspired-by-new-york-fashion-week) based on NY fashion week that I will be exploring.

# Milestone 2 Update

For Milestone 2, I did not get as far as I would have liked to, but I was able to tweak some of the parameters of the procedural elements and make more of the parameters audio-reactive. I changed the texture instancing pattern to have larger texture size such that more of the particle systems can be seen once overlayed by the procedural pattern. The particles are now spawned at the bottom, closer to the feet, since House dance focuses a lot on the bottom movements. I have brought the reprojection of the actor as a foreground element so it can be seen more clearly now. Finally, I have also changed the color tone to be cooler, although I'm still not 100% satisfied with it.

Here's a video of the current state:

https://user-images.githubusercontent.com/77313916/204447443-830f3ccc-7921-4b64-8074-61e143c864df.mov

I was not able to test it with a depth sensor or projector as I was not able to acquire them on time. However, I will be getting the ZED mini this week and will rent a projector from the library to test the setup.

# Final Version Update

For the final version of the project, I have separated out the procedural patterns as individaul scenes instead of composing them all together. This allows the audience interactions to be more visible, while reducing the overall complexity of the scene, which was previously quite overwhelming. The four scenes are: flakes, lines, tiles, and waterfall.

<img width="1511" alt="Screen Shot 2022-12-05 at 10 24 50 AM" src="https://user-images.githubusercontent.com/77313916/205735938-fa2cd2cc-a163-40cb-921c-ad861ec3cccd.png">

# Live Installation

For the live installation, I've set up the projector and ZED mini on a desk and projected the visuals on a plain wall in our lab. Since the space is limiting, the size of projection is roughly 3.2m x 1.8m. Ideally, it could be scaled up even further.

<img src="https://user-images.githubusercontent.com/77313916/205736554-6bf6a3e6-5a87-4877-a82a-8577979dc43b.JPG" width="640" height="360">

<img src="https://user-images.githubusercontent.com/77313916/205736567-d4f00a94-3f54-4c28-b336-b580cc8691ad.JPG" width="640" height="360">

## Flakes

<img src="https://videoapi-muybridge.vimeocdn.com/animated-thumbnails/image/b23ac24c-b752-412b-94d7-9ffa7e1bfd92.gif?ClientID=vimeo-core-prod&Date=1670271445&Signature=6e660fb96fb42aeed91f6b7ffc32c2a92f52b0d3" width="640" height="360">

## Lines

<img src="https://videoapi-muybridge.vimeocdn.com/animated-thumbnails/image/00bd470e-7b06-41c8-b53c-3357a795ab22.gif?ClientID=vimeo-core-prod&Date=1670271685&Signature=1c2f32e8cf83ccf56d73d72bd296179634d1f69e" width="640" height="360">

## Tiles

<img src="https://videoapi-muybridge.vimeocdn.com/animated-thumbnails/image/d25303f9-50a8-44f5-b61f-08e08ff79a24.gif?ClientID=vimeo-core-prod&Date=1670272342&Signature=d4f805c7572b8576025cccec5510e8355e0486e8" width="640" height="360">

## Waterfall

<img src="https://videoapi-muybridge.vimeocdn.com/animated-thumbnails/image/cef90173-3b01-4405-81ea-e06a098ef9e6.gif?ClientID=vimeo-core-prod&Date=1670272266&Signature=32c5b521bd67cc0568267c06e9d4fc4ed95d27be" width="640" height="360">

# [Check out the final live demo here!](https://vimeo.com/manage/videos/778235844)




