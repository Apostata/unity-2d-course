# OnTriggerEnter

To detect collisions between GameObjects, you can create a script that uses the `OnTriggerEnter` method. This method is called when a GameObject enters a trigger volume, which is a special type of collider that is used to detect when GameObjects pass through a specific area in the scene.

Here is an example of a script that uses the `OnTriggerEnter` method to detect collisions between two GameObjects:

```csharp

using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class Trigger : MonoBehaviour
{
    void OnTriggerEnter(Collider other) {
        Debug.Log("Trigger with " + other.gameObject.name);
    }
}

```

&larr; [Back to Codding](./Coding_unity.md)\
&larr; [Back to Colliders and Rigid Bodies](./colliders_rigdbody.md)\
&larr; [Back to Begin](./readme.md)