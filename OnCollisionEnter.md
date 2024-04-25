# OnCollisionEnter

To detect collisions between GameObjects, you can create a script that uses the `OnCollisionEnter`These methods are called when a GameObject collides with another GameObject or enters a trigger volume, respectively.

there are 2 diferent `OnCollisionEnter` methods:
- `OnCollisionEnter(Collision other)` - This method is called when a GameObject collides with another GameObject.
- `OnCollisionEnter2D(Collision2D other)` - This method is called when a 2D GameObject collides with another 2D GameObject.

Here is an example of a script that uses the `OnCollisionEnter` method to detect collisions between two GameObjects:

```csharp
using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class Collision : MonoBehaviour
{
    void OnCollisionEnter(Collision other) {
        Debug.Log("Collision with " + other.gameObject.name);
   }
}
```
so when the GameObject collides with another GameObject, the `OnCollisionEnter` method will be called and the name of the GameObject that the GameObject collided with will be printed to the console.

&larr; [Back to Codding](./Coding_unity.md)\
&larr; [Back to Colliders and Rigid Bodies](./colliders_rigdbody.md)\
&larr; [Back to Begin](./readme.md)