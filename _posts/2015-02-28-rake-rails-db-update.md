---
layout: post
title: rake rails:update
category: upgrading
---

<div class="message">
  <cite> "I just want to test out this railscast...." </cite>
</div>

I am sure you have done this.  You find a railscast about something you are interested in, and besides
watching the vid, you want to run the app.

You download it, and all heck breaks loose due to the rc demo using older versions of just about anything.  Rather than
using RVM or something to create or duplicate the original environment, I prefer just to upgrade it to the most
current thing I am using on my dev machine.  I really don't like loading up old versions of stuff all over
the place.

One issue i ran into..some weird issue about a configuration file.  Differences in configuration can happen with
major upgrades, say going from rails 3.2 to 4.x.

Rails provides a rake rails:update task to update configuration files. Be sure you’ve committed your application with git before running rake rails:update
in case you need to roll back changes.

{% highlight ruby linenos %}
def update_config_files
puts "rake rails:update"
end
{% endhighlight %}

The rake rails:update will identify every configuration file in your application that differs from a new Rails application.
When it detects a conflict, it will offer to overwrite your file.

Don’t blindly allow rake rails:update to overwrite your files. Many of your files will be different because you’ve made changes from a default new Rails application.
You’ll need to check each file to determine if rake rails:update is seeing your own changes or pointing out changes due to a Rails update.

When rake rails:update offers to overwrite a file, enter d (for “diff”) and review the differences.
Most differences will be your own. If you’re uncertain, don’t overwrite the file; make a note for yourself and investigate later.
If you are certain that the difference is due to a Rails version change, you can allow rake rails:update to overwrite the file.

