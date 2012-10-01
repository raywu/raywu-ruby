---
layout: post
title: "Hello World!"
date: 2012-03-17 20:38
comments: true
categories: [helloworld, ruby]
---

A few months earlier, I started tackling <a
href="http://www.projecteuler.net">Project Euler</a>. Here is one of the
lessons I learned:

<h3>Avoid Infinite Loops</h3>

Yes, Infinite Loop. I thought I had you pinned to the wall, but I was wrong; I didn't even realize what I got myself into. No, not until my buddy <a href="http://www.github.com/igrabes">Ian Grabill</a> pointed it out.

<h3>Project Euler's #3 problem:</h3> What is the largest prime factor of the number 600851475143 ?
The way I started out with this problem, was to get all the factors for the number in question. My approach was to wrap the number in question into a method as an argument:

``` ruby
def factor(num)
  (2..num).map { |n| yield n if num/n * n == num }
end
```

This seemed straight forward enough. Boom, donzo.
I ran the script to test it out with 40, and factor(40) worked beautifully. Then I tried it withfactor(600,851,475,143); 10 seconds' went by, nothing yet. 120 seconds, nothing still. Next thing I knew, my computer was screeching noises I hadn't ever heard before. Ctrl-C, Ctrl-C, Ctrl-C, abort, abort!!!

What happened?
While 40 spat out 8 numbers that are all divisble to 40, who knows how many of these factors are out there for 600851475143.
So, now what?

``` ruby
def factor(num, limit)
  (1..limit).map do |f|
    num / f
    yield f if num / f * f == num
  end
end
```

After talking to Ian at 2am ET about this ungodly problem of mine, he pointed me to this neat little trick. Ian had discovered that by dividing each number within a range of (1..limit) into the num (in this case 600851475143), would help you find all the factors within a contained range.

For instance, factor(600851475143, 10000) would only look for all the factors of 600851475143 that were within the range of (1..10000). This made my computer happy.

<h3>Conclusion</h3>

Granted, had my MacBook Pro had more computing power, and my memories a gizzillion GBs, I could have just left the script run until it got all the factors for 600851475143.

Okay, okay, IT'S NOT AN INFINITE LOOP. But my point is, if you have an inkling that you will run into this kind of technical problems (Hello Houston!), put a cap on it.

