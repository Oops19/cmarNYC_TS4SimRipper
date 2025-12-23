# TS4 SimRipper Classic: rip sims from savegames. V3.14.2.0, updated 4/19/2023

## Additional Information
* This is a fork from MTS. 
* Original description by [CmarNYC](https://modthesims.info/member.php?u=3216596) who retired on earth and is now supporting the TS4 development in heaven.
* Builds by andrew can be found here: [GitHub](https://github.com/CmarNYC-Tools/TS4SimRipper)

### Requirements:
* s4pi: https://github.com/s4ptacle/Sims4Tools
* .NET 4.5, 64-bit Windows
* t.b.d.

### Other forks on GitHub:
* https://github.com/technificentConsulting/TS4-SimRipper
* https://github.com/LynnSpyre/TS4-SimRipper


## Description

I am again maintaining this tool here on MTS as TS4 SimRipper Classic, currently version 3.14.2. PLEASE REPORT ALL PROBLEMS, WITH SUPPORTING ERRORS, FILES, ETC. HERE, NOT ON DISCORD.

SimRipper on Discord will be maintained and improved by thepancake1 when he's able to do so.

SimRipper version 4 and up on Github: (V4 has NOT been updated for the latest patches and should not be used at this time.)

--- Tool description ---
This is a tool to read TS4 save files, list the sims, and create a mesh of the sim with all the appropriate morphs applied, hopefully duplicating the appearance of the sim in the game. The mesh can then be saved in a choice of mesh formats. The composited diffuse and specular textures are also saved. Optionally a composited bumpmap and emissionmap can be saved, but these are experimental and may not be useful.

Meshes exported as Collada DAE can be imported into Blender (or other 3D editors that support DAE) with rig and bone assignments.

To use: Extract the tool folder from the attached zip and run TS4SimRipper.exe. Select a save file, then click on any of the sim's names which appear on the left. After several seconds the sim should appear and you can use the outfit dropdown to change outfits and the save buttons to save the sim in the current outfit.

WHEN ASKING FOR HELP WITH A PROBLEM, PLEASE UPLOAD THE SIM TROUBLESHOOTING INFO, PICTURES, ERROR MESSAGES, AND LOG FILES IF APPROPRIATE. IF THE SIM WON'T DISPLAY, REMOVE ALL CC AND MODS. IF IT STILL WON'T DISPLAY, UPLOAD YOUR SAVED GAME AND THE SIMBUILDERLOG.TXT FILE YOU SHOULD FIND IN THE SIMRIPPER FOLDER. IF IT DOES DISPLAY, UPLOAD THE SIM TROUBLESHOOTING INFO zip FILE AND OPTIONALLY THE LOG FILE.

WE CAN ALL SAVE TIME AND ANNOYANCE IF I DON'T HAVE TO ASK EVERY TIME.

Requirements: .NET 4.5, 64-bit Windows. No Mac and no plans to support Mac, sorry.

* Please note that with custom content and default replacements supported, if you're using adult skins and meshes they may show up.

Tutorial on the basics of using these meshes in Blender, including importing textures and animations and transferring normals: http://www.modthesims.info/showthread.php?t=639931

Known problems/limitations:
- Some, maybe all, big dogs may have distortion in the meshes.
- Animations for big dogs look like they were made for a much larger animal and there's distortion of the head. Animations for little dogs and cats are fine. No idea why.
- Pet collars and clothing do not (yet) compress fluffy fur and will disappear into the fur on floofy pets.
- When loading toddlers or children, you may get errors saying one or more physique morphs (heavy/muscle/thin/bony) was not found. As far as I can tell this is normal and caused by some of the body morphs not being implemented for children/toddlers.
- The edges of hair meshes may be slightly visible, especially in Blender. This may be a normals problem.
- Some skin details and makeup don't show up as visibly as they should.
- Cleaning DAE meshes seems not to be working very well.

A note about error messages:
- Error messages saying it can't find presets, sim modifiers, BGEOs, DMaps, or BoneDeltas may or may not mean anything. In most cases it's caused by a custom preset or slider you used to have but have removed. The preset/slider reference may still be in the sim's data.
- Error messages saying it can't find a LRLE texture may or may not mean anything. Because of the workarounds used for CC makeup and skins the 'LRLE' texture may actually be an RLE.
- If the sim looks right, don't worry about the messages.

Please note the Collada DAE format will import into Blender with all skeleton and joint assignments intact. Unfortunately their importer will not keep the original normals. IMO in most cases that probably won't make a significant difference but the people who may use these meshes in Blender will have to determine that. Possibly they can export in both DAE and OBJ and transfer data in Blender.

Texturing and alpha transparency:
- Starting in version 2.3, textures are linked into DAE meshes and will be loaded automatically as long as the textures are in the same folder as the DAE. All you should have to do is change the Viewport Shading (next to the Mode selection) to Material.
- To make transparency work and to adjust shine:
-- If alpha hairs or other meshes that use alpha transparency aren't displaying correctly: After importing the DAE, expand the rig and select any mesh, click the Texture icon in the properties under the objects listing, select the first texture, scroll down to the Influence section, and under Diffuse put a check next to Alpha.
-- To adjust shine intensity: select a mesh and click on the Texture icon as above, then select the second texture (which should be the specular) scroll down to the Influence section, and under Specular change the Intensity number. Higher numbers = more shine.

Pictures include sims in SimRipper and in Milkshape. I'm hopeless in Blender but have managed to do a couple of screenshots.

If you're reporting a problem, please, please don't just say 'It doesn't work'. I need to see error messages, a description of the problem, pictures if possible, whether it's happening with all sims or certain sims. If you have an error message saying the tool can't read something, please post a screenshot of the message or the text. You can blur or edit any file paths that contain personal information. Please only include the first 10 lines or so in comments.

As of version 3.3, you can click the "Sim Troubleshooting Info" button and save a zip including the information and error listings and the CC resources the sim is using. Please upload this zip with your report of a problem, it'll save everyone a lot of time. PLEASE INCLUDE IT WHEN YOU POST SO I DON'T HAVE TO ASK.

As of version 3.13.2, if the program crashes or gets an error that prevents the sim from appearing, please upload SimBuilderLog.txt which you should find in the SimRipper folder. Do not use the program again before making a copy of SimBuilderLog.txt or uploading it; loading another sim will create a new log file. AGAIN, PLEASE INCLUDE IT WHEN YOU POST SO I DON'T HAVE TO ASK.




Image and package handling is done with s4pi: https://github.com/s4ptacle/Sims4Tools

#### 4/19/2023, Version 3.14.2.0:
- Did a workaround to get SimRipper working again after the patch of 4/18/2023.

Notes: EA has a new version of the DeformerMap which does most of the human sim morphs. So far it's only updated the frame modifiers that convert male clothing to female frame and vice versa. The new version seems substantially different. SimRipper is using the older version of these morphs at least for now.
Known bug: breast size on male clothing used on females is not working.

#### 3/15/2023, Version 3.14.1.0:
- Added support for infants. Finding the infant skin definition textures is taking a while, so for now I'm using the toddler skin definitions. From the one infant texture I've found so far, they appear to be practically identical to toddler skin anyway.
- Finally fixed the distortions in hind legs and occasionally necks seen in some dogs and cats. This was caused by badly made EA pet DMap morphs.

#### 3/3/2023, Version 3.14.0.0:
- Fixed a problem with replacement heads not categorized as heads not having seams matched with the body.
- Improved pet and werewolf pelt blending so fur shading isn't so washed out. Very light colors still lose some detail but I think this is the best I can do.
- Updated to use the correct werewolf fur shading textures instead of one I picked randomly.
- Added mannequins. (Needs more testing.)
- Added the ability to export a Sim Information/Sim Outfit resource from the currently displayed sim, for future use.


#### 2/21/2023, Version 3.13.6.0:
- Added slot adjustments to make animation easier.
- Added correction for duplicate presets.
- Fixed bug caused by extra uv maps.
- Fixed bug caused by links to region maps that don't exist.
- Fixed bug causing necklaces not to morph.
- Fixed major bug causing pets not to work.
- Fixed bug causing meshes with vertices very close together to be distorted.

#### 10/7/2022, Version 3.13.5.0:
- Fixed bug causing facial hair and probably some hairs and face accessories to not morph correctly and not fit smoothly to the head mesh.
- Will now give a meaningful error message if the log file can't be created, and continue to work without logging instead of crashing.
- Added a startup message so you know the tool is starting and not dead.

#### 9/14/2022, Version 3.13.4.0:
- Updated with a long-awaited fix for the floating eyelashes problem: items near the face did not morph properly when using an accessory replacement head.

#### 8/23/2022, Version 3.13.3.0:
- Updated to handle the case of custom meshes using custom rigs that are not in the user Mods folder, resulting in DAE meshes not being correctly rigged. Please note that vertices with bone assignments to bones not in the current rig will be reassigned and may not animate correctly.
- Fixed bug causing the loading of several outfits for the same sim to sometimes result in increasing facial deformity.
- Fixed bug causing distortion between the thighs in some combinations of thigh morphs.

#### 8/15/2022, Version 3.13.2.0:
- Updated to support teen acne.
- Updated to support DLC content.
- Added logging.
- Fixed bug causing skin color to appear on alpha hair under some conditions.
Log files will now be written in the SimRipper folder you run the tool from. If the program crashes or you get a system error, please save SimBuilderLog.txt and upload it when reporting the problem. Do not run SimRipper again before saving or uploading the log file, it will be overwritten the next time you load a sim.

#### 7/13/2022, Version 3.13.1.0:
- Fixed bug causing most CC clothing and accessories to not appear.

#### 7/12/2022, Version 3.13.0.0:
- Now supports werewolves.
-- Some female clothing is distorted in the werewolf form. It's distorted in the game too so I'm not going to worry about it too much.
- Pets are working again.
- Some speed improvements.

#### 2/23/2022, Version 3.12.1.0:
- Updated to support certain Wedding Stories items.

#### 2/16/2022, Version 3.12.0.0:
- Updated for the new version of CASP, only to have a working version posted here.

#### 1/21/2022, Version 3.11.0.0:
- The older skin blend some people wanted back has been added as an option, called 'Original'.
- You can now separately save the complete composited texture/specular, the 'glass' texture/specular, the skin texture alone, composited makeup texture/specular, composited clothing texture/specular, composited normal map (optionally converted to the RGB format used by many/most tools), and composited emission map.
- Normal maps and emission maps (if any) are now always generated.
- Made shadows more subtle to better duplicate appearance in-game.
- Fixed seam gaps at the ankles in children in some clothing.
- Fixed skin definition textures with facial lines and shadows being smoothed over.
- Fixed bug causing animals to error out.
- Fixed normal maps not being resized correctly before compositing.

#### 12/5/2021, Version 3.10.0.0:
- Overhauled treatment of the combination of a female top with a male bottom, to eliminate gaps at the waist under some circumstances.
- Overhauled the Sim Troubleshooting Info:
--- Now only saves the CC resources actually used instead of whole CC packages, drastically reducing the size of the zip in most cases.
--- Now includes the save game.
--- Now includes resources from expansion/stuff/etc. packs for testing purposes since I may not have the packs you're using.
- Fixed a bug causing some resources to not be readable under some circumstances.
- Error messages concerning failure to open or read packages are now more detailed.

Please note that you must upload a Sim Troubleshooting zip for EACH outfit you're reporting a problem with.

#### 9/20/2021, Version 3.9.1.0:
- Added support for fingernails and toenails.
- Added options for alternate sort orders of skin details. If one's not working, try the others.
- Added buttons to save skin textures and clothing/makeup/hair/accessory textures separately.
- Added sorting of sims by first name and household as well as last name.
- Tweaked the texture sort order to include ordering by composition method.
- Restricted the sim troubleshooting info to the current outfit.

#### 8/15/2021, Version 3.8.2.0:
- Another fix for skin detail overlays. This may be the best I can do in this area.

#### 7/21/2021, Version 3.8.1.0:
- Fixes the issue of clothing textures appearing transparent in older save games, putting your poor sim in a skin suit.

#### 6/17/2021, Version 3.8.0.0:
- Changed the order in which skin detail overlays are applied to fix some being hidden by others. If you still have disappearing overlays, please upload an example package.
- Will now read custom CAS modifier tuning, supporting enabling and tweaking of morphs.
- Added support for skin and makeup sliders.
- Added options for skin blending.
- Changed the preview to an orthographic camera.
Notes:
- SimRipper does not have the same limits as the game on what the color sliders can be used on, so if hue, saturation, brightness, and/or opacity have adjustment values in the save game those adjustments will be shown.
- Since I've never been happy with the skintone blending, I've added additional methods that you can choose. "Blend" is the old method which is almost unchanged. "HSV" retains color better with mid-tone skins but looks terrible with light skin. With "HSL" medium and light skins may look sallow or slightly bluish. Very dark skin looks almost the same in all three but may vary a little in brightness. There's also an option of whether to apply the overlaid "Colorize" color - with most skins this will make little or no difference.
- Using an orthographic camera instead of a perspective one should eliminate perspective distortion making noses, ears, etc. appear too big, and duplicate the view in CAS a little better.

#### 5/11/2021, Version 3.7.0.0:
- Will now skip unreadable packages instead of crashing.
- Will now skip invalid bone assignments when converting to Collada DAE.
- Fixed glitches at hairline with some alpha hairs.
- Fixed very short hair disappearing when used with a hat.
- Fixed some CC with nonstandard vertex paint not morphing correctly.
- Added support for painted pet coats.
- Known problems:
---Textures not saving on some systems. Try saving them in another location.
---Alpha hair and eyelashes may not render correctly. I believe this is a rendering problem in Windows WPF and Blender since they show up correctly in Milkshape and look different in WPF vs Blender.

#### 2/26/2021, Version 3.6.0.0:
- Fixed skins showing up bluish gray after the 2/25 patch.
- Changed how images are saved in hopes of fixing the GDI+ errors some users are getting.
- Fixed bug causing children and toddlers to appear pregnant if loaded after a pregnant adult.

#### 1/16/2021, Version 3.5.0.0:
- Fixed layer order of face sculpt textures causing cheek and forehead sculpts to layer default or blank definition over the other features.

#### 1/13/2021, Version 3.4.2.0:
- Fixed bug causing default replacement skin definitions to not show up.

#### 1/10/2021, Version 3.4.1.0:
- Fixed bug causing some sims in HQ to look like monsters from hell and others to be missing makeup items like eyebrows.

#### 1/6/2021, Version 3.4.0.0:
- Now supports the December patch.
- Added support for the LRLE image type. MAC makeup and all skin definitions should show up correctly.
- Updated the Sim Troubleshooting Info to include only the current outfit.
- PLEASE NOTE: MAKEUP AND SKIN SLIDERS ARE NOT YET SUPPORTED. You'll get the makeup/skin color but without any slider adjustments.

#### 11/18/2020, Version 3.3.0.0:
- Added a button to "Save Sim Troubleshooting Info". This will let you save a zip file with the information and error listings and copies of all the CC packages used by the sim. You can then upload the zip to your comment reporting the problem.

#### 11/17/2020, Version 3.2.0.0:
- Update to support new version of savegame data.
- Toddler eyebrows and other makeup textures along with the eye colors added in a patch are now included along with skin definition files. Most toddlers should show up correctly.

#### 10/20/2020, Version 3.1.0.0:
- Bugfix for sims with alpha hair and no other alpha parts failing to save as solid and glass meshes and textures.
- Diffuse textures now blended with premultiplication to avoid blending artifacts on some parts.
- The preview will now reflect the different saving options, which handle the skin texture a little differently. This will make no difference in the majority of cases but sometimes may give you a more accurate idea of how it will look in Blender or other tools.

#### 10/14/2020, Version 3.0.0.0:
- Lots of fixes for the Oct. 6 patch. This update has not been fully tested but I wanted to get something out there that's at least mostly working. Please report problems.
- Added option to save as solid and glass meshes and textures, like in older versions.
- Added option to save DAE meshes without linked textures.

#### 8/30/2020, Version 2.3.3.2:
- Fixed bug causing textures to not save to some folders.

#### 8/23/2020, Version 2.3.2:
- Fixed bug causing overlays to not appear. They still may be fainter than you expect.
- Bone morphs will no longer crash on faces with a zero length side.
- Fixed unevenness in long dresses and skirts with some morphs.
- Increased the precision of bone morph calculations. Much to my surprise, .NET uses different mechanisms for floating point arithmetic in 32-bit vs 64-bit, which apparently is why the MS3D meshes had the arms at the wrong angle in 64-bit but not in 32-bit. Using double precision has fixed that and may help with small rig errors a couple of people have reported.

#### 8/18/2020, Version 2.3:
- Added HQ texture support.
- Textures are now linked into DAE meshes. Import the DAE and change the Viewport Shading to Material and you should see the model with diffuse and specular textures. See instructions above under "Texturing and alpha transparency".
- Some alpha hairs or accessories may not display correctly using the main diffuse texture if they've been uv-mapped onto face or body areas. In that case you can save a 'glass' texture which has no skin texture background and import it for your alpha mesh that's not looking right.
- Optionally meshes can be saved as one mesh or as multiple mesh parts, one for each part of the sim: head, hair, body, accessories, etc.
-- Separate mesh parts will show visible seams between parts because Blender doesn't import the normals correctly. You may be able to correct this by importing an obj of the same model and transferring normals as explained in the tutorial above.
-- Having "Clean DAE Mesh" checked and saving as a single mesh will in most cases give you a mesh with no visible seams.
- Fix for null reference exceptions affecting occult sims, possibly due to a change in the EA save game format.
- Various fixes.

#### 7/26/2020, Version 2.2.2:
- Fix for new version of the CASP introduced in the Knitting patch.
- You can now select different bone sizes in Blender. A setting of 9 gives you pretty visible bones.
- This is an interim update to get the CASPs working again. Still working on separate part meshes, HQ support, and various fixes.

#### 6/4/2020, Version 2.2.1:
- The June 3, 2020 patch seems to have changed the way makeup textures are compressed, resulting in eyecolor, eyebrows, lipstick etc. not appearing. This is an interim update which uses older versions of those textures. Any new makeup that came with the June 3 patch will not show up correctly.

#### 5/31/2020, Version 2.2.0: (Yes, I messed up the version number.)
- Bone morphs are reworked to hopefully be more accurate in extreme morphs and scaling.
- The creation and save speed for Collada .DAE meshes is substantially improved.
- Uses a better folder browser for choosing paths in the setup.
- *known bug* Milkshape meshes have an error in the rig causing the arm bones to be positioned wrong. Collada DAE meshes seem to be fine.

#### 2/26/20, Version 2.0.2:
- Failure to correctly read CASModifier tuning in countries that use a comma as a decimal marker has been fixed. This caused the modifiers not to be read, and is likely the cause of crashing when trying to load a sim.

#### 2/23/20, Version 2.0:
- There are now three file paths that can be modified in Setup if needed: The path to the game files, the full path to the Mods folder, and the full path to the Saves folder.
- You can now filter the list of sims in a save game listing by species, gender, and age.
- There is now a button to save textures only.
- A missing Region Map should no longer cause crashing.
- Errors are now logged and can be displayed by clicking the Show Errors button.
- The listing of the sim's information (background info, morphs, CAS parts, etc.) is no longer shown in the tool but can be displayed by clicking the "Show Sim Information Listing" button.
- Duplication of sims' appearance, especially children and toddlers, has been improved by the inclusion of CAS Modifier tuning. (Thanks, Menaceman44!)
- Males in female frame now have flattened breasts when wearing female tops.
- Filling of the waist gap when combining female tops and male bottoms should now work correctly in all clothing.
- A pregnant morph can now be applied to cats and dogs.
- Tans and sunburns are now supported, with or without tan lines. (Tan lines must be created in the game.)
- The correct parts of pants should now be removed when combined with boots.
- I fiddled with the bumpmaps and emission maps, but I can't tell if it's an improvement.

#### 1/23/20, Version 1.9.2:
- Fixed Collada DAE meshes exported on systems with languages that use a comma for decimals not importing the rig into Blender correctly.
- Fixed the teeth texture and made the inner mouth color more realistic.
- Tweaked skin colors a little.

#### 1/15/20, Version 1.9:
- Animations should now work well in Blender.
- CAS parts using the SimGlass shader are now supported. They will be a separate mesh part within the Collada, OBJ, or MS3D file, and their texture will be exported to separate images named as Glass. At this time all glass parts will be combined into one mesh part. This will however affect only transparency hair in most cases.

#### 12/18/19, Version 1.8:
- Bugfixes for locality differences.
- Skin details are now blended according to the composition method.
- Occult states added. Occult sims with an alternate form can now be put into that form.
- Pregnant sims will now have a pregnant morph applied, and a slider for pregnancy progress can make any sim appear pregnant. (Human sims only so far.)
- Improved appearance of light skin colors.

#### 12/6/19, Version 1.7:
- Added more robust handling of errors in reading resources. If a resource can't be read, the tool will now tell you the resource type, tgi, and the package it's in; and ignore it.
- Now uses skintone settings for makeup opacity, so your sims should no longer look like they put blush and eyeshadow on with a trowel. 
