# Image Sequence Updater for Blender 2.8+ add-on
Replaces Image Sequence Texture nodes with a Single Image Texture nodes and loads appropriate frame image file on every frame change.
# Install
- Download ZIP file from the https://gumroad.com/products/MVekg/
- don't unpack it!
- Open Blender. From top menu go to -> Edit -> Preferences -> Add-ons -> Install
- Find downloaded ZIP file and click "Install Add-on" button
- After add-on installed check enabling checkbox near its name
# Location
- Shader Editor > UI (N-Panel) > Image Sequence Updater
# Use
Enabling checkbox will:
- create the new Color Mix node with factor 1 for each active output (Image, Alpha) of each Image Sequence Texture in each material in the project
- link Image Sequence node's active outputs to the upper color sockets of the newly created Color Mix nodes
- create single Image Texture node for each Image Sequence Texture
- load image file appropriate to the current Image Sequence Texture node frame for each newly created Image Texture node
- link newly created Image Texture nodes outputs to the bottom sockets of appropriate Color Mix nodes
- reconnect Image Sequence Texture outgoing links to the Color Mix nodes outputs 
- therefore Image Sequence Texture nodes now are replaced with the newly created single Image Texture nodes with appropriate frames
- While checkbox is enabled every time frame changes add-on will load appropriate frame Image to the Image Texture node
- Images that are not used by add-on anymore are being immediately cleared every time frame changes or on add-on disabling

Disabling checkbox will:
- Remove all nodes previously created by add-on and relink Image Sequence nodes outputs back to where they were linked to.
- Remove all loaded images which are not used anymore (files on disc remain untouched).
# Warnings
As this is a kind of hack out of Blender render systems, it may randomly produce crashes and errors.
If you caught some issues please let me know here: https://github.com/sorecords/image_sequence_updater/issues.
Error log is much appreciated. You can get it from the Blender Toggle System Console on Windows and with launching Blender from Terminal on Mac.
