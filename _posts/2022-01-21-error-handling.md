---
title: Error handling guide
categories: [OOP]
tags: [design,c#]
---

Error handling is tricky. Without discipline, it usually becomes a mix of uncatched exceptions, ugly return codes and abusive logs. Here are some guidelines to keep it right.

> What is error handling?

**Error handling is how we manage special code executions**, whenever the program does not follow its expected path. Sometimes, something wrong happened and we wanna stop everything. Sometimes, it's no big deal and we just wanna keep running. Sometimes, we're inbetween with a special case we don't know how to deal with.

> Got it, I add some null checks and we done?

Not really. Anything can happen during an execution: an external API might be down, a file system blocked, a database timeout reached. You need to **design defensively, always expect the worse**.

> What about return codes to organize all this?

Please don't! **Return codes are a bad pattern**: they don't give the error context and add complexity without real value. Anytime you discover a new error, you're forced to add a new code and handle it specifically. Quite a burden...

> Then what shall I do?

Here is a good practice in my humble opinion:
- A special case is not an error. Use default values and let the code run normally.
- If the error is non-blocking, throw a custom exception and catch it at the right level. Log a warning and resume the execution.
- If the error is blocking, throw a custom exception and catch it at the top. Log an error and exit.
- if the error is unexpected, catch the system exception at the top. Log a fatal and exit.

**Handle errors with custom exceptions and right level catching. Handle special cases with normal code.** This hugely simplifies the error handling in the whole codebase. Less null checks, no complicated return code.

> But exceptions are scary!

An exception basically screams "I got a problem", nothing else. Don't be scared to use them. Just check you catch it properly. **Add exception classes to match business errors.**

> But exceptions are slow!

Performance drops when the count of exceptions is too high, which is a code smell. Prevent this by throwing a single exception or changing your logic. In common cases, exceptions are totally worth the cost.

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
// Exit
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
// Exit
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