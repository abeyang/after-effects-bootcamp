
# Animation Curves + Trackers

## Intro

Watched the **Everpix** commercial under `Extras/`. 

A good adjective to describe this video is that it's *fun* (another one is *playful*).  It's very well done. If we were to give the original assets (all the drawings, the voiceover narration, even the music) to a lesser animator, I can imagine that it wouldn't be nearly half as good. And that's what I'd like to address in this lesson: 

> What makes an animation *good*?

## Animation Principles

First, I want to say that I am *not* an expert animator. The second thing is that it takes a lot of time to refine and craft animations into something that *feels good*. When I went to art school, it took me 8 weeks to model and rig a 3D character (from scratch), and another 7 weeks just to animate a [two second clip][1].

Whole lessons and [books][2] are taught on this subject matter (it was one of the more popular majors in Academy of Art in SF), but for the sake of time -- and as a basic primer for beginners -- "good" animation can be boiled down to this (very general) rule of thumb:

> Things "look good" when it matches to perceived reality

Ok, sounds obvious right? However, when you start animating, you'll be surprised how oftentimes things "don't look right" or "mechanical", and it's often because it doesn't match to our perceived reality of things. For example, if I were to ask you to animate a bouncing ball, how would you do that? It's *not* just a matter of setting a few keyframes, because that would not accurately reflect how gravity would affect it.

Another example is that when something slides in and slides out, almost nothing in reality maintains the same speed throughout that entire process. Think of a car: from stop to motion there is a ramp-up time (acceleration) before it reaches its desired velocity.

So, in the Everpix video, things don't move from one place to another statically. There are bounces, there are momentum shifts, there are ramp-ups and ramp-downs (or "ease-in" and "ease-out" in AE terms). A lesser animator might have only two keyframes between one animation; the expert animator would have a bunch (as well as modifying the animation curves -- more on that later), just to make it feel more grounded in reality.

Ok, enough philosophizing -- let's get started with our lesson.

## Getting Started

Let's watch this [commercial from Coin][3]. Did you see how the credit cards pop out of the "Coin"? (It's hard to notice the ease-in, but it's there.) We're going to try to emulate that, and add a slight *Minority Report* / *Ironman* twist to it.

Open **110-wide-vfx** under `Lesson 4/`. Let's also add *one* DT journal into the comp (let's use **Assets/dt-11-12.jpg**). For now, we'll just key in on the part where Jasper flicks it away.

## Linear vs. Easy-ease

Jump to 03:07 in the comp. Center the DT image on Jasper's finger -- jump forward 10 frames (cmd+shift+right) and move the image out of frame (top).

> **Pro-tip #1**: If you hold shift as you drag an image, it will lock itself into an axis (for us, that would be the Y-axis). Otherwise, as you're dragging, you would invariably mess with the X-axis as well.

If you do a RAM Preview, it looks rather mechanical. Before we proceed, let's take a look at its graph. 

> **Pro-tip #2**: When working with animations in which you're dealing with individual axes, it would be highly recommended to separate them out in AE. Right-click on the Position property and select *Separate Dimensions*

Once that's done, click on the graph icon (next to the clock) for "Y Position", and then select the *other* graph icon (Graph Editor) near the top of the timeline. You should see something like this:

![][image-1]

What we're seeing is a linear graph; the speed is constant throughout the two keyframes.

Go back to the normal timeline view (click on the graph icon again). With the keyframes selected, right-click and select *Keyframe Assistant-\>Easy Ease* (for F9). You'll notice that your keyframe markers now look something like an hourglass. Do a RAM Preview -- do you notice a difference? How would you describe it? Let's look at the graph again -- it should look like this:

![][image-2]

Yes, horrible flashbacks to your physics classes are coming back! So, what are we seeing? It starts out slow, ramps up to speed, and then ends slowly. If Jasper was flicking a toy car on a table, the initial part of the graph would look like this. However, the toy car wouldn't decelerate -- not that quickly, anyways. So let's adjust the ending part of the graph a bit. Select the last keyframe, and grab the yellow handle, and move it up like so:

![][image-3]

So, what this graph is describing is that starts off a bit slow, picks up speed and stays that way until it's out of screen. RAM-Preview it -- feels better, right?

## Tracking DTs to the Slab

If you notice, there are two separate things happening in this footage:

1. Jasper's interaction with the Slab+DTs (we just covered a part of this)
2. Slab's interaction with the DTs -- the DTs follow the Slab's movements

So, let's delete the keyframes you've just created (we'll get to those later), and let's import the rest of the DTs (01-02 should be on top / 11-12 should be on bottom). How do we group these six DTs together?

### Null Object

For simplicity's sake, we will:

- Just track based on position and rotation. It would be nice to track the full perspective of the slab, but that's harder than it looks.
- Use a **null object** rather than a pre-comp. If you recall, a pre-comp requires a specific dimension. Let's not worry about that. Moreover, once you use a pre-comp, you have to jump *in* a pre-comp to change its layers. What we want is to group the layers, but *still be able to modify* its properties directly in this comp (for Jasper's interaction).

Create a null object (*Layer-\>New-\>Null Object*). A null object is literally a *blank layer* -- it's intended to be a parent of other layers. So let's do that -- select all the DT layers, and either drag the spiral icon to the null layer, or use the drop down box and select the null layer:

![][image-4]

Now, select the null object, and move it around. What else happens?

### Adding a Tracker

Now that we have the null object set, it's time to track it!

#### Trackers

Each tracker comes with 3 distinct parts:
1. Outer square (search region)
2. Inner square (feature region)
3. Crosshair (attach point)

Naturally, each part has its own function (from [Adobe's site][4]):

> The **feature region** defines the element in the layer to be tracked. The feature region should surround a distinct visual element, preferably one object in the real world. After Effects must be able to clearly identify the tracked feature throughout the duration of the track, despite changes in light, background, and angle.

> The **search region** defines the area that After Effects will search to locate the tracked feature. The tracked feature needs to be distinct only within the search region, not within the entire frame. Confining the search to a small search region saves search time and makes the search process easier, but runs the risk of the tracked feature leaving the search region entirely between frames.

> The **attach point** designates the place of attachment for the target —the layer or effect control point to synchronize with the moving feature in the tracked layer.

#### Attaching Tracking Points

For this lesson, we will track the rotation and position of the slab. We would do the 3D geometry as well, but that's getting ahead of ourselves. Make sure the tracker window is visible (**Window-\>Tracker**), set "Motion Source" to the footage layer (begins with "110"), and do a "Track Motion" on it. Yours should look similar to this (with the Motion Target being your null object):

![][image-5]

Generally, to get a good track, the search region should be plain and simple, whereas the feature region should be set on something distinct. Now, I'll admit -- this wasn't filmed with proper trackers. It would have been nice if I used a [different color tape][5] to demarcate the corners of the Slab. Nonetheless, we're still able to get a decent tracker in.

Let's start at 02:07. Since Jasper's shirt is a solid color, we can use that as a good background for Track Point 2, so let's set the target to the bottom-right corner of the slab. Track Point 1, however, cannot be the above corner, because the background keeps changing (Jasper moves the Slab around substantially). So, set Track Point 1 to the dot that's the most isolated, and pin the *attach point* to the corner:

![][image-6]

Analyze the trackers forward until 07:07 -- everything should go by without a hitch. Go back to 02:07, and analyze backwards until 00:21. This is a little bit harder, because when Jasper gives the Slab a shake, that will most likely mess up your trackers. Manually adjust in the *attach points* for the ones that need it.

#### Applying Trackers

Once you're done, apply the trackers to the null object (X and Y positions). You might notice something strange -- your DTs will suddenly be rotated 90 degrees. One way to easily compensate this is to select the DT layers, and adjust the rotation all at once:

![][image-7]

### Your Turn

Scrub through the timeline, and hopefully your DTs will "stick" to the slab. Now, finish the rest of the animation, including:

- Jasper "popping" out the DTs
- Jasper flicking away the DTs
- Jasper grabbing (and merging) DTs, and flicking them back into the Slab

## Outline (to delete)


- Null objects and trackers
	- [More information on trackers][6]
	- duplicate Precomp (3) and rename it to Precomp (4)
	- loading: 07:06
		- from 09:14 on, manual track (just the attach points)

## Advanced

If you're done early, you can do these exercises:


Go back to lessons 2-3 and--
- Add trackers to the Slab, and apply the keyframes to the UI. Right now the UI just "slides" on top of the Slab (as Jasper can't hold it perfectly still). This will make it feel more realistic.
- Smooth out the animation keyframes (where it makes sense).


### Loading Indicator 

Add the **loading indicator** comp. It should show up from 07:01-09:22. Instead of the Transform track type, you'll need to use the *perspective corner pin*. Similar to Track Point 1, for all four points, you'll need to track certain dots that are fairly distant from the others. Bonus points if you get that spin down, because that's all manual!

### Lesson 2's Tracking

Track the slab from Lesson 2, and apply to the UI. I started at 0:15, with these points:

![][image-8]

### Lesson 3's Tracking

Track the slab from Lesson 3, and apply to the UI. I started at 1:06, with these points:

![][image-9]

Track Point 1 was rather difficult -- I had to make sure the search region didn't hit the other dots.




[1]:https://vimeo.com/5086644
[2]:http://en.wikipedia.org/wiki/12_basic_principles_of_animation
[3]:http://quietube6.com/v.php/http://www.youtube.com/watch?v=w9Sx34swEG0
[4]:http://helpx.adobe.com/after-effects/using/tracking-stabilizing-motion-cs5.html
[5]:https://vimeo.com/76845690
[6]:http://helpx.adobe.com/after-effects/using/tracking-stabilizing-motion-cs5.html

[image-1]:Assets/100-graph.jpg
[image-2]:Assets/110-graph.png
[image-3]:Assets/120-graph.png
[image-4]:Assets/130-nullparent.jpg
[image-5]:Assets/200-tracker.png "Tracker window"
[image-6]:Assets/210-trackers.png
[image-7]:Assets/220-rotation.png
[image-8]:Assets/300-lesson2.png
[image-9]:Assets/400-lesson3.pn