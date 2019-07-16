## Introduction to vectors
A _vector_ is a collection of numbers used to describe a length and/or a direction.

In game development vectors store 2 or 3 numbers and are used to describe things in 2D or 3D space, such as position and direction. They can also describe changes in position and direction i.e. movement. Movement is important for game development as almost all games involve moving entities.


It is useful to think of a vector as two sets of coordinates, where one set is all 0s (the _origin_) and the other set is the vector's collection of numbers (the _point_). The vector is the line between the origin and the point. The vector shown below is 2D (has two numbers) and has a value of 3,3.
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


In Unity we commonly work with 2D and 3D vectors using the Vector2 and Vector3 classes. These store collections of 2 or 3 numbers and also provide helper functions for operating on vectors such as [Vector3.Angle()](https://docs.unity3d.com/ScriptReference/Vector3.Angle.html). An Angle() method also exists in the Vector2 class. Most rules, operations and Unity tools work in the same way for 2D and 3D vectors.

- [Vector3](https://docs.unity3d.com/ScriptReference/Vector3.html) stores 3 numbers, referring to the x, y and z axis. Able to describe things in 3 dimensions.

- [Vector2](https://docs.unity3d.com/ScriptReference/Vector2.html) stores 2 numbers, referring to any two of the three axis. Able to describe things in 2 dimensions.

### Using vectors

Mathematical operations can be performed on variables with type Vector2 and Vector3 in the same way as with variables of type float, int or double.


Performing a mathematical operation on two vectors will result in each of the first vector's numbers being operated on individually with the corresponding number from the second vector. The two lines below give the same result.
```
Vector2 sum = vectorA + vectorB;
Vector2 sum = new Vector2(vectorA.x + vectorB.x, vectorA.y + vectorB.y)
```
Performing a mathematical operation on a vector and a single number will result in each of the vector's numbers being operated on individually with the single number. The two lines below give the same result.
```
Vector2 sum = vectorA + 1;
Vector2 sum = new Vector2(vectorA.x + 1, vectorA.y + 1)
```

You can learn more about vector arithmetic [here](https://docs.unity3d.com/Manual/UnderstandingVectorArithmetic.html).


Vector length and direction can be used to describe a number of things. Most common are position, movement, speed and direction. Speed is not usually stored as a vector variable because only one number is required to describe it. But it is calculated using a vector, by determining the vector's _length_.

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
The movement vector also described the direction of movement. The length of a direction vector is irrelevant because changes in the length of a vector do not change it's direction. We usually _normalize_ a  vector before using it as a direction. Normalizing a vector shortens it's length to 1 without changing it's direction. Vector2 and Vector3 have a convenience property called [normalized](https://docs.unity3d.com/ScriptReference/Vector2-normalized.html) which returns the vector with it's length reduced to 1.
<p align="center">
<img src="https://imgur.com/W9s5O5f.png">
</p>
<p align="center">
On the left is a vector of 1,1, with a length of roughly 1.4. The vector on the right has been normalized (reduced to a length or magnitude of 1). The vector is now roughly 0.7,0.7. Notice it still points in the same direction.
</p>

It's important to normalize a vector before using it as a direction. This is because certain operations you might use with a direction vector will have different results based on the length. Failing to normalize vectors before using them as directions may cause unexpected results where you have multiple direction vectors with different lengths. 

