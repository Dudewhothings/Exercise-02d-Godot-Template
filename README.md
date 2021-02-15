# Exercise-02d-Godot-Template
Exercise for MSCH-C220, 15 February 2021

The purpose of this exercise is to create a template of a Godot project that can be used for future projects.

One of the problems with hosting a Godot project on GitHub is that both platforms assume that projects (or repositories) will be created inside an empty folder. If you clone an empty repository and try to create a Godot project inside it, Godot will complain (since it actually contains the .git folder), and if you create a project in a new folder in Godot, it won't be tracked by git.

We are going to create a (nearly) empty Godot project that you can build from in the future.

First, fork this repository. When that process has completed, make sure that the top of the repository reads [your username]/Exercise-02d-Godot-Template. Edit the LICENSE and replace BL-MSCH-C220-S21 with your full name. Commit your changes.

Then edit .gitignore. Replace its contents with the following:
```
# Godot-specific ignores
.import/
*.import
export.cfg
export_presets.cfg

# Mono-specific ignores
.mono/
data_*/

# General
.DS_Store
.AppleDouble
.LSOverride

# Icon must end with two \r
Icon

# Thumbnails
._*

# Files that might appear in the root of a volume
.DocumentRevisions-V100
.fseventsd
.Spotlight-V100
.TemporaryItems
.Trashes
.VolumeIcon.icns
.com.apple.timemachine.donotpresent

# Directories potentially created on remote AFP share
.AppleDB
.AppleDesktop
Network Trash Folder
Temporary Items
.apdisk

# Windows thumbnail cache files
Thumbs.db
Thumbs.db:encryptable
ehthumbs.db
ehthumbs_vista.db

# Dump file
*.stackdump

# Folder config file
[Dd]esktop.ini

# Recycle Bin used on file shares
$RECYCLE.BIN/

# Windows Installer files
*.cab
*.msi
*.msix
*.msm
*.msp

# Windows shortcuts
*.lnk
```
Commit your changes.

Press the green "Code" button and select "Open in GitHub Desktop". Allow the browser to open (or install) GitHub Desktop. Once GitHub Desktop has loaded, you should see a window labeled "Clone a Repository" asking you for a Local Path on your computer where the project should be copied. Choose a location; make sure the Local Path ends with "Exercise-02d-Godot-Template" and then press the "Clone" button. GitHub Desktop will now download a copy of the repository to the location you indicated.

Open Godot. In the Project Manager, tap the "New Project" button. Type "Template" in the Project Name field, and "Browse" to the folder where you store C220 projects (near your repository, *but not in it*). Create Folder. If your computer project has struggled to this point with running Godot, select OpenGL ES 2.0, otherwise select OpenGL ES 3.0. Then press "Create & Edit".

You will now see an empty Godot project. Before copying it to our repository, let's set up some features we will commonly be using.

First, we will add a global singleton for our projects. Choose the Scripts Workspace. In the Script Editor area, select File->New Script and save it as Global.gd. The resulting script should contain the following:
```
extends Node

func _process(delta):
	if Input.is_action_pressed("quit"):	
		get_tree().quit()
```
(make sure to indent using tabs). Save the changes to the script.

Next, we add inputs to the Input Map. In the Project menu, choose Project Settings, and select the Input Map tab. Near the top of the window is an "Action:" text box with an "Add" button next to it. Add the following inputs to the map (case is important, so make sure these are all lower case):
 * up
 * down
 * left
 * right
 * quit

Map those inputs to w, s, a, d, and escape (respectively).

Finally, in the Scene Node, Create Root Node: 2D Scene. Name the resulting node "Game". Save the scene as Game.tscn.

Quit Godot. Navigate to the Template folder you created. Copy all the files to the Exercise-02d-Godot-Template folder being tracked by GitHub.

In GitHub desktop, you should now see the updated files listed in the left panel. In the bottom of that panel, type a Summary message (something like "Creates the template") and press the "Commit to master" button. On the right side of the top, black panel, you should see a button labeled "Push origin". Press that now.

If you return to and refresh your GitHub repository page, you should now see your updated files with the time when they were changed.

When you see the changes reflected on GitHub, you can remove the Template folder from your computer.

Now edit the README.md file. When you have finished editing, commit your changes, and then turn in the URL of the main repository page (https://github.com/[username]/Exercise-02d-Godot-Template) on Canvas.

The final state of the file should be as follows (replacing my information with yours):
```
# Exercise-02d-Godot-Template
Exercise for MSCH-C220, 15 February 2021

A Godot Project Template, for use in future projects.

## Implementation
Built using Godot 3.2.3
Includes WASD mappings (up, left, down, right) and escape to quit.

## References
None

## Future Development
None

## Created by 
Jason Francis
```
