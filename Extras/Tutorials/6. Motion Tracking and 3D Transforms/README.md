
# Lesson 6: Motion Tracking and 3D Transforms

## Before You Begin

Take a look at the commercial in the **Examples/** directory. Afterwards, take a look at the end result of this shot, as well as the clean plate (500-slab.mov).

Given what you know already, how much of this can you accomplish on your own? What are some things that you might not be too certain about?

In future projects, these are the questions that you'll need to answer for yourself. When you see something neat (like a commercial, or some effect in a movie), you'll need to try to break it down to its parts. However, for now, let's get on with the lesson.

In the After Effects file, go to **COMPS/Lesson 6/** and open up the comp titled **500-slab-vfx**.

## Stabilization

The first thing you should notice is that the clean plate is very shaky. If we were filming for *The Blair Witch Project* or the *Bourne* series that might've been acceptable, but product shots are typically still, with no camera movement. Thus, we'll need to stabilize this shot.

Search for "warp stabilizer" in the effects panel. Drag and drop it it onto the footage, and match the settings as shown below:

![][image-1]

OK, the set is now (more or less) still. 

For more information on the warp stabilizer:
- [video][1]
- [purpose and function of each attribute][2]

## Elements

...

Before we move on, let's adjust the speed of the ripple effect (on the stroke layer). When the image falls back into the Slab, think of it like a fist hitting the table -- the ripple effect should start off fast, then slow down (rather than slow-fast-slow). Thus, we'll need to adjust the scaling curves from this:

![][image-2]

To this:

![][image-3]



[1]:	http://tv.adobe.com/watch/cs-55-production-premium-feature-tour-/stabilize-shaky-footage-with-the-warp-stabilizer-in-after-effects-cs55/
[2]:	http://helpx.adobe.com/premiere-pro/using/stabilize-motion-warp-stabilizer-effect.html

[image-1]:Assets/010-warp.jpg "warp stabilizer"
[image-2]:Assets/110-curves.jpg "curves (before)"
[image-3]:111-curves.jpg "curves (after)"