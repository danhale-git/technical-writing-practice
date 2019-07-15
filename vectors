## Introduction to vectors

A _vector_ is a collection of numbers that defines a length and/or a direction.

In game development, vectors can be used to describe things like position and direction. They can also be used to describe changes in position and direction i.e. movement. Position, direction and movement are important for game development as almost all games involve moving entities.

[Image showing how a vector can describe length and direction, emphasis on there being two points, one of which is 0,0]

#### Axis
Unity uses 3 axis, X, Y and Z. 2D and 3D vectors represent either 2 or 3 of these axis.

X: Right/left.
Y: Up/down.
Z: Forward/back.

Positive numbers (e.g. 10) refer to right, up and forward and negative numbers (e.g. -10) refer to left, down and back. You can see how a Vector3 describes these six directions in the Static Properties [here](https://docs.unity3d.com/ScriptReference/Vector3.html).

In Unity we commonly work with 2D and 3D vectors using the Vector2 and Vector3 classes. These store the collections of numbers and provide helper functions for operating on them, such as Vector3.Angle().

#### Unity API

##### Vector3
Stores 3 numbers, referring to the x, y and z.

##### Vector2
Stores 2 numbers, referring to any two of the three axis.
**Important Note:** Vector2 is commonly used with the X and Y world axis and it's 2 number variables are called _x_ and _y_. But you can use Vector2.y to store a number relating to the Z world axis. In this case, your vector would describe something from a top-down view in a 3D world, where only horizontal position and direction matters.

#### Using vectors

Length and direction can describe a number of things.

##### Position
This vector describes a position. This is an **offset from the coordinates 0,0**.
[Image showing a 2D game character in a graph, with a vector position of 1,2]

##### Movement
This vector describes a change in position. This is an **offset from the position vector**.
[Image showing the character in a new position of 2,3 and the vector 1,1 describing the difference]

##### Speed
By describing movement, we also describe speed. Speed is the **_length_ of the movement vector**. If you make the change in position of 1,1 every second, the character's speed would be that vector's magnitude per second. The Vector2 class has a convenience property called magnitude that returns the length of the vector.
[Image showing the movement vector and highlighting the length as speed]

##### Direction
The movement vector also described a direction. The length of direction vectors is irrelevant. For this reason we usually _normalise_ the vector. All normalised vectors have a length of 1. Failing to normalise a vector which describes a direction can cause unexpected results when processing the direction.
[Image showing the movement vector normalised emphasising direction]

