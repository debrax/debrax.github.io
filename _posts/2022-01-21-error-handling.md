---
title: Error handling guide
categories: [Design]
tags: [oop,c#]
---

Error handling is tricky. Without discipline, it usually becomes a mix of uncatched exceptions, ugly return codes and abusive logs. Here are some guidelines to keep it right.

> What is error handling?

**Error handling is how we manage special code executions**, whenever the program does not follow its expected path. Sometimes, something wrong happened and we wanna stop it. Sometines, it's no big deal and we wanna keep running.

> Got it, I add some null checks and we done?

Not really. Anything can happen during an execution: an external API might be down, a file system locked, a database timeout reached. You need to **design defensively, always expect the worse**.

> What about return codes to organize all this?

Please don't, **return codes are a bad pattern**: they don't give the error context and add complexity without real value. Besides, it's quite a burden to maintain...

> Then what shall I do?

**Handle errors with custom exceptions, caught at the right level. Process special cases with normal code.**
- If the error is non-blocking, throw a custom exception and catch it at the right level. Log a warning and resume the execution.
- If the error is blocking, throw a custom exception and catch it at the top. Log an error and exit.
- if the error is unexpected, catch the system exception at the top. Log a fatal and exit.
- A special case is not an error. Use default values and let the code run normally.

This hugely simplifies the error handling in the whole codebase. Less null checks, no complicated return code.

> But exceptions are scary!

Exceptions basically scream "I got a problem", nothing else. Don't be scared to use them. Just check you catch them properly. **Add exception classes to match business errors.**

> But exceptions are slow!

Performance drops when the count of exceptions is too high, which is a code smell. Prevent this by throwing a single exception or changing your logic. Exceptions are totally worth the cost when used right.

Hope this can be useful, happy coding!

---

*Unexpected error: top level global catch*
```csharp
try
{
    // Do stuff
}
catch (Exception exception)
{
    _logger.LogCritical(exception);
}
// EXIT
```

*Blocking error: top level custom catch*
```csharp
try
{
    // Do stuff
}
catch (CustomException exception)
{
    _logger.LogError(exception);
}
// EXIT
```

*Non-blocking error: right level custom catch*
```csharp
try
{
    // Do stuff
}
catch (CustomException exception)
{
    _logger.LogWarning(exception);
}
// Do other stuff
```