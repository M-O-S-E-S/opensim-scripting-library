Author: Steven Thompson, copyright 2015

DISCLAIMER: 
These instructions assume a beginner level of understanding of the environment. A user will have to make all the scripts in the environment and
paste the text from the scripts on GitHub into the scripts the user just created. 

INSTRUCTIONS: 
Below is the Work Flow for constructing the Destructible Wall and Grenade:
There are a number of primitive objects that you will need to be created in order to fulfill this Work Flow. 
1. Brick
2. Destructible Wall
3. Deleter Button
4. Set Wall Alpha Button 
5. Grenade
6. Grenade Launcher Button

I. Brick
	1) Spawn a box-shaped primitive; this will be used as an individual brick of the destructible wall.
	2) Set the dimensions of the primitive to x = 0.5, y = 0.24, and z = 0.25. 
	   NOTE: These dimension values can be changed but they will also have to be changed in RezBricks.txt on line 23 where brickSize is specified.
	3) Apply the following scripts to this object:
		a. GetExploded.txt
		b. PrimDeleter.txt
	4) Name the primitive 'Brick'
	5) OPTIONAL: Change the texture and color of the brick
		a. Go to the 'Texture' tab when editing the primitive
		b. Find the drop-down that says 'Texture (diffuse)' and change it to 'Bumpiness (normal)'
		c. Click 'Texture' and set it to 'None'
		d. Click on the drop-down labeled 'Bumpiness' and select 'concrete'
	6) Copy the primitive to your inventory

II. Destructible Wall:
	1) Spawn a box-shaped primitive, which will act as your destructible wall.
		a. Use ctrl-B to open 'Build' menu.
		b. Click the box icon.
		c. Move cursor over into environment and click where you want to place the primitive. 
	2) Set the dimensions of the primitive to those desired. 
		a. Note: these dimensions are not so important. This object is a place holder for the bricks to be spawned.  
	3) Make the wall hollow:
		a. Go to the 'Object' tab when editing the object.
		b. Set 'Hollow' to 99.0
	4) Make the object 'Phantom':
		a. Editing the primitive, got to the 'Object' tab
		b. Click the check box next to 'Phantom' 
	5) OPTIONAL: Set the Alpha of the object so that it's partially invisible:
		a. Go to the 'Texture' tab.
		b. Set the 'Transparency' to 50 or to that desired.
		c. NOTE: this just makes it easier to see bricks spawning. The SetWallAlphaButton will change this value when clicked.
	6) Name the primitive something meaningful; I named mine 'DestructibleWall'.
	7) Apply the following scripts to this object:
		a. RezBricks.txt
		b. SetWallAlpha.txt
	8) Place a copy of the 'Brick' primitive in the Destructible Wall's 'Content' tab
	9) Copy the Destructible Wall Primitive to your inventory
	10) Optional: Test by clicking on the wall
	11) IMPORANT NOTE: Make sure the wall isn't clipping through the floor

III. Deleter Button:
	1) Spawn a box-shaped primitive, which will act as a Delete Button in your HUD.
	2) Name the primitive something meaningful; I named mine 'DeleterButton'.
	3) Apply the following script to this object:
		a. DeletePrims_ButtonScript.txt
	4) Take a copy of the Deleter Button primitive.
	5) Apply it to your HUD:
		a. Go into your inventory.
		b. Right click the Deleter Button.
		c. Click 'Attach to HUD' and place where desired.
		d. Ensure that this button location does not interfere with other buttons.

IV. Set Wall Alpha Button:
	1) Spawn a box-shaped primitive, which will act as a Button that changes the wall's alpha in your HUD.
	2) Name the primitive something meaningful; I named mine 'SetWallAlphaButton'.
	3) Apply the following script to this object:
		a. SetWallAlpha_ButtonScript.txt
	4) Take a copy of the Set Wall Alpha Button primitive.
	5) Apply it to your HUD:
		a. Go into your inventory.
		b. Right click the Set Wall Alpha Button.
		c. Click 'Attach to HUD' and place where desired.
		d. Ensure that this button location does not interfere with other buttons.
	
V. Grenade:
	1) Spawn a circle-shaped primitive; it will act as your grenade object
	2) Edit the physical properties of the grenade:
		a. Set the size of the Grenade primitive to be more appropriately sized: try x=0.063, y=0.063, z=0.063; adjust as needed
		b. Go into 'Features' and set the following values:
			i. Gravity = 1.0
			ii. Friction = 0.60
			iii. Density = 1000.0
			iv. Bounciness = 0.50
	3) Apply the following scripts:
		a. GrenadeExploder.txt
	4) Make the Grenade Physical
		a. While editing the primitive, go to the 'Object' tab.
		b. Click the check box next to 'Physical'
	5) Take a copy of this primitive.

VI. Grenade Launcher Button:
	1) Spawn a box-shaped primitive, which will act as a Button that throws a grenade object.
	2) Name the primitive something meaningful; I named mine 'GrenadeLauncher'.
	3) Apply the following to this object:
		a. GrenadeThrower.txt
		b. Grenade (primitive)
	4) Take a copy of the Grenade Launcher Button primitive.
	5) Apply it to your HUD:
		a. Go into your inventory.
		b. Right click the Grenade Launcher Button.
		c. Click 'Attach to HUD' and place where desired.
		d. Ensure that this button location does not intefere with other buttons.

To test that everything works, spawn bricks by clicking the Destructible Wall. Click the Grenade Launcher Button to throw a Grenade at the wall. 
After 4 seconds the Grenade should go off, letting loose some of the Bricks depending on the location of the Grenade during detonation. Once
the Bricks have been spawned, you can use the SetWallAlphaButton to hide the Destructible Wall. Once the Bricks have been exploded, you can use 
the DeleterButton to delete all the Bricks. 
		
DIAGRAM:
For More details about how these primtives and scripts go together, refer to the image, DestructibleWall.jpeg. 