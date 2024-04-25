# Object.GetComponent

This method is used to get a component of an object. It returns the component of the object that matches the type passed as a parameter.\

Here is an example of how to use the `GetComponent` method to access the `SpriteRenderer` component of an object and change its color:

```csharp
using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class Collision : MonoBehaviour
{
  [SerializeField] Color32 carDefaultColorColor = new Color32(255, 255, 255, 255);
  [SerializeField] Color32 carLoadedColor = new Color32(250, 0, 186, 255);

  SpriteRenderer spriteRenderer;

  void Start() {
    spriteRenderer = GetComponent<SpriteRenderer>();
  }

  void OnTriggerEnter2D(Collider2D other) {
    // if is a trigger from a package 
    if(other.CompareTag("Package")) {
      spriteRenderer.color = carLoadedColor;
    }

    if(other.CompareTag("Customer") && hasPackage) {
      spriteRenderer.color = carDefaultColorColor;
    }
  }
}

```

&larr; [Back to Codding](./Coding_unity.md)\
&larr; [Back to Begin](./README.md)