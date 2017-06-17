---
title: "Best way to blog (#2)"
layout: post
theme: default
category: building
tags: [blog, learning]
---
I have been looking around for a while for a good blogging solution. I wanted
it to be hassle free to maintain as a service, and simple to use so writing
posts won't become a big burden.

I evaluated a few solutions, mainly based on different hosting configurations
of [Wordpress](https://wordpress.com/), but I found it burdensome to maintain.
For example, some essentials such as where to host or how to back up the site
don't come for free. These obviously need careful consideration, otherwise you
may end up with a blog that is down and all your precious posts are permanently
lost -- too bad! Beyond that, I also found all those wordpress's capabilities
quite distracting to what I wanted for focus on, *which is to write*.

Later on, I came across [gitbub's pages](https://pages.github.com) and I was
immediately delighted! Not only it's free, simple, and to-the-point, but also
as a programmer, I am already familiar with how to make it work.

The upsidee and downsides were immediately clear:

### Upsides:
* It is free with zero maintenance (let it all be someone else's problem `:)`).
* It is easy to author new posts (simply open a text editor and get started).
* The tools and languages are well-known (other than Jekyll which is simple to
setup, I already knew git and markdown).
* Working on drafts is a breeze (with Jekyll's `--drafts` argument you can
preview your posts before publishing).
* It is a good addition to my [github](https://github.com/shkreza/)
repositories `:)`.

### Downsides:
* There is no native support for dynamic pages (Jekyll is inherently static).
* It is hard to enable user comments -- something that can be handy (albeit
        there are apparently ways to solve this, e.g., see
        [here](http://savaslabs.com/2016/04/20/squabble-comments.html)).

So, from my point of view, the decision was easy. My
[blog](http://shkreza.github.io) was up in no time, and I added my [personal
domain](http://blog.shkreza.com) as well. All that is left is to keep up with
publishing regularly -- which I fully plan to do `:)`.

-- shkreza

{% include disclaimer.html %}
{% if jekyll.environment == "production" %}
  {% include google-analytics.html %}
{% endif %}
