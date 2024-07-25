# C#

C# is a programming language that is used in unity to create scripts that control the behavior of the game objects.\

## Math methods

Math methods are used to perform mathematical operations in C#. Here are some of the most commonly used math methods in C#:

- `Math.Abs()`: Returns the absolute value of a number.
- `Math.Round()`: Rounds a number to the nearest integer or to a specified number of decimal places.
- `Math.Floor()`: Rounds a number down to the nearest integer.
- `Math.Ceiling()`: Rounds a number up to the nearest integer.
- `Math.Min()`: Returns the smaller of two numbers.
- `Math.Max()`: Returns the larger of two numbers.
- `Math.Pow()`: Returns a specified number raised to the specified power.
- `Math.Sqrt()`: Returns the square root of a number.
- `Math.Sin()`: Returns the sine of an angle.
- `Math.Cos()`: Returns the cosine of an angle.
- `Math.Tan()`: Returns the tangent of an angle.
- `Math.PI`: Represents the mathematical constant π.
- `Math.E`: Represents the mathematical constant e.
- `Math.Log()`: Returns the natural logarithm of a number.
- `Math.Log10()`: Returns the base 10 logarithm of a number.
- `Math.Exp()`: Returns e raised to the specified power.
- `Math.Sign()`: Returns the sign of a number (1 if positive, -1 if negative, 0 if zero).
- `Math.Truncate()`: Removes the fractional part of a number.
- `Math.Clamp()`: Clamps a value between a minimum and maximum value.
- `Math.Lerp()`: Linearly interpolates between two values.
- `Math.LerpUnclamped()`: Linearly interpolates between two values without clamping the result.
- `Math.LerpAngle()`: Linearly interpolates between two angles.
- `Math.Deg2Rad()`: Converts degrees to radians.
- `Math.Rad2Deg()`: Converts radians to degrees.
- `Math.Atan2()`: Returns the angle whose tangent is the quotient of two specified numbers.
- `Math.Atan()`: Returns the arctangent of a number.
- `Math.Asin()`: Returns the arcsine of a number.
- `Math.Acos()`: Returns the arccosine of a number.
- `Math.Clamp01()`: Clamps a value between 0 and 1.
- `Math.DeltaAngle()`: Calculates the shortest difference between two angles.
- `Math.MoveTowards()`: Moves a value towards a target value.
- `Math.SmoothStep()`: Interpolates between two values smoothly.
- `Math.Approximately()`: Compares two floating-point numbers for approximate equality.
- `Math.IsPowerOfTwo()`: Determines if a number is a power of two.
- `Math.NextPowerOfTwo()`: Returns the next power of two that is greater than or equal to a specified number.
- `Math.ClosestPowerOfTwo()`: Returns the power of two that is closest to a specified number.
- `Math.IsNaN()`: Determines if a value is not a number (NaN).
- `Math.IsInfinity()`: Determines if a value is positive or negative infinity.
- `Math.IsNegativeInfinity()`: Determines if a value is negative infinity.
- `Math.IsPositiveInfinity()`: Determines if a value is positive infinity.
- `Math.FusedMultiplyAdd()`: Performs a fused multiply-add operation.



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