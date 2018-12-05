---
layout: post
title:      "Interesting Array Functionality, New!?"
date:       2018-12-05 16:38:10 +0000
permalink:  interesting_array_functionality_new
---


When tackling the tic tac toe game status lab, I realized that I needed to go back and take a deeper dive into manipulating arrays and leveraging enumerators.  In the Nested Arrays lesson, in the sandbox I started playing with arrays.  In section, Reading and Writing with Nested Arrays, Accessing Data from a Nested Array, the instructions provide the following nested array:

```
nested_students = [
  ["Mike", "Grade 10", "A average"],
  ["Tim", "Grade 10", "C average"],
  ["Monique", "Grade 11", "B average"]
]
```

The instructions were showing how you could assign arrays as variables.  

> 
If you set the return value of calling nested_students[0] equal to a variable, we can then operate on it with further bracket notation:

```
mike = nested_students[0]
mike[0] #=> "Mike"
```


I asked the question, can I automatically name the variable as the 1st element of the array, so if I wanted to assign Mike as the variable to his information, I didn't have to specifically name each array.  I could then setup a enumerator to assign each student info array as their name.  In my 1st unsuccessful attempt I  set:

```
nested_students[0] = nested_students[0][0] 
```
This set Mike's array to the string "Mike", which was a fail.  The new nested_students array returned:

```
["Mike", ["Tim", "Grade 10", "C average"], ["Monique", "Grade 11", "B average"]]
```

I randomly interrogated the array and it returned this:

```
nested_students[0][1]
 => "i"
```
WHOA!

The 1st element, Mike although a string is being interpreted as an array.  The nested_students[0] returns "Mike", nested_students[0][1] returns index 1, the second element of "Mike", an i.  This worked in several other instances.  Cursory research into this string as an array intepretation didn't turn up anything, but the function could already be well known.
