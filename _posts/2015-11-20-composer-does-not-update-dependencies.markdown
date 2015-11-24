---
layout: post
title: "Composer does not update dependencies"
date: "2015-11-20 13:35"
---
I don't know when or how this exactly happens, but sometimes a working copy can get into a state where `composer update` actually creates output, but ends up with the message

    Nothing to install or update
    Writing lock file

but you know, there is an updated version available.


This can be fixed:

* Create a backup of `composer.lock` and  your `vendor` folder.
* Delete them
* Run `composer install --prefer-dist`
