# Camera.ViewportToWorldPoint

This method takes a `Vector3` in the viewport space (values from 0 to 1) and returns a `Vector3` in world space.

```csharp
using System.Collections;
using System.Collections.Generic;
using UnityEngine;
using UnityEngine.InputSystem;

public class Player : MonoBehaviour
{
    Vector2 rawInput;
    Vector2 minBounds;
    Vector2 maxBounds;
    
    Dictionary<string, float> playerPadding;
    [SerializeField] int paddingBottomForUI = 1;
    [SerializeField] float speed = 5f;
    [SerializeField] float padding = 1f;
    [SerializeField] int paddingTop = 5;


    void Start()
    {
        InitBounds();
        
    }

    void Update()
    {
        MoveShip();
    }

    void InitBounds () {
        Camera cam = Camera.main;
        minBounds = cam.ViewportToWorldPoint(new Vector2(0, 0)); // bottom left
        maxBounds = cam.ViewportToWorldPoint(new Vector2(1, 1)); // top right
        playerPadding = new Dictionary<string, float>
        {
            { "left", minBounds.x + gameObject.transform.localScale.x / 2 },
            { "right", maxBounds.x - gameObject.transform.localScale.x / 2 },
            { "top", maxBounds.y - paddingTop - gameObject.transform.localScale.y / 2 },
            { "bottom", minBounds.y + paddingBottomForUI + gameObject.transform.localScale.y / 2 }
        };
    }

    void MoveShip(){
        Vector3 delta = speed * Time.deltaTime * rawInput;
        Vector3 newPos = new Vector3
        {
            x = Mathf.Clamp(transform.position.x + delta.x, playerPadding["left"], playerPadding["right"]),
            y = Mathf.Clamp(transform.position.y + delta.y,playerPadding["bottom"], playerPadding["top"]),
        };
        transform.position = newPos;
    }

    void OnMove(InputValue value)

    {
        rawInput = value.Get<Vector2>();
    }
}

```

This script moves the player object within the bounds of the camera. The `InitBounds` method calculates the bounds of the camera and sets the padding for the player object. The `MoveShip` method moves the player object within the bounds of the camera. The `OnMove` method gets the input from the player and stores it in the `rawInput` variable. The `rawInput` variable is used to move the player object in the `MoveShip` method.

&larr; [Back to Codding](./Coding_unity.md)\
&larr; [Back to Begin](./readme.md)