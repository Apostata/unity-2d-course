# C#

C# is a programming language that is used in unity to create scripts that control the behavior of the game objects.\


## Async Await vs Coroutines

What is the difference between Async Await and Coroutines? 

Async/Await and Coroutines are both techniques used in programming to handle asynchronous operations, but they are used in different contexts and have different behaviors.

Async/Await is a feature of many modern programming languages, including C#, JavaScript, and Python. It's used to write asynchronous code in a more linear, easy-to-read style, similar to traditional synchronous code. When you mark a function as async, you're saying that the function will return a Task that represents the ongoing operation. The await keyword is used to pause the execution of the function until the awaited task completes. This doesn't block the thread; instead, control is returned to the caller of the async function, allowing other work to be done in the meantime.

```csharp
public async Task<string> GetWebPageAsync(string url)
{
    using (var client = new HttpClient())
    {
        string result = await client.GetStringAsync(url);
        return result;
    }
}
```

Coroutines, on the other hand, are a feature of some specific languages and frameworks, like Unity's C# implementation and Python's generators. A Coroutine is a function that can suspend its execution (yield) at certain points, and then continue from where it left off the next time it's called. This can be useful for operations that need to happen over time, like animations or user input in a game.

```csharp
IEnumerator Fade()
{
    for (float ft = 1f; ft >= 0; ft -= 0.1f) 
    {
        Color c = renderer.material.color;
        c.a = ft;
        renderer.material.color = c;
        yield return null;
    }
}
```

In this example, the Fade function will gradually decrease the alpha value of the object's color over time. Each iteration of the loop will happen over multiple frames of the game, because of the yield return null; statement.

In summary, while both Async/Await and Coroutines can be used to handle asynchronous operations, they do so in different ways and are used in different contexts. Async/Await is generally used for IO-bound tasks like network requests or file reads, while Coroutines are often used for time-bound tasks like animations or gradual calculations.