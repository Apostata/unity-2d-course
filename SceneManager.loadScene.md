# SceneManager.loadScene

This method is used to load a scene by its name or index. It can be used to load a new scene or to reload the current scene.

Here is an example of how to use the `loadScene` method to load a scene by its name:

```csharp
using System.Collections;
using System.Collections.Generic;
using UnityEngine;
using UnityEngine.SceneManagement;

public class FinishingLine : MonoBehaviour
{
    Collider2D finishLine;

    void Start() {
        finishLine = GetComponent<BoxCollider2D>();
    }
   void OnTriggerEnter2D(Collider2D other) {        
    bool isPlayer = other.CompareTag("Player");
    CircleCollider2D playerHead = other.GetComponent<CircleCollider2D>();
    bool isColidding = playerHead.IsTouching(finishLine);

        if(isPlayer && isColidding){
            Debug.Log("Player has reached the finish line!");
            SceneManager.LoadScene(0); // Load the scene with the index 0
        }
    }
}
```

In this example, the `loadScene` method is used to load the scene with the index `0` when the player reaches the finish line. The `loadScene` method can also be used to load a scene by its name, like this:

```csharp
...
SceneManager.LoadScene("Level2"); // Load the scene with the name "Level2"
...
```

&larr; [Back to Codding](./Coding_unity.md)\
&larr; [Back to Begin](./readme.md)