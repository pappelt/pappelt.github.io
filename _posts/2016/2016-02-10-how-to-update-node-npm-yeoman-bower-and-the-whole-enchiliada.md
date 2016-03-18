---
layout: "post"
title: "How to update Node.js, npm, yeoman, bower and the whole enchiliada"
date: "2016-02-10 15:45"
published: false
---
Recently i ran one of my generators and received a message that i should update bower.
Whilst updating bower itself was straight forward:

    $ npm install -g bower
    $ bower --version
    1.7.7

As it was easy to update bower my next candidate, yeoman, complained about a very outdated version of Node.js.

Node.js can be downloaded as binary, compiled from source or installed via npm and controlled via nvm.
I found [this article][6cef5196] by David Walsh on how to use npm to update Node.js itself - even if that sounds counterintuitive it works.

tl;dr: this updates your local Node.js version to the latest stable release:

    $ sudo npm install -g n
    $ sudo `which n` lts
    $ node -v
    v4.3.0

In a [later article][12fc3190] he describes how to handle different versions of Node.js.

[6cef5196]: https://davidwalsh.name/upgrade-nodejs "update nodejs via npm"
[12fc3190]: https://davidwalsh.name/nvm "manage node versions with nvm"
