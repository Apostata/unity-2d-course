# Ridigbody.AddTorque

This method is used to add a torque to a Rigidbody. The torque is a rotational force that causes an object to rotate around its center of mass. The direction of the torque is determined by the sign of the torque value: positive values rotate the object counterclockwise, while negative values rotate the object clockwise.

Here is an example of how to use the `AddTorque` method to add a torque to a Rigidbody:

```csharp
using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class PlayerController : MonoBehaviour
{
    // Start is called before the first frame update
    Rigidbody2D rb2d;
    [SerializeField] float torqueAmount = 1f;

    void Start()
    {
        rb2d = GetComponent<Rigidbody2D>();
    }

    // Update is called once per frame
    void Update()
    {
        if(Input.GetKey(KeyCode.A) || Input.GetKey(KeyCode.LeftArrow)){
            rb2d.AddTorque(torqueAmount);
        }
        else if(Input.GetKey(KeyCode.D) || Input.GetKey(KeyCode.RightArrow)){
            rb2d.AddTorque(-torqueAmount);
        }
    }
}
```

&larr; [Back to Codding](./Coding_unity.md)\
&larr; [Back to Colliders and Rigid Bodies](./physics.md)\
&larr; [Back to Begin](./readme.md)
