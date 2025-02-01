1) DrewZ ReTeX Wiki
Overview
DrewZ ReTeX is a Python/Qt-based tool developed to help DayZ server owners and modders easily retexture clothing, gear, and weapons. It provides a graphical interface to blend custom textures onto existing DayZ template assets, apply text or images, adjust brightness/contrast, generate scripts, and optionally pack everything into a PBO.

This program can speed up the workflow of customizing items for DayZ modded servers. By focusing on a visual approach, you can see precisely how your retexture will look before exporting or converting to .paa format.

Note: You must have an active VIP Tier 2 Patreon Subscription to use DrewZ ReTeX. The Login Panel enforces this requirement upon startup.

Prerequisites and Requirements
DayZ (the game) installed.
DayZ Tools installed (from Steam Library Tools section).
Mounted P:\ Drive using DayZ Tools’ Work Drive Mount (this is critical for modding).
You should also extract the DayZ data to a convenient project folder. Typically, this extracts into:
P:\DZ\Characters (for clothing)
P:\DZ\Weapons (for weapons)
P:\DZ\Gear (for various gear items)
Windows OS (the code references Windows paths for DayZ Tools).
VIP Tier 2 Patreon Subscription (required for the login panel).
If you do not meet all of these prerequisites, you will likely encounter errors or be unable to log in.

Installation & Setup
Obtain the Program

Download DrewZ ReTeX (the .exe or the full bundle) from the official Patreon or Discord channel.
Ensure you place it in a location with read/write permissions (e.g., C:\DayZModding\DrewZ ReTeX\).
Launch & Login

Double-click on DrewZ ReTeX.exe (or main.py if using source code).
A Login Panel will appear.
Enter your credentials (associated with your Tier 2 Patreon subscription).
Upon successful authentication, the main application window will open.
Auto-Detect DayZ Tools

The program attempts to locate DayZ Tools in common directories (C:\Program Files (x86)\Steam\steamapps\common\DayZ Tools, etc.).
If it cannot find DayZ Tools automatically, it will prompt you to manually select the DayZ Tools directory.
Confirm your DayZ Tools path is correct (e.g., E:\Steam\steamapps\common\DayZ Tools).
Mount the P Drive

Open DayZ Tools from your Steam library.
Use the Work Drive utility to mount the P:\ drive.
Extract (unpack) DayZ’s game data to P:\DZ\ or your chosen project directory.
Program Layout & Features
Below is a high-level view of the DrewZ ReTeX interface:

Select Template: Choose your base image (e.g., a blank .png or an extracted in-game texture from P:\DZ\Characters\…).
Select Texture Folder: Choose the folder containing your custom textures (the images you wish to apply to the template).
Scan for Duplicates (optional): Quickly scans your texture folder for duplicated images by hash.
Select Output Folder: Where the final images (blended textures) will be saved.
Logout: Exits the application or returns to the login panel.
Instructions: Opens a separate instructions script/dialog.
Join Discord: Opens the official DrewZ ReTeX support Discord link.
Checkboxes

Convert to .PAA: Whether to convert the final PNGs to .paa format using DayZ Tools.
Generate Scripts: Whether to generate a config.cpp or other mod-related scripts for your retextured items.
Pack into .PBO: Whether to pack your output into a .pbo file for distribution. (Requires the other checkboxes to be enabled.)
Options Button

Opens a dialog to configure in-depth parameters for script generation (e.g., mod name, parent class, hidden selections) and PBO signing.
Blending Mode

A dropdown to choose how your texture is blended with the template: Normal, Multiply, Overlay, Screen, etc.
Template Preview

Displays the loaded template image in a large preview area.
Texture Previews

A horizontal scroll area of thumbnails from your chosen Texture Folder.
Clicking on a thumbnail will select that texture for the preview blend.
Output Images List

Shows the final rendered images (filenames) in the Output Folder.
Selecting an image here updates the main preview with that image.
Selected Output Preview

Large preview of the currently selected output image within a QGraphicsView.
Allows placing text or icons on top of the preview if you want to finalize or brand your texture.
Controls & Buttons

Blend to Template: Applies the currently selected texture to the template and saves it to the output folder.
Convert to .PAA: Visible/active if you check the “Convert to .PAA” option.
Apply to Current Texture & Apply to All Textures:
Specifically for layering text/icons on top of existing blends.
Text Options

Text field, Color button, Add Text: Enter custom text, pick color, and place it onto your image.
Font Options: Choose a custom font from resources/fonts, set the size, update selected text items.
Image/Icon Options

Add Image/Icon: Insert additional graphical elements (e.g., logos) into your preview.
Clear Selected: Remove the currently selected icon or text from the scene.
Brightness/Contrast

Sliders to adjust brightness and contrast of the blended image.
An Apply to All button to apply these adjustments to every output image.

Choose a base .png that matches the layout of a DayZ item (for instance, the extracted UV map or texture from P:\DZ\Characters\…).
Select Texture Folder

Choose the folder containing your custom designs or patterns you want to apply. (e.g., C:\MyTextures\).
Output Folder

Choose where final blended images will be written (e.g., C:\MyModOutput\).
Blend to Template

Select a texture from the thumbnail row.
Click “Blend to Template.” This merges the custom texture onto the base template using the chosen Blending Mode.
The output (by default) is a .png saved in the output folder. It appears in the “Output Images” list.
Repeat or Bulk-Apply

You can apply multiple different textures. Or rename them (using the Base Name field) to keep them organized.
Add Text or Icons (Optional)

In the “Selected Output Preview,” you can place text or images (logos, watermarks, etc.).
Click Apply to Current Texture (for one image) or Apply to All Textures to replicate your text/icons across every output image.
Brightness/Contrast (Optional)

Use the sliders to lighten or darken the new texture or adjust contrast.
If you like your adjustments, you can “Apply Brightness/Contrast to All.”
Convert to .PAA (If Desired)

If you want your final images as .paa (the format DayZ uses), check the “Convert to .PAA” box and then click “Convert to .PAA.”
This leverages ImageToPAA.exe from your DayZ Tools Bin\ImageToPAA directory.
Generate Scripts (If Desired)

Check “Generate Scripts.”
Provide details such as:
Dependent Mod (optional)
Mod Name (for the folder structure)
Parent ClassName (e.g., TShirt_Base)
HiddenSelections (the hiddenSelections used by that base item)
The tool will create a config.cpp referencing your new textures and place it in your mod folder.
Pack into .PBO (If Desired)

With “Pack into .PBO” checked, the program uses a built-in PBO packer to place your mod contents into a .pbo.
Additional details for key signing can be entered in the Options dialog.
After you have your .pbo and your .bikey in the right place, you can upload them to your server.

Key Points for DayZ Modding
Mount P Drive: DayZ modding typically requires the P:\ drive to simulate the game file structure.
Hidden Selections: Many DayZ items use hiddenSelections for retexturing. You must list them properly if generating a config.
Signing & Keys: If you plan on distributing your mod, you should sign your PBO and provide a .bikey so server owners can add it to their keys folder.
Common Troubleshooting
Login Issues

Ensure your Patreon subscription is Tier 2 and active.
Check that your credentials match your Patreon account.
DayZ Tools Not Found

Manually select the directory: Usually C:\Program Files (x86)\Steam\steamapps\common\DayZ Tools.
Confirm you see subfolders like Bin\ImageToPAA.
No Textures Found

Make sure your selected texture folder has .png, .jpg, or .jpeg.
Check that the folder path is correct.
Blending Not Working

Some blending modes require the template and texture both be RGBA. Confirm the images are 32-bit with alpha if you want to preserve transparency.
Convert to .PAA Errors

Confirm ImageToPAA.exe is present in your DayZ Tools Bin\ImageToPAA subfolder.
Some antivirus or Windows permissions might block the tool from running.
Advanced Functions & Code Insights
The project’s Python code includes:

main.py – The primary GUI logic for DrewZ ReTeX:

Login panel enforcement.
UI layout with template preview, texture previews, etc.
Threaded operations for applying textures, converting to PAA, scanning duplicates.
Options dialog for script generation and PBO packing.
Automatic update checks from GitHub.
essentials.py – A set of helper classes and threads:

BlendingHelper handles all blending modes (Normal, Multiply, Screen, Overlay, etc.) and alpha compositing with NumPy/PIL.
ApplyTextureThread runs the bulk texture-application in the background.
ConvertToPAAThread runs the .png → .paa conversions, optional script generation, and optional PBO packing.
ResizableTextItem and ResizableIconItem let you drag, scale, or rotate text/images in the QGraphicsView.
Those wanting to modify or extend DrewZ ReTeX can customize these scripts. However, normal usage does not require code edits.

Conclusion
DrewZ ReTeX provides a comprehensive, visual method to retexture DayZ items quickly. By leveraging a robust blending workflow, script auto-generation, and PBO packing, modders can drastically streamline the process of updating server content.

Enjoy your modding workflow, and remember to maintain an active Tier 2 Patreon subscription for continued access and updates!
