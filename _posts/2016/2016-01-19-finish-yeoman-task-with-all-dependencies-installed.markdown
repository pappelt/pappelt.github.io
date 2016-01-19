---
layout: post
title: "Finish a Yeoman task with installing all dependencies"
date: "2016-01-19 17:57"
---
[Yeoman][c2838604] is used to scaffold a project to advance the development of your code.

In my case i rely on a predefined set of other npm and bower packages, which are already listed in my generator and when i create a new project with that generator i want to have them installed right away.


Here is the a step for your index.js which enables you to do so:

    installDeps: function () {
      this.installDependencies(
        {
          npm: true,
          bower: true,
          skipInstall: false,
          callback: function() { this.spawnCommand('grunt', ['init'])}.bind(this)
        })
      }

[c2838604]: http://yeoman.io "Yeoman Project Page"
