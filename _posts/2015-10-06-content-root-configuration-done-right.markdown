---
layout: post
title: "PHPStorm: Content root configuration done right"
date: "2015-10-06 13:20"
tags: PHPStorm
---
This is the summary of the [PHPStorm Help Article][0] on configuring folders within a [content root][1].

**Content Root** itself is not a configuration flag but the parent folder of a project. All folder configuration is done inside the content root.

**Sources Root** is the root folder for every namespace of the project.

**Test Sources Root** holds all test code of the content root.

**Ressource Root** allows autocompleting paths (e.g. to images) to the contents inside this folder in other files.

**Excluded** prevents PHPStorm from indexing and searching files inside this folder.

[0]: https://www.jetbrains.com/phpstorm/help/configuring-folders-within-a-content-root.html
[1]: https://www.jetbrains.com/phpstorm/help/content-root.html
