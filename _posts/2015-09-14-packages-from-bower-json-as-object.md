---
layout: post
title: "Retrieve all packages from bower.json as Object in your Gruntfile"
date: 2015-09-14
categories: code grunt
---
To retrieve the dependencies this line is used:

    var deps = Object.keys(grunt.file.readJSON('./bower.json').dependencies);

Now you can use forEach to do something with ``deps``:

    deps.forEach(function (dependency)
    {
        grunt.config(['dust', dependency], {
            options: { ... },
            build:   { ... }
        });
    });

This adds an  entry to ``dust[]`` for every dependency listed.

If you just write `` grunt.config(dependency, { ... } ); `` it will use the dependency name as task name.
