# Object.Instantiate

This method is used to create a new instance of an object. It will create a new object in the game world and return a reference to the new object.\

To this method, you need to pass the object you want to instantiate as a parameter.\

Here is an example of how to use the `Instantiate` method to create a new instance of an object:

```csharp
using System.Collections;
using System.Collections.Generic;
using System.Threading.Tasks;
using UnityEngine;
using UnityEngine.InputSystem;


public class Player : MonoBehaviour
{

    [SerializeField] GameObject arrow;
    [SerializeField] Transform bow;

    async void OnFire (InputValue value) // occurs when the player presses the fire button, this method is comming from the inoput
    {
        if(wasHitted){ return;}
        bool fired = value.isPressed;
        if(fired){
            Instantiate(arrow, bow.position, transform.rotation);
        }
    }

}
```

The `OnFire` method is called when the player presses the fire button. If the player presses the fire button, the arrow prefab is instantiated at the position of the bow object and with the rotation of the player.

&larr; [Back to shooting](./shooting.md)
&larr; [Back to Codding](./Coding_unity.md)\
&larr; [Back to Begin](./readme.md)