# Object.CompareTag

This method is used to compare the tag of an object with a string. It returns true if the tag of the object is equal to the string passed as a parameter, and false otherwise.

Here is an example of how to use the `CompareTag` method after passing though a object in a trigger volume:

```csharp
using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class Collision : MonoBehaviour
{

  void OnTriggerEnter2D(Collider2D other) {
    // if is a trigger from a package 
    if(other.CompareTag("Package")) {
      Debug.Log("package collected");
    }
  }
}
```

&larr; [Back to Codding](./Coding_unity.md)\
&larr; [Back to Begin](./README.md)