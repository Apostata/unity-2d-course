# Rotate Method

To rotate the object, select the object in the hierarchy window and click on the rotate tool in the toolbar. You can rotate the object by dragging the mouse in the scene window. You can also rotate the object by changing the value in the transform component in the inspector window.

or

via Script:

```csharp
using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class RotateObject : MonoBehaviour
{
    public float speed = 0.1f; //f is used to denote float value

    // Update is called once per frame
    void Update()
    {
        transform.Rotate(0, 0, speed);
    }
}
```

rotate method requires three values to rotate the object around the x, y, and z-axis. In this script, we are rotating the object around the z-axis.

Attach this script to the object you want to rotate and set the speed value in the inspector window. The object will rotate around the z-axis at the speed you set.

&larr; [Back to Codding](./Coding_unity.md)\
&larr; [Back to Begin](./README.md)