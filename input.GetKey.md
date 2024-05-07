# Input.GetKey

this method is used to get the key that was pressed in the current frame.

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

        groundEffector = GameObject.FindGameObjectWithTag("Ground").GetComponent<SurfaceEffector2D>();
        // groundEffector = FindAnyObjectByType<SurfaceEffector2D>();
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

In this example, the `RotatePlayer` method is called when the player presses the A or D keys. The `BoostPlayer` method is called when the player presses the W or S keys. The player rotates when the A or D keys are pressed, and the player moves faster or slower when the W or S keys are pressed.

&larr; [Back to Codding](./Coding_unity.md)\
&larr; [Back to Begin](./readme.md)