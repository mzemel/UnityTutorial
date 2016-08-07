# Unity Lightning Talk:

## Ground

`git checkout First`

We have already created a plane object; one without a background (texture).  We can do things like adjust the size in the Inspector tab and give it a background.

The camera and lighting are game objects as well, and we can create additional lighting and adjust the angle and position as needed.  Observe how the shadow changes when we move the lighting source.

Let's add a background from our Assets folder to the object.  Some assets are open-source, others are available for purchase in the Asset store: they can include animations, textures, and prefabricated objects.

## Player

`git checkout Second`

Here we have created a spherical player object.  It is like all other game objects, except that we are going to map our keyboard input to physical forces acting on this game object; this gives us the feel that this object represents the "player".

Physical forces are dictated by a RigidBody component, which is a component that we can add.  This includes things like mass, drag, and gravity -- all of which can be programatically adjusted in C# or JavaScript as the game progresses.

We can link a "script" to the object - one which provides us callbacks upon things like game initialization, on collision, and upon each frame.

Public variables are are accessible in the Unity IDE as well, as well as other objects and components (such as adjusting gravity through the RigidBody API)

After saving a script, it is compiled and errors are displayed in the IDE.

Let's go through adjusting a public variable for the player object: speed.  Also notice how the player will fall off of the ground if you pass the edge.

## Walls

`git checkout Third`

#### Colliders vs. RigidBodies

These walls are colliders without RigidBodies.  This means they can collide with other objects but are not subject to gravitational and other physical forces, such as impact from those collisions.

We would use colliders that are not rigidbodies for scenery; when we want a player to interact with a wall but we are not interested in walls hitting other walls; something that would be programmatically expensive in a game.

As noted earlier, we are given a C# callback when collision is detected, which we will use in the next step in our player's controller script.

There is also such a thing as a "kinematic" RigidBody - one which does not respond to physical forces but relies on programming to dictate its movement.  We will see this in the next step.

Observe how the player object can impact the walls when we run the game.

## Full Game

`open Complete/Roll-A-Ball in Unity3D`

The spinning boxes (pick-ups) are kinematic rigidbodies, so they do not fall down but we can still script things like rotation.

They are also colliders, which gives us a callback when our player object collides with them.  This callback lets us increase the `count` variable on each collision and terminate the game when appropriate.


## Conclusion

Unity is used in applications from video games to medical animations to military, scientific, and other commercial applications.

Can be built for Desktop, Steam, Oculus Rift, mobile, web, and other platforms with minimal changes across build targets.

PokemonGo was written in Unity.

Great resource community on their website and across the web, including reddit.  Other tutorials are available at [https://unity3d.com/learn/tutorials](https://unity3d.com/learn/tutorials)