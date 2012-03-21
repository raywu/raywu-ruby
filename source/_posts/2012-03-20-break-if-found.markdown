---
layout: post
title: "Break if found"
date: 2012-03-20 22:32
comments: true
categories: ruby
---

Ruby blocks are awesome. I find myself using a lot of enumerables & enumerators.

Not knowing how to break out of a block is a problem I ran into a lot.

In Problem 9 of <a href="http://www.projecteuler.net">Project
Euler</a>, the answer has to satisfy the condition of x^2 + y^2 = c^2.

{% gist 2093533 problem9false.rb %}

This nested block describes the logic needed for the answer.
Printing out 'found' displays the answer in an array. This took a while.

<h3> Using Break </h3>

{% gist 2093533 problem9.rb %}

In this scenario, by setting 'found = false' (line 8), it gives the block a heads up to break out of the loop, when 'found' returns true.

This dramatically reduces the time to run the script.

<h3> Conclusion </h3>

Blocks are awesome; but knowing when to break out of a loop is double awesome.
