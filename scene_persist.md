# Scene Persist

In unity, when you change the scene, the objects in the scene are destroyed. But sometimes you want to keep track of some objects across scenes. For example, you might want to keep track of the enemies distroyed by the player, the coins picked up by the player.

here is a simple example of how you can keep track of the objects across scenes.

```csharp
using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class ScenePersist : MonoBehaviour
{
   void Awake()
   {
       
       int scenePersistLength = FindObjectsOfType<ScenePersist>().Length;
        
        if(scenePersistLength > 1)
        {
            ResetScenePersist();
        }
        else
        {
            DontDestroyOnLoad(gameObject);
        }
   }

   public void ResetScenePersist()
   {
       Destroy(gameObject);
   }
}

```	

In this example, the `ScenePersist` class is used to keep track of the objects across scenes. The `Awake` method checks if there is more than one `ScenePersist` object in the scene. If there is more than one `ScenePersist` object, the `ResetScenePersist` method is called to destroy the extra `ScenePersist` object. If there is only one `ScenePersist` object, the `DontDestroyOnLoad` method is called to keep the `ScenePersist` object across scenes.

**If you don't want that eliminated enemies reapear when you die, put the enemies as children of the ScenePersist object.**
&larr; [Back to Begin](./readme.md)