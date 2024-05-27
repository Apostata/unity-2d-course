# Object.GetComponentsInChildren

This method is used to get all components of this GameObject and its children. It returns an array of components of the object that matches the type passed as a parameter.

```csharp
using System.Collections;
using System.Collections.Generic;
using UnityEngine;
using TMPro;
using Unity.VisualScripting;

public class QuizLogic : MonoBehaviour
{
    [SerializeField] QuestionSO question;
    [SerializeField] TextMeshProUGUI questionText;
    [SerializeField] GameObject answerButtonGroup;
    void Start()
    {
        questionText.text = question.GetQuestion();
        int buttonsLength = answerButtonGroup.transform.childCount;
        for (int i = 0; i < buttonsLength; i++)
        {
            Transform button = answerButtonGroup.transform.GetChild(i);
           button.GetComponentInChildren<TextMeshProUGUI>().text = question.GetAnswer(i);
        }
    }
}

```
In this example, we have a `QuizLogic` class that is responsible for setting the question and answers of a quiz. The `question` variable is a `QuestionSO` scriptable object that contains the question and answers. The `questionText` variable is a `TextMeshProUGUI` component that will display the question. The `answerButtonGroup` variable is a `GameObject` that contains the buttons that will display the answers. In the `Start` method, we set the question text and the answers of the quiz by getting the `TextMeshProUGUI` components of the buttons in the `answerButtonGroup` object.

&larr; [Back to Codding](./Coding_unity.md)\
&larr; [Back to Begin](./readme.md)