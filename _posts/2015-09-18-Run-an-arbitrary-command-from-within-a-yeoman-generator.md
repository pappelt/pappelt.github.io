---
layout: post
title: "Run an arbitrary command from within a yeoman generator"
date: 2015-09-18
categories: code grunt
---
Okay, this is pretty basic, but for documentation purposes: the [Yeoman API][0] states
that ``installDependencies`` can take a callback parameter.

So let's assume you want to precompile something one your generator finished installing all requirements, you can do so with the snippet below:

    installDeps: function () {
      this.installDependencies(
      {
        npm: true,
        bower: true,
        skipInstall: false,
        callback: function() { this.spawnCommand('grunt', ['init'])}.bind(this)
      }
    )};

[0]: http://yeoman.github.io/generator/actions_install.html
