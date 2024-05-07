# Object.IsTouching 

This method is used to check if a collider is touching another collider. It returns true if the collider is touching another collider, and false otherwise.

Here is an example of how to use the `IsTouching` method to check if a collider is touching another collider:

```csharp
public class CrashDetector : MonoBehaviour
{   
    Collider2D playerHead;

    void Start() {
        playerHead = GetComponent<CircleCollider2D>();
    }

    void OnCollisionEnter2D(UnityEngine.Collision2D other)
    {
        EdgeCollider2D ground = other.gameObject.GetComponent<EdgeCollider2D>();
        bool isColidding = playerHead.IsTouching(ground); 
        bool isTheGround = other.gameObject.CompareTag("Ground");
        
        if(isTheGround && isColidding){
            Debug.Log("Ouch! The player has crashed!");
        }
    }
}
```

&larr; [Back to Codding](./Coding_unity.md)\
&larr; [Back to Begin](./readme.md)