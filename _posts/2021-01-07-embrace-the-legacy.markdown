---
layout: post
title: "Embrace the legacy"
date: 2021-01-07 20:29:33 +0100
categories: programming
---
Legacy code. Sooner or later, you encounter the beast. I wish someone told me from the start how to deal with it, instead of wasting all that time against it... This post is an opinionated attempt to share my thoughts; maybe it will spare some of yours.

Originally defined as *code that relates to no-longer supported system or technology*, legacy code is generally understood as *code inherited from someone else*. Some go further in saying it is *code we are afraid to change*, like the almighty Michael Feathers who simply defines it as *code without tests*.

**Whichever the definition, legacy code is code we're reluctant to work with.**

![Legacy code can't be hard](/assets/img/legacy-code-comic.gif){:class="img-responsive"}

# Accept the legacy

*"Hey, Junior! We got marvelous projects for you, you gonna have so much fun coding with us!*

Well, that was before you first met the legacy code you eventually got to maintain. Your curriculum did not prepare you for this and you fall into despair as you discover how twisted was its creator's mind. [(For his defense, he's usually not the only one to blame.)][say-no]

Some people choose to fight. They force their logic because they think they know better. They rewrite entire modules at night. They only long for the purrrrrrfect code.

Don't be like that. It is a lost cause and, surprise, **the perfect code doesn't exist**. Accepting that is a big step in your early career (and life? :P).

![Nobody's per- Mmm, pizza](/assets/img/perfect-pizza.png){:class="img-responsive"}

# Respect the legacy

Some legacy code is old. It means it lived in production for a long, long time. Therefore the chances are high it is much more robust than your fresh and shiny project you love to create from scratch.

What about its business value? As you discover its abyssal age with horror, just consider what it provided for so long for the users. No matter how ugly or dirty it is, its [ROI][roi-wikipedia] can be huuuge!

You have to respect legacy code, because it usually bears an empirical value which is not to be neglected.

# Embrace the legacy

**Coding becomes much more enjoyable once you accepted to embrace legacy code.**
Maintain its value, monitor its debt, play with it. Protect your critical use cases with [approval tests][approval-tests]. Cover your refactoring with unit tests. Let your craft really shine!

Or [let it be][let-it-be], because legacy code just works. Because making real another great idea might be better than wasting your time on an endless or risky refactoring which adds close to nothing. Let's never lose sight of what we work for: the value our code offers to its users.

Happy coding! :)

![Cat coding](/assets/img/cat-coding.gif){:class="img-responsive"}

[say-no]: https://simpleprogrammer.com/developer-workload/
[roi-wikipedia]: https://en.wikipedia.org/wiki/Return_on_investment
[approval-tests]: https://understandlegacycode.com/approval-tests
[let-it-be]: https://www.youtube.com/watch?v=QDYfEBY9NM4