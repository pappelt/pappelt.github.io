---
layout: post
title: "How to handle the non-responding Keyboard issue in PHPStorm on Ubuntu"
date: 2015-09-14
categories: PHPStorm
---
Okay, i am in the middle of writing a line of code and suddenly PHPStorm stops accepting any keyboard input.
After a ragequit and a restart i asked auntie Google for help and found out that it might be a problem with IBUS, whatever that may be.

Jetbrains seem to know about this issue, but it is not an issue in the IDE itself, it's *'rather in IBus or possibly in Java X events handling code.'* [Jetbrains issue tracker][].

For me, adding these lines to `bin/phpstorm.sh` solves the problem:

    XMODIFIERS=""
    export XMODIFIERS

Source: [Stackoverflow](http://stackoverflow.com/a/31999270)

[Jetbrains issue tracker] https://youtrack.jetbrains.com/issue/IDEA-78860
