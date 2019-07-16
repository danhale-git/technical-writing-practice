# Introduction to vectors
A _vector_ is a collection of numbers used to describe a length and/or a direction.

In game development vectors store 2 or 3 numbers and are used to describe things in 2D or 3D space, such as position and direction. They can also describe changes in position and direction e.g. movement. Movement is important for game development as almost all games involve moving entities.


It is useful to think of a vector as two sets of coordinates, where one set is all zeros (the _origin_) and the other set is the vector's collection of numbers (the _point_). The vector is the line between the origin and the point. The vector shown below is 2D (has two numbers) and has a value of 3 and 3 or x3 y3.
<p align="center">
<img src="https://imgur.com/MkYX0XZ.png">
</p>
<p align="center">
2D vector with the value x3 y3. The vector is a line stretching from x0 y0 to x3 y3.
</p>


- The length of the vector is the distance between the origin and the point.
- The direction of the vector is the direction from the origin to the point. 

## Vectors in Unity
Unity uses 3 axes, X, Y and Z. The numbers in vectors usually relate to these axes.

Positive numbers (e.g. 10) refer to right, up and forward and negative numbers (e.g. -10) refer to left, down and back. You can see how a 3D vector describes these six directions in the Vector3 Static Properties [here](https://docs.unity3d.com/ScriptReference/Vector3.html).

|Axis Name|Axis Color|Positive number|Negative number|
|---------|----------|---------------|---------------|
|X|Red|Right|Left|
|Y|Green|Up|Down|
|Z|Blue|Forward|Back|

In Unity we commonly work with 2D and 3D vectors using the Vector2 and Vector3 classes. These store collections of 2 or 3 numbers and also provide helper members for operating on vectors such as [Vector3.Angle()](https://docs.unity3d.com/ScriptReference/Vector3.Angle.html). An Angle() method also exists in the Vector2 class. Most of the these convenience members exist in both Vector2 and Vector3. Most vector rules and operations work for both 2D and 3D vectors.

- [Vector3](https://docs.unity3d.com/ScriptReference/Vector3.html) stores 3 numbers, referring to the x, y and z axes. This can describe things in 3 dimensions.

- [Vector2](https://docs.unity3d.com/ScriptReference/Vector2.html) stores 2 numbers, referring to any two of the three axes. This can describe things in 2 dimensions.

Mathematical operations can be performed on variables with type Vector2 and type Vector3 in the same way as with variables of type float, int or double.


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

## Using vectors
Vector length and direction can be used to describe a number of things. Most common are position, movement, speed and direction.

### Position
This vector has been used to describe a position. This is an **offset from the coordinates 0,0**.
<p align="center">
<img src="https://imgur.com/oBA7wFc.png">
</p>
<p align="center">
The position vector is x1 y2.
</p>

### Movement
This vector has been used to describe a change in position. This has been **offset from the position vector** by adding the two vectors together.
<p align="center">
<img src="https://imgur.com/a7Sao5A.png">
</p>
<p align="center">
The movement vector is x1 y1. Movement is applied by adding the movement vector to the position vector. The final position is x2 y3.
</p>

### Speed
The movement vector also describes the speed at which the object is moving. Speed is calculated using **_length_ of the movement vector** otherwise known as _magnitude_. The Vector2 and Vector3 classes have a convenience property called [magnitude](https://docs.unity3d.com/ScriptReference/Vector2-magnitude.html) that returns the length of the vector. If a movement vector is added to a game object's position, once per second, the object's speed per second is the length of the movement vector.

### Vectors as directions
The movement vector also describes the direction of movement. When using a vector only to describe a direction, length is irrelevant. This is because changes in the length of a vector do not change its direction. We usually _normalize_ a  vector before using it as a direction. Vector2 and Vector3 have a convenience property called [normalized](https://docs.unity3d.com/ScriptReference/Vector2-normalized.html) which returns the vector with the same direction but reduces its length to 1.
<p align="center">
<img src="https://imgur.com/KPdD5E2.png">
</p>
<p align="center">
On the left is a vector of x1 y1 with a length of roughly 1.4 . The vector on the right has been normalized (reduced to a length or magnitude of 1). The vector is now roughly x0.7 and y0.7 . Notice it still points in the same direction.
</p>

It is important to normalize a vector before using it as a direction. This is because certain operations you might use with a direction vector will have different results depending on the vector's length. Failing to normalize vectors before using them as directions may cause unexpected results where you have multiple direction vectors with different lengths. 

