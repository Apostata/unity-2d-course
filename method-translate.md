# Translate Method

To translate the object, select the object in the hierarchy window and click on the move tool in the toolbar. You can move the object by dragging the mouse in the scene window. You can also move the object by changing the value in the transform component in the inspector window.

or

via Script:

```csharp
using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class TranslateObject : MonoBehaviour
{
    public float speed = 0.1f; //f is used to denote float value

    // Update is called once per frame
    void Update()
    {
        transform.Translate(0, speed, 0);
    }
}
```

translate method requires three values to move the object in the x, y, and z-axis. In this script, we are moving the object in the y-axis.

Attach this script to the object you want to translate and set the speed value in the inspector window. The object will move in the direction of the object at the speed you set.

&larr; [Back to Codding](./Coding_unity.md)\
&larr; [Back to Begin](./readme.md)