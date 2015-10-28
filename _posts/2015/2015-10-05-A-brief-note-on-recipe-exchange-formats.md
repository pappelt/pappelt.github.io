---
layout: post
title: "A brief note on recipe exchange formats"
tags:
published: false
---
When starting to work through the list of enhancements for the olymp project i faced the problem how to store recipe information like the ingredients required and all steps to get the meal done. Simply storing plain text or markdown into a text field was not really an option because of the limited possibilities to reuse specific parts of a recipe.

I short visit at Auntie Google brought up a merely overseeable list of approaches to structure a recipe to make it exchangeable.

To name a few

* CookML
* Cookbook XML
* REML
* YumML

Most of them were based on xml, which is a kinda obvious choice in terms of machine readable data representation. Storing XML in a database or parsing it before doing so was also not a real option and so YumML came in quite handy.

As one can guess from the name it is based on YAML, so it is machine readable, could be processed with a kind of validator and it is human readable as well.

Storing YumML data is easy as cake with the symfony/yaml component from Mr. Potencier, as the parser converts YAML into a native PHP Array which itself can be serialized or converted into plain JSON, both can be stored in a database very well.
