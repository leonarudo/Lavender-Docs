# Viewing the Dialogue Database

To patch a conversation, we first need to see how it is setup in the existing game data.  This page will guide you through how to do this:

# Extracting the database JSON

1. Install Unity Asset Studio and open the game's folder with it.
  > Google is your friend here, I found v0.16.47 to work sufficiently
3. On the Asset List tab, search for Dialogue Database (space is required).
4. Click on the one that is NOT inside of a container
	- In the file explorer dialog that pops up, *make sure* to navigate to and select the folder Obenseuer/Obenseuer_Data/Managed
	- If you fail this step, you need to close/reopen the asset studio
5. Open the Export menu at the top and select "Selected Assets"
	- Select somewhere to save the file, and shortly a folder view should open
	- Check that the file was exported as a .json
	- If you have problems with this, you may need to go to the Options menu, expand out the Unity Version submenu and enter 2021.3.45f1

# Actually reading the dialogue database
Now that we have the dialogue database, it's time to look at some tools that will help with reading it.  It's a hard ask to understand the dialogue directly from the JSON (though technically doable).

## Installing the dialogue system editor
1. Go to https://www.pixelcrushers.com/dialogue-system/evaluation-version/ and download the evaluation version.
2. Install Unity Hub, and from there install Unity 2021 LTS (2021.3.45f1).
	- This *is* a different Unity version than Obenseuer is built on, but there's no evaluation version of the dialogue editor for OS's version
3. Setup a new project (2D template without code is fine)
4. Go to the Assets menu at the top and navigate to Import Package > Custom Package...
5. Find the Pixel Crushers Dialogue system file you downloaded before and import that.
6. Provided everything goes well, you should now be seeing a window having popped up: "Dialogue System for Unity" with a bunch of buttons and checkboxes

## Importing your dialogue database .JSON
1. Open the Tools menu at the top of the Unity editor and navigate to Tools > Pixel Crushers > Dialogue System > Import > JSON
2. Click the ... on the Source File field to navigate to the "Dialogue Database.json" file that you extracted from the game files earlier
3. Set the Database Filename to something reasonable, like "OS Dialogue Database" and Import it
4. You won't get any sort of confirmation or alert when it finishes successfully.  When you are able to interact with the editor again, assume it finished.
5. Go ahead and open the new asset
6. At the top, make sure to select the "Conversations" tab.  From here, you can select which conversation to inspect from the dropdown.
  > There's a lot of outdated/incorrect stuff in here.  DO NOT take this to be a source of truth or spoilers.  It isn't.


## Tips for using the dialogue editor and understanding what's going on

YOU DO NOT EDIT DIALOGUE HERE.  In order to edit dialogue for the game in a mod, you need to use the ConversationPatcher class.  It's not as friendly or easy as using this UI, but it's what we have.
<br>

On the right side of the editor, make sure you have "Inspector" selected instead of "Welcome".  This way you can actually see properties of the object/field/etc you have clicked on
<br>

The name of the conversation at the top is the name you provide to the patcher.  For example: `Mines/Canteen/Anna Markkanen`.  That space is very important.
<br>

The dialogue nodes are usually jumbled on top of each other at the top left.  You can get them into a more legible layout by:
  1. Right click > Arrange Nodes > (your preference, I prefer vertical)
  2. Right click > Center on START
  > This appears to happen because the node arrangement was refactored by PixelCrushers between OS's version of the DialogueDatabase and the trial version we have access to.
<br>

When inspecting a dialogue node, the "Actor" is the character speaking.  The "Conversant" is who is being spoken to.  Usually this is a back and forth between Player and an NPC.
<br>

Dialogue nodes with a yellow star on them trigger a script that exists somewhere in the scene.  We don't know what this event is, cause we don't have the scene.
<br>

The "Conditions" field on a dialogue node is a condition written in Lua that is run before a response or conversation routing is displayed and/or happens, and is useful to route the conversation.
  > The Condition field needs to fit inside a Lua if statement.  ie: `if <Conditions> then`

The counterpart to that is the "Script" field, which can execute any Lua code block that it contains.
Also, Lua can be embedded inside of the dialogue text itself (this is explained in the ConversationPatcher examples).  This is how, for example, the police conversation displays how much it costs to bribe the officer.
<br>




Some useful things hidden in the Menu dropdown:
* Show Outline / Show Nodes - Let you swap between a list of all conversations (and rename conversations) and the dialogue tree
