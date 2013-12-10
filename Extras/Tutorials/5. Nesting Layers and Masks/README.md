
# Lesson 5: Nesting Layers and Masks

## What We Want to Produce

If you look at the final video, you'll see that this is very similar to the previous lessons. However, if you look carefully at the UI, it gets cut off *before* it reaches the edge of the slab. This is done via *masks*.

In this lesson, you'll learn:

- How to apply masks
- Feathering
- Importing Photoshop files into AE

## Importing Photoshop Files

Go to **File-\>Import-\>File...** (or cmd+I) and select **Assets/After Effects/310-UI.psd**. Import it as a "composition." You'll notice that it'll import in as a comp (**310-UI**) as well as a folder ("310-UI Layers") of assets.

What you'll want to do is have each element inside **310-UI** to appear at cascaded times (as opposed to appearing all at the same time). You can do this right inside **310-UI**.

## Masking

After you're done, you'll want to create a pre-comp in the same dimensions as the background slab image (what we've been doing every lesson up until now). You'll want to animate the overall **310-UI** comp by moving it upwards, so that it has the effect of scrolling.

Now, we want to add a mask. It's typically done on the layer/comp that you want to apply to, but because **310-UI** is moving -- and we *don't* want the mask to move -- we'll have to use another method.

Create a shape layer (Layer-\>New-\>Shape Layer), name the layer "Mask," and draw a rectangle around the comp. Rather than having it cut off abruptly, it would be nice if it fades off. So, let's at a 15px *feather* around the mask. You should end up with something like this:

![][image-1]

**Mask** should be above **310-UI** in the layer stack. In **310-UI**, look fofr the TrkMat (track matte), and choose "Alpha Matte 'mask'":

![][image-2]

This will cause it to use the layer above as its own mask. Scrub through your timeline to make sure it's working.

## Your Turn

It's now up to you to get this pre-comp onto Jasper's slab. Should be a piece of cake, given that there's very little movement to the slab (you should just manually track it).

[image-1]:Assets/100-feather.png
[image-2]:Assets/110-alphamatte.png