---
layout: post
title:      "Rspec flaws"
date:       2018-12-18 00:03:30 -0500
permalink:  rspec_flaws
---


A couple of times I've noticed that I've written a program that works perfectly except that it doesn't pass a test.  For example, tic tac toe in Ruby I wrote the following #play:

```
def play(board)
  until over?(board)
  turn(board)
  end
  
  if won?(board)
    puts "Congratulations #{winner(board)}!"
  elsif draw?(board)
  puts "Cat's Game!"
  end
end
```
The game plays perfectly.

One out  of 45 rspec test fails because #play doesn't check for a draw after every #turn.  Ok, but why would you check for a draw after every turn?  A draw could be declared when either there is no way someone could win, which I haven't tried to implement or when the board is truthy for #full?, but falsey for #won? So what's the issue with the if statement above if I'm truthy for #over? I'm truthy for #won? or #draw?.  

If I could I change the rspec test.  But here I am trying to change the program to fit the test.  I'm sure there's an inherent danger changing tests to fit the code; however, in this case I've verified that the game plays perfectly.  Thoughts?

