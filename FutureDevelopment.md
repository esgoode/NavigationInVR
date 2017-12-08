# Future Development

The project employs a method to switch scripts easily called SwitchMovement.cs, a script that allows the user to switch between movements easily by click “A” or “B” and changing the message displayed to the user (the message informing them what movement is selected and that they are able to click “A” or “B” to switch between movements). There are 10 total movements implemented and you are able to cycle through them (the cycle starts over once the end is reached).

All of the movements utilize the left joystick as the main controller.

The following are scripts to change movement behavior:

* Controller.cs: This is a class that enables traditional joystick movement to move the player around with the left thumbstick being used for input. Speed is able to be adjusted for as well as a constant height for the player

* Grappling.cs: This class allows the user to “grapple” to a certain location, using the left controller to point and shoot at the target location and, as the trigger is held down, move towards the desired location in a smoothed motion

* Hoverboard.cs: This class allows the user to navigate using head movements (for direction) and tilting of the controller (for acceleration speed). The left trigger is used to determine activation of the movement (so holding the left trigger and tilting the controller forward will move the player forward). Tilting backwards is also account for and moves the player backward with the angle of tilt determining acceleration. Holding the controller parallel to the ground keeps the player from moving even when the left trigger is pressed.

* Jetpack.cs: This class is similar to hoverboard as it allows users to navigate using head movements (for direction) and tilting of the controller (For acceleration speed) but also causes the user to levitate off the ground and simulate a jetpack. The jetpack begins firing and moves the user off of the ground in the specified direction when the left controller is pressed and begins bringing them back to the ground once it is released. 

* PinchZoom.cs: This class emulates the pinch to zoom feature of touch interfaces and allows users to set their max location with the hand trigger, then hold down the left trigger to zoom in and out of a set location.

* SkiPole.cs: This class uses the triggers on both controllers to trigger movement, using the controllers to pull yourself towards a direction and pulling with both hands for faster movement (similar to using ski poles)

* PlatformMvt.cs: This class allows the user to control a platform with the left joystick while also letting them move around the platform at the same time. 

* Soar_Earth.cs: This class allows the users to zoom out (fly in the air) using the left trigger and then use the joystick to move around the environment

* Teleporter.cs: This class is similar to the grappling hook class in that it allows a user to point at an area and move to that location, however, the movement happens instantly in this case. You can hold down the trigger and point to the target area, releasing the trigger to teleport. 

* SwingingArms.cs: This class allows the user to move in the direction they are facing and swing their arms to start the movement. The direction the arms are swinging has no effect on the direction of movement (only facing direction does).

The following are objects within the scene:

* EventSystem: This GameObject manages the OVRInputModule script to handle and accept Oculus Touch controller input. Allows for the use of OVRInput.*

* OVRCameraRig: The main camera for the given scene. Tracks the VR headset and touch controllers in the scene. 

* OVRCameraRig/TrackingSpace/CenterEyeAnchor: This object holds all of the movement scripts. These include SwitchMovement, Teleporter, Controller, Hoverboard, Grappling, PlatformMvt, SwingingArms, PinchZoom, JetPack, SkiPole, and Soar_Earth. It also contains a Rigidbody so that gravity can be applied for the JetPack script. It is the main location of the camera, so it holds the scripts so that they can check for the orientation of the headset.

* ModeUpdate: Contains all of the UI canvas elements. These include messages and instructions for each movement method and a timer for researching and testing the methods. Used by the SwitchMovement script to update the player as to what movement method they currently have selected.

* Target: A canvas that holds a sprite to denote a target location in a number of the movement methods. These include the Teleporter, GrapplingHook, and PinchZoom scripts. Contains a small script in Target/Canvas called UpdateRotation which keeps the sprite facing toward the player’s camera.

* LineRenderer: Renders a visible line to help the player tell which way their controller is pointing in the Teleporter and GrapplingHook methods. Helps players make more accurate selections on their target locations.

* Platform:  Used in the Platform script. Visualization of a platform for the player to move around on to mitigate motion sickness when moving through an environment.
