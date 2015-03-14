---
layout: post
title: rails view debug
category: rails
---

<div class="message">
  <cite> "I would really like to see you..really..." </cite>
</div>

It's fairly easy to debug controllers.  Use you IDE debugger, or PRY, and set your debug. But how about in views, for
example the variables being rendered via ERB or HAML or whatever.

Rails has some helpers you can use:  In particular, <em>debug</em> and <em>to_yaml</em>.   Just go into your view code
and add either(or both of the following)


{% highlight ruby linenos %}
def use debug
<%= debug @article %>
<p>
  <b>Title:</b>
  <%= @article.title %>
</p>

end

def use to_yaml
<%= simple_format @article.to_yaml %>
<p>
  <b>Title:</b>
  <%= @article.title %>
</p>

end

{% endhighlight %}
