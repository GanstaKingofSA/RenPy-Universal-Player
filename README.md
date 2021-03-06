# Ren'Py Universal Player (Ren'Py UOST-Player)
[![ko-fi](https://www.ko-fi.com/img/githubbutton_sm.svg)](https://ko-fi.com/K3K22K8SU)

<u>Current Version:</u> [**1.6**](https://github.com/GanstaKingofSA/RenPy-Universal-Player/releases/latest)

Ren'Py-Universal-Player or (Ren'Py UOST-Player) is a enhanced music room for Ren'Py projects that allows users to play tracks outside the game's story along with sideloaded songs. 

## Credits
- Nikso - Original DDLC Music Player Developer
- Sam Kujo#9403 - Original DDLC Music Player Design and Beta Tester
- Staryxz#3613 - Original DDLC Music Player Beta Tester
- Tom Rothamel - Feedback
- RyzekNoavek#0624 - Adjustable Play Bar Code
- khaase (Pixabay) - Refresh Icon (UOST-Player 1.0 - 1.2)
- eugenialcala (Pixabay) - Replay Icon (UOST-Player 1.0 - 1.2)
- raphaelsilva (Pixabay) - Shuffle Icon (UOST-Player 1.0 - 1.2)
- Josy_Dom_Alexis (Pixabay) - Volume Icon (UOST-Player 1.0 - 1.2)
- Google - Noto Sans SC Font (Author/Description Tag) and Icons (UOST-Player 1.3 onwards)
- Ren'Py Discord - Feedback on Ren'Py Universal Player Features
- Weiss Schnee - Support (Weiss :D)

## Features
1. MP3, OGG/OPUS, and WMA Playback from a folder or inside a RPA/APK file.
2. Metadata support for tracks.
3. Music player controls.
4. Dynamic Font Scaling for Titles (some-what).
5. Sorting support.
6. Based off the Ren'Py auto-generated template screen.
7. Music unlock support.
8. RPA/APK Playback and Metadata Support
   > You will need to enable Developer Mode in order to make the metadata of songs in the track RPA folder generate for distribution.
9. Android Support!

## What do I need to run this?
1. A Ren’Py project (new or existing).
2. The recent version of [Ren'Py UOST-Player](https://github.com/GanstaKingofSA/RenPy-Universal-Player/releases).

## How do I install this?

1. Drop all the contents in this ZIP file to your projects' *game* folder.
2.	Open <u>screens.rpy</u> and add this line somewhere after line `291` under the *screen navigation():* block.
   ```py
   textbutton _("Music Room") action [ShowMenu("music_room"), Function(ost.get_music_channel_info), 
                                    Stop('music', fadeout=2.0), Function(ost.refresh_list)]
   ```
3. **(Optional)** Add some music to the <u>track</u> folder.
4. Run your project and enter the Music Room!

## What can I customize in Ren'Py UOST-Player?
Pretty much anything. This is based off the auto-generated Ren'Py template so everything is good for you to use as-is. Just change the settings under <u>music_screen.rpy</u>.

## How do I manually define a song?
<u>manualtracks.rpy</u> has a small template to define songs manually if you need to do so. You have the following options to define these tracks.
```
name | Name of the track
path | File path to the track from the game folder
priority | Priortization of track on the list.
author | Artist of the song
description | Track description, comments, etc.
cover_art | Path to the track's cover art (JPG/PNG Only)
unlocked | Allows a song to be shown to the player or not.
```

## How do I priortize a song or make a song the first one?
Enable the numbered list icon in the music room and set the song priority by a value. 0 is the highest priority you can make a song be while 1, 2, etc. will be prioritzed lower in the list. i.e. 0 > 1 > 2 > ...
> You may also enable this by setting *organizePriority* to True within <u>ost.py</u>.

## How do I make songs locked from the player?
As of now, the way to make a song unlock is by manually defining a song in <u>manualtracks.rpy</u>. You can see a example on how this works in within the RPY file and under the **How do I manually define a song?** section of this Readme.

## How do I add metadata info?
Right-click your song, Select <u>Properties</u>, go to <u>Details</u>, and fill the blank boxes you can.
Alternatively, use [MusicBee](https://www.getmusicbee.com/) or a similar music player, or [MusicBrainz Picard](https://picard.musicbrainz.org/) and find your song.

- For MusicBee: Right-Click your song within the player, select <u>Edit</u> and edit away the info you want, then click <u>Apply</u> then <u>OK</u>.
- For MusicBrainz Picard: Add your song to Picard, select it, right-click the rectangle box that has 3 columns, select <u>Add New Tag</u>, select the tags you want to add like <u>Title</u>, <u>Artist</u>, <u>Comment</u>, <u>Album</u>, etc. There should be a blank box in the box area below, double-click it and edit away the info you want to add, then click <u>Save</u> and press the <u>Save</u> button near <u>Info</u>.

## Why did you do this?
I wanted to expand the original project I made with ([DDLC-OSTPlayer](https://github.com/GanstaKingofSA/DDLC-OSTPlayer)) to everyone else in Ren'Py. Originally made to see RWBY songs play within the Ren'Py engine. (Yang _:P_)
