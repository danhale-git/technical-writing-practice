# Introduction to vectors
A _vector_ is a collection of numbers which can describe a position, length and direction.

In game development we usually work with 2D or 3D vectors (collections of 2 or 3 numbers). They can describe positions and changes in position (movement) from a 2D or 3D perspective. Position and movement are important for game development as almost all games involve moving entities.

It is useful to think of a vector as two sets of coordinates on a graph, where one set is all zeros (the _origin_) and the other set is the vector's collection of numbers. The vector is the line between the origin and the vector coordinates. The vector shown below is 2D (has two numbers) and has a value of 3 and 3 or <3, 3>.
<p align="center">
<img src="https://imgur.com/To1RMk8.png">
</p>
<p align="center">
2D vector with the value <3, 3>.
</p>

- The **length** of the vector is the distance between the origin and the point.
It is also known as the _magnitude_.
- The **direction** of the vector is the direction from the origin to the point.
It is possible to calculate the angle (0º to 360º) between the directions of two vectors.

The vector pictured above could be written in a Unity C# script as:
```
var myVector = new Vector2(3, 3);
```

## Vectors in Unity
Unity uses 3 axes: X, Y and Z. The numbers in vectors usually relate to these axes.

Positive numbers (e.g. 10) refer to right, up and forward and negative numbers (e.g. -10) refer to left, down and back. You can see how a 3D vector describes these six directions in the Vector3 Static Properties [here](https://docs.unity3d.com/ScriptReference/Vector3.html).

|Axis Name|Axis Color|Positive number|Negative number|
|---------|----------|---------------|---------------|
|X|Red|Right|Left|
|Y|Green|Up|Down|
|Z|Blue|Forward|Back|

In Unity the Vector2 and Vector3 classes are commonly used to work with vectors. These store collections of 2 and 3 floats (2D and 3D vectors) respectively. They also provide convenience methods and properties for operating on vectors such as [Vector3.Angle()](https://docs.unity3d.com/ScriptReference/Vector3.Angle.html) and [Vector3.magnitude](https://docs.unity3d.com/ScriptReference/Vector3-magnitude.html). These, along with a number of other convenience members, exist in both the Vector2 and Vector3 classes. Most vector related operations and algorithms will either work with both 2D and 3D vectors, or have equivalents for both types.

- [Vector3](https://docs.unity3d.com/ScriptReference/Vector3.html) stores 3 floats and can describe things in 3 dimensions.

- [Vector2](https://docs.unity3d.com/ScriptReference/Vector2.html) stores 2 floats and can describe things in 2 dimensions.

Arithmetic operations can be performed on variables with type Vector2 and type Vector3 in the same way as with variables of type float, int or double. The examples below show addition but this is also applies to other operations such as subtraction, multiplication and division.

Performing an arithmetic operation on a vector and a single number will result in each of the vector's numbers being operated on individually with the single number. The two lines below give the same result.
```
Vector2 sum = vectorA + 1;
Vector2 sum = new Vector2(vectorA.x + 1, vectorA.y + 1)
```
Performing an arithmetic operation on two 2D or two 3D vectors will result in each of the first vector's numbers being operated on individually with the corresponding number from the second vector. The two lines below give the same result.
```
Vector2 sum = vectorA + vectorB;
Vector2 sum = new Vector2(vectorA.x + vectorB.x, vectorA.y + vectorB.y)
```
Such operations cannot be performed implicitly on two vectors of different types (one 2D and one 3D). One of the lines below will result in an error:
```
var vector2D = new Vector2(1, 2);
var vector3D = new Vector3(3, 4, 5);

//  Operating on a Vector2 and a Vector3 like this causes a compile error
Vector2 sum = vector2D + vector3D

//  Operating on the values of each vector individually works
sum.x = vector2D.x + vector3D.x;
sum.y = vector2D.y + vector3D.y;
```
You can learn more about vector arithmetic [here](https://docs.unity3d.com/Manual/UnderstandingVectorArithmetic.html).
