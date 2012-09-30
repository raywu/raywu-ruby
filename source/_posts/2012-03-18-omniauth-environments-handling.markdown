---
layout: post
title: "OmniAuth Environment Handling"
date: 2012-03-18 12:01
comments: true
categories: [ruby, rails, omniauth]
---

OmniAuth is very powerful, and it's dramatically improved after 2.0 came out. I only started to feel more comfortable with its magic after the third time using it.

One thing I didn't do before, was to set separate authentication keys
for development and production environments.

Doing this on the <a href="http://tourious.co/">Tourious</a> app made life so much easier!

<h3>Here are the files</h3>

This is the standard OmniAuth set up on initializer. Instead of passing authentication keys directly, set them to constants.

{% gist 2076187 omniauth.rb %}

Pass the constants with a set of keys from Twitter and Facebook for
development environment:

{% gist 2076187 development.rb %}

Create another set of Twitter and Facebook authentication keys strictly for production:

{% gist 2076187 production.rb %}

<h3> Conclusion </h3>

This way, I can also set different call-back URL on Twitter and Facebook, and never have to touch the settings again.
