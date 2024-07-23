# Game session

Game session is a class that will manage the game session. It will implement a singleton pattern to make sure that there is only one instance of the game session at a time. The game session will keep track of the player's score, lives, and other game-related information.

## Singleton pattern in Unity

Here is an example of how you can implement the singleton pattern in Unity:

```csharp	
using System;
using System.Collections;
using System.Collections.Generic;
using TMPro;
using UnityEngine;
using UnityEngine.SceneManagement;
using UnityEngine.UI;

public class GameSession : MonoBehaviour
{

    [SerializeField] int playerLives = 3;
    [SerializeField] int playerScore = 0;

    [SerializeField] TextMeshProUGUI playerLivesText;
    [SerializeField] TextMeshProUGUI playerScoreText;
    
   void Awake()
   {
       
       int gameSectionLength = FindObjectsOfType<GameSession>().Length;
        
        if(gameSectionLength > 1)
        {
            Destroy(gameObject);
        }
        else
        {
            
            DontDestroyOnLoad(gameObject);
        }
   }

   void Start()
   {
       DisplayPlayerLives();
       DisplayPlayerScore();
   }

    private void DisplayPlayerScore()
    {
        playerScoreText.text = playerScore.ToString();
    }

    void DisplayPlayerLives()
    {
         playerLivesText.text = playerLives.ToString();
    }

    public void ManagePlayerLives()
   {
       
       if(playerLives > 1)
       {
        TakeLife();
       }
       else
       {
        ResetGameSession();
       }
   }

    public void AddPlayerScore(int score)
    {
        playerScore += score;
        DisplayPlayerScore();
    }

    void TakeLife()
    {
        playerLives--;
        playerScore = 0;
        SceneManager.LoadScene(SceneManager.GetActiveScene().buildIndex);
        DisplayPlayerLives();
        DisplayPlayerScore();
    }

    public void ResetGameSession()
    {
        FindObjectOfType<ScenePersist>().ResetScenePersist();
        SceneManager.LoadScene(0);
        Destroy(gameObject);
    }
}

```

In this example, the `GameSession` class is a singleton class that keeps track of the player's lives and score. The `Awake` method checks if there is already an instance of the `GameSession` class in the scene. If there is, it destroys the new instance. If there isn't, it makes the new instance persistent across scenes. The `Start` method initializes the player's lives and score. The `DisplayPlayerLives` and `DisplayPlayerScore` methods update the UI with the player's lives and score. The `ManagePlayerLives` method checks if the player has any lives left and either takes a life or resets the game session. The `AddPlayerScore` method adds to the player's score. The `TakeLife` method takes a life from the player and resets the player's score. The `ResetGameSession` method resets the game session and destroys the `GameSession` instance.

All the persists through the scenes and the player's score and lives are maintained throughout the game as well the UI is updated with the player's lives and score.

**So UI should be a child of the GameSession object.**

&larr; [Back to Begin](./readme.md)

