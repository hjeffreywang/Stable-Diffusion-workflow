# Stable-Diffusion-workflow
How to make a multi-layered Controlnet bash
Step 1 - Have Automatic1111
Step 2 - Install the Controlnet Extension from the extensions tab
Step 3 - Controlnet Models (> https://civitai.com/?query=Controlnet < I use Havoc's models)
Step 4 - Go to settings in Automatic1111 and set "Multi ControlNet: Max models" to at least 3
Step 5 - Restart Automatic1111
Step 6 - Take an image you want to use as a template and put it into Img2Img
Step 7 - Enable controlnet in it's dropdown, set the pre-process and model to the same (Open Pose, Depth, Normal Map). You can either do all three at the same time or one at a time (I recommend this personally) and run each one

Step 8 - Ok this is the important part; so for each generation you're gonna ignore the image itself, and take the open pose/depth/normal image outputs and save them. These are what we need for Txt2Img

Step 9 - Now go to Txt2Img and this time set "Preprocessing" to "None" (we don't need it to make new ones) and then set each dropdown (Pose -> Depth -> Normal Map). Could we have just used the original image in each of these? YES! (In theory), however each controlnet model adds to memory usage and yada yada, this basically gives us an easy template that we saved and can use whenever and also don't need to be generated from scratch. This is probably the best option for time optimization

Step 10 - Make sure the image size is set to the same you used for Img2Img and if using Hi-Res Fix. remember that this still uses extra memory, so you may have to lower the number depending.

That's pretty much it.I'll be uploading more results and the final edits on my AI art Twitter if you want to see more> https://twitter.com/ArtrifactsFX <






Openpose is the one i use the lowest to be honest because of the "mirror" front/back pose i can get in the output and also the head/eyes points tends to add more heads depending how close you're from the subject. which is only working good with full bodies or half bodies. If only they added a "point eraser" into open pose editor i would use it more (without relying to Photoshop to do it myself) a big lack of the extension. But for charturnerv2 from civitai, it's extremely good for what you explained at 40's minutes of your video about reference sheets and sourcing concept.

Depth is really good for background and space awareness of prompts. I tends to use it more for backgrounds instead of characters because from my understanding of it, it's more: white is in front, black is in back, instead of white is what we see, and black is what we don't see. I would say it's more like bump map instead. Very good for outputing a wood crate texture with something coming out of it with ControlNet or a detailed landscape with depth map to follow what's near and what's far.

Normal is what i want to ask you about. Is it worth for an example creating normal maps for adding details to the skin ? like veins, scars, skin details (because almost all of the time the skin is too flat and glossy), or will it generate a completely different output with those details ?

Segmentation is what i wasn't understanding but you explained it very well ! Compositing with it is amazing because without prompts it knows what should be seen on the picture. I didn't knew it was color code related. I will use it a lot from now on ! I think this could be more detailed like color codes for each parts of a subject (like open pose works) because we could correct errors more easily that way if not handling with openpose in multi-ControlNet.
