---
layout: post
title: "Embrace the legacy"
date: 2021-01-07 20:29:33 +0100
categories: programming
---
Legacy code. Sooner or later, you encounter the beast. I wish someone told me from the start how to deal with it, instead of wasting so much time against it... This post is an opinionated attempt to share my thoughts, so that you might spare some of yours.

Legacy code was originally defined as *code that relates to no-longer supported system or technology*. It is more generally understood as *code inherited from someone else*. Some go further in saying it is *code we are afraid to change*, like the almighty Michael Feathers who simply defines it as *code without tests*.

**Whichever the definition, legacy code is code we're reluctant to work with**, especially as a junior.

![Legacy code can't be hard](/assets/img/legacy-code-comic.gif){:class="img-responsive"}

# Accept the legacy

*"Hello, Junior. We got marvelous projects for you, you gonna have so much fun coding with us!*

Well, that was before you first met the legacy code you eventually got to maintain. Your programming curriculum has not prepared you for this and you fall into despair as you see your favorite framework flying away...

Some people choose to fight. They force the code because they think they know better. They rewrite entire modules at night. They only long for the perfect code.

Don't be like that. It is a lost cause and, surprise, **the perfect code doesn't exist**. Accepting the imperfection could be the biggest step you can do in your early career (and life?).

![Nobody's per- Mmm, pizza](/assets/img/perfect-pizza.png){:class="img-responsive"}

# Respect the legacy

Legacy code is old. It means it lived in production for a long, long time. Therefore the chances are high it is much more robust than your fresh and shiny projects from scratch you love to create.

What about its business value? As you discover its abyssal age with horror, don't forget what it provided for the users for so long. No matter how ugly or dirty it is, its ROI can be huge!

You have to respect legacy code, because it bears an empirical value. You know, the same that makes your pay higher as you progress in your career.

# Embrace the legacy

**Coding becomes much more enjoyable once you accepted to respect legacy code.**
Play with it: maintain its value, monitor its debt. Protect your critical use cases with snapshot tests. Cover your refactoring with unit tests. Let your craftsman skills shine.

Or [let it be][let-it-be], because legacy code just works. Because you can allocate your time to another great idea instead of wasting your time on an endless or risky refactoring which adds close to nothing. Never lose sight of what you work for: the value your code offers to its users.

Happy coding! :)

[let-it-be]: https://www.youtube.com/watch?v=QDYfEBY9NM4