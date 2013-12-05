
# Animation Properties

## Intro

Under `Examples` (Lesson 2), watch:
- Clip of **Irritable Bowl Syndrome**
- Both NFL commercials

If you noticed, in addition to text appearing, what else happened? Other things (animations) were occurring on the screen at the same time. But the beautiful thing is -- for the most part -- they weren't complicated animations. And they did **not** rely on filters (the more you observe good animations and such, you'll notice that many of them do not rely on filters). They're just simple animations. But because there's a lot going on the screen at once, it seems like a lot is going on, and that's often what gives a video that "slick" or "cool" feel. 

I repeat -- it's the *combination of doing a lot of tiny things right that makes a video cool*, **not** because they've applied a ton of filters!

For this exercise, in addition to text animation (what we've learned in Lesson 1), but we'll learn the basic properties of animation.

## Hands On

Under Lesson 2 in AE, open up **230-psalm23-vfx**. You'll notice that all the elements are laid out for you. You'll also noticed that the footage with Jasper is currently invisible -- that's ok, just leave it like that for now.

### First Task

Look at the **final video**. Again, your job is to recreate it. From the last lesson, what do you know already? That's right, the text flying in on the right. Let's take what you just learned and apply it right away.

### Additional Properties

++ Opacity/position/scale

For the assets on the left, you'll notice that the way it appears is very similar to the way the text appeared in the previous lesson. It *fades in* while *shifting upwards*. However, unlike the previous lesson, we **won't** be using the text animator.

So, let's start with the image of the lamb (**230-sheep.png**). If the animation begins on 00:12 and ends at 01:04, how would you do it? Because we're working with the *final position* of everything (this is what it will look like when it *ends*), I would begin at 01:04, click the clock icon for position and opacity (remember from Lesson 1 -- that's 'p' and 't' on the keyboard). Go back to 00:12, set the opacity to 0%, and shift the position down by 20px (easy way is to shift + down arrow). Your layer should look like this:

![][image-1]

Do a RAM Preview (remember to set the beginning/end to your work area). Once it's working properly, work on the Psalm 23 text (from 00:20 to 01:12) -- remember, we're going to use the layer properties, not text animator!

**Pro-tip #1**: As you're moving a keyframe, if you hold shift, it will "snap" to key regions of interest (such as a position in the timeline where another keyframe exists or the CTI -- current time indicator -- itself).

Ok, done? Simple, right? 
Well, if you did everything from scratch, there is a *simpler* way--

**Pro-tip #2**: You can copy keyframes from one layer and apply it to another. I would have copied the opacity keyframes from the lamb layer, jump to 00:20, and paste it into the Psalm 23 layer.

**Pro-tip #3**: Going even further, we *could* also copy/paste the position keyframes. With those keyframes still selected, we can then shift the position accordingly -- AE is smart enough to preserve the keyframes. In other words, the beginning and end keyframes will **not** be the same value, but the animated shift upwards will be preserved. This is a good thing!

### Pre-composition + Corner-pin

So, all the elements on the Slab are animated. However, it's not very exciting to have it show up on this 2D image of the Slab -- we want it to be positioned to the Slab that Jasper's holding!

One quick way to do this is to use the *corner pin* filter:

![][image-2]

Let's apply this to the slab layer. Move the corner pins so it matches with the slab that Jasper is holding (turn that layer visible if you haven't done so already):

![][image-3]

That's cool and all, but how do we get this applied to the other layers? While you *could* just copy/paste this effect to the others, what would happen if we need to change something around (like move a corner pin over)? Wouldn't it be *great* if we only apply this effect once, and have it apply across the board?

This is where **pre-compose** (or pre-comp) comes in. Select all the layers except the Jasper footage, and go to **Layer-\>Pre-compose...** (or Shift+cmd+C).  Name it "Precomp Slab (2)". Those layers should now be collapsed into one. If you scrub the timeline, you'll see that your animations are preserved; double-click to jump in and see the rest of your layers. Essentially, we've created a comp inside a comp.

Now, apply the corner pin on the pre-comped layer. Play with the corner pins? All done, right? *Wrong*:

![][image-4]

You'll notice that it's really hard to align the corner of the slab image to the  on in the footage. The reason is because the pre-comp is using the same resolution as the base footage; what we really want is for the pre-comp to mirror the dimensions of the slab image.

Select the pre-comp in the project window and go to **Composition-\>Composition Settings...** (or cmd+k). Change the dimensions to this:

![][image-5]

Once that's done, try apply the corner pins again. Success!

## Conclusion

By working on the flat image of the slab first, this ensured that your animations will not "fly off" Jasper's slab. Moreover, it's much easier to work in 2D (up is up on the Y axis) than in 3D ("up" is really a combination of directions on the X/Y/Z axes). By pre-comping the layers together, we were able to do one corner-pin effect and it's applied to all.

If you noticed, Jasper isn't keeping the Slab perfectly still, so it looks like our "user interface" is sliding right off of it; it looks like we simply Photoshopped this in. Don't worry about it for now; we'll tackle "tracking" in a future lesson.

[image-1]:Assets/100-sheep.png "Keyframes on the sheep layer"
[image-2]:Assets/200-cornerpin.png
[image-3]:Assets/210-slabonslab.png
[image-4]:Assets/220-misaligned.jpg "Misaligned corners"
[image-5]:Assets/230-rightdimensions.png "Correct dimensions"