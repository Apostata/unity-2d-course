# OnCollisionExit

This method is called when the Collider has stopped touching another Collider. This can be useful for detecting when an object has left a trigger zone or stopped colliding with another object.

```csharp
using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class SnowTrail : MonoBehaviour
{
    // Start is called before the first frame update
    SurfaceEffector2D groundEffector;
    [SerializeField] ParticleSystem snowTrail;

    void Start() {
        groundEffector = FindObjectOfType<SurfaceEffector2D>();
    }
    void OnCollisionEnter2D(Collision2D other)
    {
        
        ParticleSystem.EmissionModule emission = snowTrail.emission;
        float spreadRate;
        if(groundEffector.speed > 15){
            spreadRate = groundEffector.speed * 10;
        }
        else if(groundEffector.speed > 5 && groundEffector.speed <= 15){
            spreadRate = groundEffector.speed;
        }
        else{
            spreadRate = groundEffector.speed * 0.5f;
        }

        emission.rateOverTime = spreadRate;
        snowTrail.Play();
    }

    void OnCollisionExit2D(Collision2D other) {
        snowTrail.Stop();
    }
}
```

In this example, the `OnCollisionExit2D` method is used to stop the `snowTrail` particle system when the object stops colliding with the ground. This is useful for creating a snow trail effect that only appears when the object is touching the ground.

&larr; [Back to Codding](./Coding_unity.md)\
&larr; [Back to Begin](./readme.md)