# Object.FindObjectOfType

This method is used to find an object of a specific type in the scene. It returns the object of the specified type if it exists in the scene, and null otherwise.


```csharp
using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class PlayerController : MonoBehaviour
{
    // Start is called before the first frame update
    Rigidbody2D rb2d;
    [SerializeField] float torqueAmount = 1f;
    [SerializeField] float boostSpeed = 25f;
    [SerializeField] float slowSpeed = 5f;
    SurfaceEffector2D groundEffector;
    float speed;
    float baseSpeed;

    void Start()
    {

        // groundEffector = GameObject.FindGameObjectWithTag("Ground").GetComponent<SurfaceEffector2D>();
        groundEffector = FindObjectOfType<SurfaceEffector2D>();
        speed = groundEffector.speed;
        baseSpeed = groundEffector.speed;
        rb2d = GetComponent<Rigidbody2D>();
    }

    void RotatePlayer(){
        if(Input.GetKey(KeyCode.A) || Input.GetKey(KeyCode.LeftArrow)){
            rb2d.AddTorque(torqueAmount * Time.deltaTime * speed);
        }
        else if(Input.GetKey(KeyCode.D) || Input.GetKey(KeyCode.RightArrow)){
            rb2d.AddTorque(-torqueAmount * Time.deltaTime * speed);
        }
    }

    void BoostPlayer(){
        if(Input.GetKey(KeyCode.W) || Input.GetKey(KeyCode.UpArrow)){
            groundEffector.speed = boostSpeed;
        }
        else if(Input.GetKey(KeyCode.S) || Input.GetKey(KeyCode.DownArrow)){
            groundEffector.speed = slowSpeed;
        }
        else{
            groundEffector.speed = baseSpeed;
        }    
        
    }

    void Update()
    {
        RotatePlayer();
        BoostPlayer();
    }
}
    
```

In this example, the `FindObjectOfType` method is used to find the `SurfaceEffector2D` object in the scene. The `SurfaceEffector2D` object is used to control the speed of the player. The `RotatePlayer` method rotates the player based on the input keys, and the `BoostPlayer` method changes the speed of the player based on the input keys.

&larr; [Back to Codding](./Coding_unity.md)\
&larr; [Back to Begin](./readme.md)