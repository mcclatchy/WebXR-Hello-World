# WebXR-Hello-World
A series of thoroughly commented a-frame demos

This is intended to help developers & designers start playing with and thinking about WebXR.

Everything the New Ventures Lab has built for the web (including the target based AR gallery above) is based on a framework called A-FRAME that was created at Mozilla.

A-Frame is open-source, available on GitHub and well documented at aframe.io. It's an entity component system, which means it's simple and extensible. If you want to go a layer deeper check out Three.js (which we've occasionally used to write custom aframe components).

The Plan
For our "Hello World" we're going to create a simple 360° photo-sphere similar to google's street view. This is the simplest form of VR, something we describe as three degrees of freedom or "3DoF VR." It's called 3DoF because the user can rotate the content around themselves on the X,Y, or Z access.

The Content
equirect.jpg

We have just one asset to worry about. It's a bitmap called a "sky" or "sky-box" and it textures the VR environment we're creating for the user. Skyboxes can be created, delivered and stored in a variety of ways. We're going to focus on "equi-rectangular photos." Most of our newsrooms now have equipment to create photos & videos in this format. They're created buy a camera with at least two fish-eye lenses that capture a whole sphere's worth of pixels.

The cameras use a "equirectangular projection" to store the spherical data in a bitmap (exactly the same way a world map presents information on a globe). These photos are usually stored as a JPEG in a 2:1 aspect ratio. Each is 360° across & 180° high.

Since the user is only ever viewing a small piece of the bitmap, the images need to be very large in order to provide a high quality experience. We encourage video to be recorded at, at least 4K (3840 × 2160px) resolution. We don't have a standard practice for still, but the most commonly used camera in our newsrooms captures spheres as 8k images (7744× 3872px)

The Code
We can actually achieve our entire demo with aframe and just ten lines of code. 

<html>
  <head>
    <script src="https://aframe.io/releases/latest/aframe.min.js"></script>
  </head>
  <body>
    <a-scene>
      <a-sky src="sample_equirectangulars/3.jpg" rotation="0 -130 0"></a-sky>
    </a-scene>
  </body>
</html>

Result
giphy.gif

See attached .ZIP for src & Comments 

Next Steps

This is just the beginning of what you can do with a-frame. The resulting page has built-in support for mobile devices, Google Cardboard and HTC Vive headsets. 

Here are some suggestions for other things to try: 

Step up to 6DoF 
In six degree of freedom VR, the user can rotate around on 3 axis, AND move around on the same three axis. 

Right now your VR scene only has a "sky." In order to experience 6DoF you need to place some objects near by. Try it out by adding some some simple 3D meshes (called "primitives" in 3D modeler speak) into the scene. 

Just copy and paste some or all of the assets below between your 
<a-scene> and </a-scene> tags. 

<a-text 
font="kelsonsans" 
value="Hello World" 
width="6" 
position="-1 2 -3"
rotation="0 15 0"
color="#000">
</a-text>

<a-box 
position="-1 0.5 -3" 
rotation="0 45 0" 
color="#4CC3D9" 
shadow>
</a-box>

<a-sphere 
position="0 1.25 -5" 
radius="1.25" 
color="#EF2D5E" 
shadow></a-sphere>

<a-cylinder 
position="1 0.75 -3" 
radius="0.5" 
height="1.5" 
color="#FFC65D" 
shadow>
</a-cylinder>

<a-plane 
position="0 0 -4" 
rotation="-90 0 0" 
width="4" 
height="4" 
color="#7BC8A4" 
shadow>
</a-plane>


Now after reloading your scene press the W,A,S&D keys to "walk" around the virtual space. 

A-Frame even comes with a visual inspector for adjusting scenes with a GUI interface. Hold  <ctrl> + <alt> + i  while on the page, to access the inspector.

Add interactivity
Try building in interactivity using with the 360° Image Gallery Guide from the documentation.

Add a complex mesh
Use the asset system and support for the new glTF 3D file type to load a model scanned by the NVL team. (See .ZIP for files)
