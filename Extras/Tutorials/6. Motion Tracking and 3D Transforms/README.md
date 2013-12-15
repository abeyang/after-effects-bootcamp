
# Lesson 6: Motion Tracking and 3D Transforms

## Before You Begin

Take a look at the commercial in the `Examples/` directory. Afterwards, take a look at the end result of this shot, as well as the clean plate (500-slab.mov).

Given what you know already, how much of this can you accomplish on your own? What are some things that you might not be too certain about?

In future projects, these are the questions that you'll need to answer for yourself. When you see something neat (like a commercial, or some effect in a movie), you'll need to try to break it down to its parts. However, for now, let's get on with the lesson.

In the After Effects file, go to **COMPS/Lesson 6/** and open up the comp titled **500-slab-vfx**. For this project, I'm just going to go through the basic principles -- it's up to you to apply them.

## Stabilization

The first thing you should notice is that the clean plate is very shaky. If we were filming for *The Blair Witch Project* or the *Bourne* series that might've been acceptable, but product shots are typically still, with no camera movement. Thus, we'll need to stabilize this shot.

Search for "warp stabilizer" in the effects panel. Drag and drop it it onto the footage, and match the settings as shown below:

![][image-1]

OK, the set is now (more or less) still. 

For more information on the warp stabilizer:
- [video][1]
- [purpose and function of each attribute][2]

## 2D vs 3D

Once it's stabilized, what do you think we should do next? You might be tempted to use another pre-comp and adjust the corner pins to fit in onto the Slab inside the footage, but that won't work. A pre-comp essentially flattens everything, so even if its content is true 3D, when we view it as a pre-comp, it'll look and feel like 2D. (You can try this later on.)

Because things pop out in true 3D, we need to treat this comp as such.

### 3D Camera

Create a new 3D camera. I used a [50mm f/1.8 lens][3] for the actual footage (shot inside Starbucks), so please enter this as your specs to the new camera. It's a bit tricky to get everything to work...

![][image-2]

Once you have it there, you can test it out by throwing the slab image in, and turning on the 3D option. Try to get it aligned to the base footage (mine was off a bit from the bottom, but that should be ok).

![][image-3]

> **Pro-tip #1**: You can easily turn on/off the 3D view by clicking on/off the eye icon in the camera layer. I highly suggest doing all the animations in the 2D view, and then RAM previewing it in 3D.

### Elements

All the elements are included in the comp for you -- you just have to make them move/animate.  You should know how to do everything, except for a few presets and tricks, which I'll fill in here.

**Outlined stroke**

For the animated outlined strokes, I used a preset called *Vegas*. For each DT layer, you can just duplicate it, apply Vegas to it (the "transparent" blend mode makes the DT image disappear), and use these settings (animate by "length"):

![][image-4]

--and the settings for the wifi/4g buttons:

![][image-5]

--and finally, the handle (animate by "Rotation"):

![][image-6]

> **Pro-tip #2**: For this lesson, I'm basing it by concept, not necessarily in chronological order. With so many things popping in and out, the best thing to remember is **KISS**: "keep it simple, stupid." Do a pass with the basic animations, and go back to add more animations. In general, fewer keyframes is better, so use the curves to your advantage.

**Fill Color Wipe**

For the DTs, you'll notice that the DT images turn beige, and there's a diagonal fade effect applied to it. Again, duplicate each DT layer, and apply the *Fill Color Wipe* effect to it. Apply these settings, and animate on "Transition Completion":

![][image-7]

**Everything else**

Everything else should be straight-forward, more or less. In the end, remember to tweak the animations to make it more life-like.


[1]:http://tv.adobe.com/watch/cs-55-production-premium-feature-tour-/stabilize-shaky-footage-with-the-warp-stabilizer-in-after-effects-cs55/
[2]:http://helpx.adobe.com/premiere-pro/using/stabilize-motion-warp-stabilizer-effect.html
[3]:http://www.usa.canon.com/cusa/consumer/products/cameras/ef_lens_lineup/ef_50mm_f_1_8_ii#Specifications

[image-1]:Assets/010-warp.jpg "warp stabilizer"
[image-2]:Assets/100-camerasettings.png
[image-3]:Assets/110-enable3d.jpg
[image-4]:Assets/200-vegas-dt.png
[image-5]:Assets/201-vegas-wifi.png
[image-6]:Assets/202-vegas-handle.png
[image-7]:Assets/210-fill.png