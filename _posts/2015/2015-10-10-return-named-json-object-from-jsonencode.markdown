---
layout: post
title: "return named json object from json_encode"
published: false
date: "2015-10-10 17:42"
---
Whilst ```[{"key":"value"}, {"key":"value"}, ...]``` is totally valid JSON, sometimes you need a 'named' top-level node, because reasons...


Here's how:

  $json = json_encode(array(
     "client" => array(
        "build" => "1.0",
        "name" => "xxxxxx",
        "version" => "1.0"
     ),
     "protocolVersion" => 4,
     "data" => array(
        "distributorId" => "xxxx",
        "distributorPin" => "xxxx",
        "locale" => "en-US"
     )
  ));
