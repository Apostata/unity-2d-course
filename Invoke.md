# Invoke

This method is used to call a method after a certain amount of time has passed. It is useful for creating a delay in the execution of a method.

```csharp

using System.Collections;
using System.Collections.Generic;
using UnityEngine;
using UnityEngine.SceneManagement;

public class CrashDetector : MonoBehaviour
{   
    Collider2D playerHead;
    [SerializeField] float timeToReload = 0.5f; // 1
    [SerializeField] ParticleSystem crashEffect;
    void Start() {
        playerHead = GetComponent<CircleCollider2D>();
    }

    void OnCollisionEnter2D(UnityEngine.Collision2D other)
    {
        EdgeCollider2D ground = other.gameObject.GetComponent<EdgeCollider2D>();
        bool isColidding = playerHead.IsTouching(ground); 
        bool isTheGround = other.gameObject.CompareTag("Ground");

        if(isTheGround && isColidding){
            crashEffect.Play();
            Invoke("ReloadScene", timeToReload);
        }
    }

    void ReloadScene(){
        SceneManager.LoadScene(0);
    }
}

```

In this example, the `ReloadScene` method is called after `timeToReload` seconds have passed. This is useful for creating a delay in the execution of the method.

&larr; [Back to Codding](./Coding_unity.md)\
&larr; [Back to Begin](./readme.md)