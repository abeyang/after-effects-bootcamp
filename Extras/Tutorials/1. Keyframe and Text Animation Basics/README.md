
# Keyframing + Text Animation Basics

## Intro

Watch the **Designed by Apple** video under `Examples/`. Even though the it's about what Apple looks for in its products, I think a majority of it is true to what animation and effects can do for videos (ok, so it doesn't "enhance each life it touches").

Now, there's *a lot* of things that can be done with After Effects (AE). There's a lot of one-off stuff that you can do, and there's typically a dime-a-dozen tutorials out there on the web that teaches how to pull each one of them off. Thus, this bootcamp will *not* cover these concepts in AE:

- Color correction
- Green screen / keying
- 99.9% of the filters out there
- Lightsabers

Instead, we'll be covering principles in animation, along with some touches of minor compositing techniques. Knowing the basics will be helpful in whatever you choose to do with AE (yes, even for adding in lightsaber effects... shudder).

For this lesson, we'll be dealing with *keyframes* and *text animation*.

## Getting Started

This bootcamp assumes that the student has some working knowledge of After Effects. I'll try to cover parts of the interface that I'll think will be useful, but for the most part, I won't talk about it. Please brush up on your [basic After Effects knowledge][1] if you need to do so.

Before you start with the After Effects project, make sure you look at the **final video**, so that you know what you're getting yourself into.

Open up **Visual Effects.aep** under `Project/` and find **200-voice-vfx** under **COMPS/Lesson 1/**. You should see something like this:

![][image-1]

It's Jasper with the text that he'll eventually say. What we want to do is animate the block of text, and sync it to words he's saying.

## Interface

### Layers + Timeline

![][image-2]

If you know Photoshop and Premiere, then the timeline should be rather intuitive [^1]. The main difference is that in AE, each layer has its own set of properties. This is where you can manually set certain things, like the position or scaling of the object. 

**Pro-tip**: It may be overwhelming once you open up all the properties, so you can view specific properties by selecting one or more layers, and hitting the following keystrokes:

- **P**: position
- **R**: rotation
- **S**: scaling
- **T**: opacity (think opaci-T)
- **A**: anchor point

You can open up more properties by holding down the **Shift** key.

### Terminology

Ok, let's get a few things straight:

- **Layer**: There are many *types* of layers, such as type, solid, shape, etc. You can view all the types when you go to Layer-\>New.
- **Property**: A specific attribute associated with a layer (see screenshot above).
- **Comp**: Short for composition, a comp consists of many layers.
- **Pre-comp**: We'll get into this in a bit, but it's *essentially* a comp [^2].
- **Keyframe**: A specific property set in a specific time within a layer. Used for animation purposes. Huh? Let's dive right in.

### Text Animation - Opacity

Ok, so going back to the project, there's nothing fancy going on. Just a block of text, sitting there. We'd like to make each word appear in sync with what Jasper's saying.

If you notice from the **final video**, there are two things happening to the text as they appear:

1. Each word slides in from bottom to top
2. At the same time, each word fades in

So, let's get animatin'!

Let's start with the **opacity** since that's visually easier to grasp. In the text block, open up the properties, and you'll find *Text-\>Animate-\>Opacity*:

![][image-3]

You'll notice that it'll add an *Animator* property, which includes a *Range Selector* and *Opacity*. For now, set the *Opacity* to 0, so it should look like this:

![][image-4]

**Pro-tip**: If you scrub the *Start* property to the right and left, you should see something magical. You can do this for every numeric attribute.

![][image-5]

However, you'll notice that the text is appearing letter-by-letter. That's nice, but that's not what we want. Go to *Advanced-\>Based On* and change from "Characters" to "Words":

![][image-6]

Now that we have the opacity figured out, let's add the **position** property. Because we've done the heavy lifting already, this will be pretty easy. Next to *Animator 1*, click on *Add-\>Property-\>Position*:

![][image-7]

The position you see is in X,Y coordinates, so let's set the Y property to 10. You should now have these properties set to these values:

![][image-8]

### Keyframes

...

- Layers + timeline
	- keyframes (clock icon)
	- choosing specific properties

### RAM Preview

- RAM Preview
	- beginning / end
	- novice error: using 1 keyframe per action instead of 2 (need 2 to "hold")

## Conclusion

This is easy because you only had to keyframe one property.. future examples will be more complicated.

[^1]:If not, please Google "Photoshop layers".

[^2]:As far as I know, there is no real difference. Pre-comps can be thought of as comps inside comps.

[1]:http://tv.adobe.com/watch/learn-after-effects-cs6/introducing-the-interface-and-the-workspace/

[image-1]:Assets/010-text.png "block of text"
[image-2]:Assets/020-layers.jpg "Layers + Properties"
[image-3]:Assets/100-opacity.png "Text->Animate->Opacity"
[image-4]:Assets/110-animator.png "Animator + Range Selector"
[image-5]:Assets/120-animator.jpg "scrub left and right"
[image-6]:Assets/130-words.jpg "Based on Words, not Characters"
[image-7]:Assets/140-add-position.png "Add->Property->Position"
[image-8]:Assets/150-set-properties.png "Set properties"