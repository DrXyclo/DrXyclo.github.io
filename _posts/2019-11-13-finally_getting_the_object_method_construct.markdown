---
layout: post
title:      "Finally getting the Object.method Construct"
date:       2019-11-13 17:54:23 +0000
permalink:  finally_getting_the_object_method_construct
---


It feels good when concepts start to click.  It's a taken awhile to understand the object.method construct, object is data, method does something with the data, and returns the modified data.  The concept started to click during the labs in EmailParser.  I was thoroughly confused by the following call:

```
EmailParser.new(arg).method

```
If I create a new instance of class and a method requires an argument and then the argument gets assigned as an attribute as an @instance variable, ALL THIS is an object which then can be further acted upon by a method...WHOA!  clicked!  So to test my thinking I wrote the following class:

```
class Whatever

     def not_initialize(word)
        puts word
     end

end

```
When I tried to call:

```
Whatever.not_initialize("howdy") or not_initalize("howdy")
|--------------method----------|
```
 I get a noMethod error.  Hmmm.  Right, because I'm calling an instance method on an instance of an object that doesn't exist yet, I didn't give the method any data. Ok cool so if my class doesn't have an explicit initialize method I can create the object manually and give the method some data to chew on.

```
Whatever.new.not_initialize("howdy")
|--object---||---method------------|

howdy
#=> nil
```

Nice!  It's so liberating when these concepts click.

Then I started to notice the pattern, esecially in class arrays with many attributes, I realized that I was trying to call parts of that objects data, data within data and call a method on that data.  That helped focus me when writing code, I felt like a just needed to access the right piece of data with the Ruby language and then call the method.  


