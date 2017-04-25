---
layout: post
title: "My blog and why I use Jekyll"
categories:
 - web_programming
date: 2017-01-13
comments: true
disqus_identifier: df3f835a5d59f934
---

So this is my first blog powered by Jekyll. The main reason for using this ecosystem is because this gives me the flexibility to tweak things around. Furthermore, blogging using Jekyll allows easy code snippetting for example consider the example below:

{% highlight ruby %}
def print_hi(name)
  puts "Hi, #{name}"
end
print_hi('Tom')
#=> prints 'Hi, Tom' to STDOUT.
{% endhighlight %}

Above code is Ruby-based code.

{% highlight php %}
<?php
 $variables = explode(array(holy), ',');
 print_r($variables);
?>
{% endhighlight %}

Above code is PHP-based code.

Therefore, you can specify as a parameter of highlight ruby plugin, which language you are using and then it will render the code nicely according to that specific language syntax.

The above notes are purely in md language. However, you can also use html tags (if you know them) to nicely render the contents as you wish. For example,

<h1> This is h1 tag. </h1>

<h2> This is h2 tag. </h2>

You can even customize tags and put it in css to make it work for example:

<blockquote> This is blockquote. </blockquote>

Above tag is '<blockquote>' tag.

In the header, you will see blinking _, this is also achieved through the use of custom tag called blink.

<blink> This text is blinking! </blink>

This is few of the reasons why I would like to use Jekyll. Other than that, it is synchronised well with Github (in fact this site is powered by Github Pages anyway) so I wanted to try this.