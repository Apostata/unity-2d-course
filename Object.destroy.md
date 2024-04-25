# Object.Destroy

This method is used to destroy an object. It will remove the object from the game world and free up the memory used by the object.\
To this method, you need to pass the object you want to destroy as a parameter.\
This method can have an optional second parameter that is the time in seconds to wait before destroying the object.\

Here is an example of how to use the `Destroy` method to destroy an object after a collision:

```csharp

using System.Collections;
using System.Collections.Generic;
using UnityEngine;

using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class Collision : MonoBehaviour
{
    void OnCollisionEnter(Collision other) {
        Debug.Log("Collision with " + other.gameObject.name);
         Destroy(other.gameObject, 0.5f); // destroy the object after 0.5 seconds
   }
}

```

&larr; [Back to Codding](./Coding_unity.md)\
&larr; [Back to Begin](./README.md)