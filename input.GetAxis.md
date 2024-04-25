# input.GetAxis

The `Input.GetAxis()` method is used to get the axis input from the user. The axis input can be from the keyboard, mouse, or any other input device. The axis input is a float value that ranges from -1 to 1. The axis input is used to get the input from the user and perform actions based on the input.

## Syntax

```csharp
using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class Driver : MonoBehaviour
{

    [SerializeField] float steerSpeed = 1;
    [SerializeField] float moveSpeed = 0.01f;

    // Start is called before the first frame update
    void Start()
    {
        transform.Translate(6.19f, 0, 0);
    }

    // Update is called once per frame
    void Update()
    {
        float steerAmount = Input.GetAxis("Horizontal") * steerSpeed;
        float moveAmount = Input.GetAxis("Vertical") * moveSpeed;
        transform.Rotate(0, 0, -steerAmount);
        transform.Translate(0, -moveSpeed, 0);

    }
}
```

So when the user presses the left arrow key, the `steerAmount` will be -1 and when the user presses the right arrow key, the `steerAmount` will be 1. The `steerAmount` is then used to rotate the object around the z-axis.

In the drivers game,  the `steerAmount` is used to rotate the car and the `moveSpeed` is used to move the car forward. But when left or right arrow key is pressed, the car will rotate in the wrong direction. To fix this, we need to set the `steerAmount` to `-steerAmount` so that the car will rotate in the correct direction.

&larr; [Back to Codding](./Coding_unity.md)\
&larr; [Back to Begin](./README.md)