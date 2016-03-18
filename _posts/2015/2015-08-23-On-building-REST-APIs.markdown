---
layout: post
title: "Some thoughts on building a REST API in PHP"
date: "2015-08-23 05:40"
tags: php
---
Using REST APIs on a day to day basis does not automagically make you an export in creating them as well i did a little research work on that topic.

Somewhere in my searchresults i found [DunglasApiBundle][0], which claims to be "The Hypermedia REST API component of API Platform". API Platform itself is a symfony application which aims to ease developing API-first solutions.

After studiyng the Docs for a good amount of time i got a clue about a few things, but i did not wan't to use that instant meal solution because i am doing this thing for personal enjoyment and research.

Lastly, i ended up researching JSON-LD and Hydra to see if and how they would fit into my plans.


Another good resource i had in my results is an article from a guy called [Corey Maynard][1].

He utilizes a .htaccess file to leverage the routing of requests at a very early stage, but i wanted a plain php solution for the backend part, so i decided to use one of the many router scripts that can be found on github.


add some results from that search.


Whilst i was astonished of what pux[2] could do, i ended using Fast-Route[3] because of it's simplicity.


Though i decided to go with another solution when it came to the routing part, this article has other parts i found very good:

* Enable CORS
* Cleaning Input from URLs

Topics covered:
* composer
* Doctrine ORM
* Angular
* PHP-based Routing

[0]: https://api-platform.com/doc/1.0/api-bundle/
[1]: http://coreymaynard.com/blog/creating-a-restful-api-with-php/
[2]: pux
[3]: http://nikic.github.io/2014/02/18/Fast-request-routing-using-regular-expressions
