# Time.deltaTime

`Time.deltaTime` is the time that has passed since the last frame. It is used to make the game frame rate independent. This means that if the game runs at 60 frames per second, the value of `Time.deltaTime` will be 1/60 = 0.0167. If the game runs at 30 frames per second, the value of `Time.deltaTime` will be 1/30 = 0.0333.
In fast computers, the game will run at a higher frame rate and the value of `Time.deltaTime` will be smaller. In slow computers, the game will run at a lower frame rate and the value of `Time.deltaTime` will be higher.

so to make the game frame rate independent, we multiply the speed of the object by Time.deltaTime. This will make the object move at the same speed regardless of the frame rate.

Sample comparison of the frames per and the duration of the frame:


|Computer speed | Frames per second | Duration of frame |
| --- | --- | --- |
| Slow computer | 10 | 0.1s |
| Fast computer | 100 | 0.01s |


so if we have a move unit of `1` \
we need to mantaing the speed of the object to be the same in both cases, so we multiply the speed by `Time.deltaTime`:

|Computer speed | Frames per second | Duration of frame | Distance per second |
| --- | --- | --- | --- |
| Slow computer | 10 | 0.1s | 1 * 10 * 0.1 = 1 |
| Fast computer | 100 | 0.01s | 1 * 100 * 0.01 = 1 |


## Example

```csharp
using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class Move : MonoBehaviour
{
    [SerializeField] float speed = 1;

    // Update is called once per frame
    void Update()
    {
        transform.Translate(0, speed * Time.deltaTime, 0);
    }
}
```

&larr; [Back to Codding](./Coding_unity.md)\
&larr; [Back to Begin](./README.md)