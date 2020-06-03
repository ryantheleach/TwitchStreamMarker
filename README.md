# What is this?
This is a simple web page that can be saved locally to your computer, that when configured correctly and used as an OBS source, allows you to use an OBS hotkey to trigger a twitch timeline marker to be created in your stream.

# How do I set it up

## Setting up the marker maker app.
1. Create a new app as a developer on https://dev.twitch.tv/login .
2. Either set up an O-Auth token generator yourself (difficult), or use this one recommended by me: https://twitchapps.com/tokengen/ (Required scope: user:edit:broadcast)
3. Get your twitch User Id
4. Edit the javascript file included, filling in your Client-ID, O-Auth Token and User ID.

## OBS Hotkey & Scene Setup
1. In OBS Create a scene and call it Marker_
2. In Marker_, Create a browser source called Marker1
	Check "Local file" Select "Marker.HTML" 
	Set the file path to the script
	Check "Shutdown source when not visiable"
	Cech "Refresh browser when scene becomes active"
        Click ok

3. In Marker_, Create a browser source called Marker2
	Check "Local file" Select "Marker.HTML" 
	Set the file path to the script
	Check "Shutdown source when not visiable"
	Check "Refresh browser when scene becomes active"
        Click ok

4. Use the eye icon to hide Marker0
5. Place the Marker_ scene on every scene that you want the hotkey to be active on, e.g. all of them.
6. Click on Controls go to settings
7. Click on Hotkeys
8. Scoll to Marker0 and Marker1 in the list
9. Set the hotkey for Marker0 and Marker1 (show and hide) to be the same hotkey.
10. Click apply
11. Click ok

# How it works

Creating a twitch developer app, and using this script, every time the marker maker html file is opened, it will send a command to the Twitch API to create a new Marker using the user_ID and O-Auth credentials that you input into the file.

By setting up the sources and scene, you are using OBS to force-load the app every time the source is hidden or unhidden. The reason why we add the source twice, and hide one, is so that one source is always hidden, waiting to be shown, so it can be force-loaded when it shows. If you only set up 1 source, you will need to press the button twice every time to be sure.

You can use any key that is readily available, but I recommend using the Page Down / Page Up key, as it's unused in most of the games I play, and is the button that cheap powerpoint presentation remotes use, such as the DinoFire Presentation Clicker Ring.
Useful for VR applications and will not interfere with contollers. I.E. Index/Knuckles controlers.

Special thanks to the Twitch dev discord especially @Dist @BarryCarlyon @Marenthyu @foodz who helped me learn how to do this. A special special thanks to @BarryCarlyon who helped me set up the code, and was very patient with me.

Have fun, and be creative.
-Elocin Anagram
