## Introduction to vectors

A _vector_ is a collection of numbers that defines a length and/or a direction.

In game development vectors store 2 or 3 numbers and are used to describe things in 2D or 3D space, such as position and direction. They can also be used to describe changes in position and direction i.e. movement. Movement is important for game development as almost all games involve moving entities.

It is useful to think of a vector as two sets of coordinates, where one collection is all 0s. The vector is the line between the 0 coordinates and those described by the vector.

[Image showing how a vector can describe length and direction, emphasis on there being two points, one of which is 0,0]

### Axis
Unity uses 3 axis, X, Y and Z. The numbers in vectors usually relate to these axis.

X: Right/left.
Y: Up/down.
Z: Forward/back.

Positive numbers (e.g. 10) refer to right, up and forward and negative numbers (e.g. -10) refer to left, down and back. You can see how a Vector3 describes these six directions in the Static Properties [here](https://docs.unity3d.com/ScriptReference/Vector3.html).

In Unity we commonly work with 2D and 3D vectors using the Vector2 and Vector3 classes. These store the collections of numbers and also provide helper functions for operating on vectors such as Vector3.Angle().

#### Vector3
Stores 3 numbers, referring to the x, y and z axis. Able to describe things in 3 dimentions.

#### Vector2
Stores 2 numbers, referring to any two of the three axis. Able to describe things in 2 dimentions.

### Using vectors

Length and direction can describe a number of things. Most common are position, movement, speed and direction. Speed is not usually stored as in a vector variable but it is calculated using a vector.

#### Position
This vector describes a position. This is an **offset from the coordinates 0,0**.

[Image showing a 2D game character in a graph, with a vector position of 1,2]

#### Movement
This vector describes a change in position. This is an **offset from the position vector**.

[Image showing the character in a new position of 2,3 and the vector 1,1 describing the difference]

#### Speed
By describing movement, we also describe speed. Speed is the **_length_ of the movement vector** otherwise known as _magnitude_. If you make the change in position of 1,1 every second, the character's speed would be that vector's magnitude per second. The Vector2 class has a convenience property called magnitude that returns the length of the vector.

[Image showing the movement vector and highlighting the length as speed]

#### Direction
The movement vector also described a direction. The length of direction vectors is irrelevant. For this reason we usually _normalise_ a  vector before using it as a direction. All normalised vectors have a length of 1. Failing to normalise a vector which describes a direction can cause unexpected results when processing the direction.

[Image showing the movement vector normalised emphasising direction]

