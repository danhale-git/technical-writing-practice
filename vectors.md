## Introduction to vectors
A _vector_ is a collection of numbers used to describe a length and/or a direction.

In game development vectors store 2 or 3 numbers and are used to describe things in 2D or 3D space, such as position and direction. They can also describe changes in position and direction i.e. movement. Movement is important for game development as almost all games involve moving entities.

It is useful to think of a vector as two sets of coordinates, where one set is all 0s (the _origin_) and the other set is the vector numbers (the _point_). The vector is the line between the origin and the point.

<p align="center">
<img src="https://imgur.com/FMGMopZ.png">
</p>
<p align="center">
2D vector with the value 3,3. The vector is a line stretching from 0,0 to 3,3.
</p>


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
_**TALK ABOUT VECTOR MATHS OPERATIONS AND MENTION THAT THE EXAMPLES BELOW ARE 2D BUT THE SAME RULES APPLY IN 3D**_
Length and direction can describe a number of things. Most common are position, movement, speed and direction. Speed is not usually stored as a vector variable because only one number is required to describe it. But it is calculated using a vector, by determining the vector's _length_.

#### Position
This vector has been used to describe a position. This is an **offset from the coordinates 0,0**.
<p align="center">
<img src="https://imgur.com/9PIFPoS.png">
</p>
<p align="center">
The position vector is 1,2.
</p>

#### Movement
This vector has been used to describe a change in position. This has been **offset from the position vector** by adding the two vectors.
<p align="center">
<img src="https://imgur.com/XgahpiQ.png">
</p>
<p align="center">
The movement vector is 1,1. Movement is applied by adding the movement vector to the position vector. The final position is 2,3.
</p>

#### Speed
By describing movement, we also describe speed. Speed is calculated using **_length_ of the movement vector** otherwise known as _magnitude_. The Vector2 and Vector3 classes have a convenience property called [magnitude](https://docs.unity3d.com/ScriptReference/Vector2-magnitude.html) that returns the length of the vector. If a movement vector is added to a game object's position once per second, the object's speed per second is the length of the movement vector.


#### Direction
The movement vector also described a direction. The length of a direction vector is irrelevant because changes in the length of a vector do not change it's direction. For this reason we usually _normalise_ a  vector before using it as a direction. All normalised vectors have a length of 1. Failing to normalise a vector which describes a direction can cause unexpected results when performing certain operations on it.
<p align="center">
<img src="https://imgur.com/W9s5O5f.png">
</p>
<p align="center">
On the left is a vector of 1,1, with a length of roughly 1.4. The vector on the right has been _normalised_ (reduced to a length or _magnitude_ of 1). The vector is now roughly 0.7,0.7. Notice it still points in the same direction.
</p>

