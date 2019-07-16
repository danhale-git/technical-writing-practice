## Introduction to vectors
A _vector_ is a collection of numbers used to describe a length and/or a direction.

In game development vectors store 2 or 3 numbers and are used to describe things in 2D or 3D space, such as position and direction. They can also describe changes in position and direction i.e. movement. Movement is important for game development as almost all games involve moving entities.

It is useful to think of a vector as two sets of coordinates, where one set is all 0s (the _origin_) and the other set is the vector numbers (the _point_). The vector is the line between the origin and the point.

[Image showing how a vector can describe length and direction, emphasis on there being two points, one of which is 0,0]

- The length of the vector is the distance between the origin and the point.
- The direction of the vector is the direction from the origin to the point. 

### Axis
Unity uses 3 axis, X, Y and Z. The numbers in vectors usually relate to these axis.

Positive numbers (e.g. 10) refer to right, up and forward and negative numbers (e.g. -10) refer to left, down and back. You can see how a Vector3 describes these six directions in the Static Properties [here](https://docs.unity3d.com/ScriptReference/Vector3.html).

|Axis Name|Axis Color|Positive number|Negative number|
|---------|----------|---------------|---------------|
|X|Red|Right|Left|
|Y|Green|Up|Down|
|Z|Blue|Forward|Back|

In Unity we commonly work with 2D and 3D vectors using the Vector2 and Vector3 classes. These store collections of 2 or 3 numbers and also provide helper functions for operating on vectors such as Vector3.Angle().

- [Vector3](https://docs.unity3d.com/ScriptReference/Vector3.html) stores 3 numbers, referring to the x, y and z axis. Able to describe things in 3 dimentions.

- [Vector2](https://docs.unity3d.com/ScriptReference/Vector2.html) stores 2 numbers, referring to any two of the three axis. Able to describe things in 2 dimentions.

### Using vectors
Length and direction can describe a number of things. Most common are position, movement, speed and direction. Speed is not usually stored as a vector variable as only one number is required to describe it. But it is calculated using a vector, by determining the vector's _length_.

#### Position
This vector has been used to describe a position. This is an **offset from the coordinates 0,0**.

[Image showing a 2D game character in a graph, with a vector position of 1,2]

#### Movement
This vector has been used to describe a change in position. This is an **offset from the position vector**.

[Image showing the character in a new position of 2,3 and the vector 1,1 describing the difference]

#### Speed
By describing movement, we also describe speed. Speed is calculated using **_length_ of the movement vector** otherwise known as _magnitude_. The Vector2 and Vector3 classed have a convenience property called magnitude that returns the length of the vector. If the movement vector is applied to a game object once per second, that object's speed is the length of that vector per second.

[Image showing the movement vector and highlighting the length as speed]

#### Direction
The movement vector also described a direction. The length of a direction vector is irrelevant because changes in the length of a vector do not change it's direction. For this reason we usually _normalise_ a  vector before using it as a direction. All normalised vectors have a length of 1. Failing to normalise a vector which describes a direction can cause unexpected results when performing certain operations on it.

[Image showing the movement vector normalised emphasising direction]

