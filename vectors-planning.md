## Planning


##### Scope
A single, small document with a very simple explanation of vectors in the context of Unity and game development.
Possibly appropriate for this [parent page](https://docs.unity3d.com/Manual/VectorCookbook.html).
Should provide readers with the basic information and usage context to read about common vector-related concepts such as magnitude and identify where vectors can be used in their project.

##### Timing
Very fast as I would like to send it to the recruiter today.

##### Process
- Write first draft.
- Review.
- Create required images.
- Write final draft.
- Review.

##### Audience
Complete beginners who do not have past experience with geometry or vectors.

##### Structure
Narrative structure will be appropriate for this document as it's a simple explanation of a general concept.

- Explain what the word _vector_ refers to.
- Talk about vectors and axis in the context of Unity world space. (also give screen space and UI a passing mention?)
- Briefly list things in game development that vectors are used to describe. 
- Describe each listed thing in a little more details with images.

## Team review 1
I reviewed this document briefly with a colleague. - [**changes**](https://github.com/danhale-git/technical-writing-practice/commit/928d23309f13ad9bc0cf32a3c7fe114a9f2d177c)
- Axis plural is Axes
- i.e. used where e.g. should be used in the first paragraph
- The Direction section is confusing as all vectors have a directions and length. Adjusted language to read 'vectors AS directions'.
- Material relating to Unity classes and axes should be in the same section.
- Language prior to the introduction of Vector3 refers to Vector3 assuming the reader is familiar with it.
- Unity Vector2/3 helpers are not only functions but properties too
- Vectors as directions paragraph is a bit repetitive

## Team review 2
I posted the document on my small Unity ECS discord.
- The second line below repeats _usually work with 2D or 3D vectors_ albeit in a slightly different context. The second line should be something like _In Unity the Vector2 and Vector3 classes are commonly used to work with vectors._ (This might also be a good opportunity to give Unity.Mathematics a passing mention)

_In game development we usually work with 2D or 3D vectors (collections of 2 or 3 numbers)._

_In Unity we usually work with 2D and 3D vectors using the Vector2 and Vector3 classes._
- 'helper members' and 'convenience members' are both used. The word 'members' while common may not be suitable for a beginner's document like this. Consider defining the word or replacing it with something non-technical.

## Outstanding issues
- **See Team review 2.**
- Is there a better word than 'things' here? Something generic but not _that_ generic.

_...stores 2 numbers, referring to any two of the three axes. This can describe **things** in 2 dimensions._

- ~The image is not good, need to start again there.~ Done

- Is there a better way to say this than "...direction of the vector is the direction..."?

_The direction of the vector is the direction from the origin to the point._

- ~Position and Movement sections are possibly unclear due to poor quality images and use of the word offset.~ (removed those sections)

- ~Position and Movement sections duplicate the Addition section in _Understanding Vector Arithmetic_.~ (removed those sections)

- Is it appropriate to mention Unity.Mathematics and float2/float3 etc? Should there be a "Unity.Mathematics for UnityEngine.Vector* users" page providing alternatives for the Vector2/3 built in convenience members? This was a challenge I faced when switching to Unity.Mathematics and I no longer use the Vector2/3 classes.

- ~This sentence could be confusing. Perhaps clarify the 'a vector can be converted...'. Might also need further clarification on normalizing vectors before converting them to angles. Maybe just remove it.~ Referred to 'the angle between the directions of two vectors' instead.

_It is not an angle (0º to 360º) but it can be converted to an angle._

- ~'written in Unity' should be 'written in a Unity C# script'~ Done.

- ~Graph image is too large.~ Made it smaller.

- 'Point' still used in the bullets of length and direction in the first section. Should probably use 'coordinates'.
