### meta-kodi
## V 0.3

## This repository contains supporting material for NEEO-Meta to control Kodi-applications over the network.

## Installation:
Please note: This release is no longer compatible with the version of meta delivered by the author of meta; it requires changes that haven't been implemented in that version.
In-stead, it uses a frozen release of meta that I creTED (named Meta-Plus) to which I added numerous functions. 
See https://github.com/Ton-O/NEEO-Meta-Plus on how to get this "Meta-plus" installed on your system. I advice Meta-Plus to run on a raspberry pi (V4 suggested), but it can also run as a docker container, hell it can even run on the NEEO-brain. Honestly, running on the Brain works, but has a much lowerr perfromance compared to the 2 others.

The version of meta installed this way, is a frozen version, based on the november 2021 release of meta, but will NOT be upgraded if the author of meta releases new versions!
As such, it is strongly adviced to install this driver on a separate meta-installation to not interfere with the excellent version of meta delivered by the author (https://github.com/jac459/meta)
USE THIS DRIVER AND THE REQUIRED META-PLUS AT YOUR OWN RISK! 

Once you have meta-plus installed and upgraded the modules by following the installation described above, you can enjoy the latest KODI-driver on youyr NEEO. Updates to the KODI-driver can be installed inb the normal-way and is describved below. 

# Installation.
The consists of activating the CoreDriver called KODI in .meta.
This is just a matter of goi g ibnto the .meta recipe on your remote or phone with neeo-app, then:
- going to Libary.
- Find KODI in the list and click it
- Select Activate driver
- Go back, select Danger zone then restart meta.
- After one minute, you can add a KODI-device through the NEEO-gui (or the NEEO-app on your phone).

# Discovery
This driver uses autodiscovery of your kodi-devices, so make sure your KODI is started before adding the device.
In the NEEO-Settings, go to devices, then do an add device. Then type KODI as search argument. NEEO will find "Tono .meta2 KODIPLAYER". 
Select this driver, then click "Next". Meta-Plus will search for KODI-instances and display the result. 
Select an instance and assign it to the correct room.  
The following shortcuts are handy, but you can select the ones you like:
Widgets:
-Menu&Back
Buttons:
- Subtitle
- SyncSub
Directories
- TVShows
- MOvies/Moviesets
Switch:
ShowThumbnails

## If you want to make changes to the NEEO-buttons in this driver, you can use the file Kodi-json and activate this via the user activation folder. 

## Supported buttons and functions

This is the third release of Kodi-driver. It contains all you normally need to control a Kodi player, but this release adds browsing
directories on your KODI-instance.  
The second release adds discovery of Kodi devices, so no IP-configuration is required anymore  
The following Buttons are defined and mapped to functions in Node-RED:
- "POWER OFF"; will shutdown the system where Kodi-player is running (itm will actually call the dialog that allows shutdown)
- "VOLUME UP" & "VOLUME DOWN"
- "CURSOR UP", DOWN, LEFT & RIGHT"; navigating the cursor
- "PAGE UP & DOWN"; navigating an entire page
- "CHANNEL UP & DOWN"; same as "PAGE UP & DOWN" (doesn't work, probably doesn't work on mediaplayer)
- "PLAY"; context-aware... while playing: pause and play, otherwise "select"
- "STOP"; stop the current player
- "SYNCSUB"; Opens window for synchronizing the subtitles (start earlier or delay them); back to exit
- "SUBTITLE"; Opens the subtitle-submenu. Allows browsing, downloading, enabling subtitles
- "PAUSE"; pause or play while playing
- "BACK"; exit a submenu or go up one level in a list/window dialog
- "MENU"; context-aware... while playing: activates OSD, otherwise "context menu"
- "SELECT"; general select
- "TVShows"; Future use with directories on the NEEO-remote.
- "Movies"; Future use with directories on the NEEO-remote.
- "Music"; Future use with directories on the NEEO-remote.
- "LANGUAGE" & "AUDIO": These buttons should (not able to test yet) swtich the Audio-language if multiple exist
- "MUTE TOGGLE"; silence the player.

New in this release are 4 directories:
- TVShows:      Directory that opens KODI library and shows all the TVShows that are defined.
- Movies:       Directory that opens KODI library and shows all the Movies that are defined.
- Moviesets:    Directory that opens KODI library and shows all the Movies that are defined within MovieSets.
- Music:        Directory that opens KODI Library for Music. It allows browsing by artist and album, and searching through a smart search method. 
- VideoSources: Directory that opens KODI library for all the VIDEO-sources. 
                Then you can browse each source as a file-explorer. Browsing through directories is currently limited to 7 levels deep because of technical and practical limits.
 
For Movies and TVSHows, a Checkmark is shown if all underlying elements are shown.
Thumbnails are shown when KODI has them defined. Internally, KODI uses the actual video-file to show a thumbnail; currently, they can not be shown in the directory. 
If you feel this annoying, you can switch off thumbnais with the switch "Thumbnails".     


To-Do:
- Fix 7 levels limit
