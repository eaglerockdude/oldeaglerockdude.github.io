---
layout: post
title: Rails with Postgres and MySql
category: database
---

<div class="message">
  <cite> "If you can just get it setup, you are halfway there...or...its not the mountains ahead that wear you down, but rather the grain of sand in your shoe." </cite>
</div>

After a while when doing ROR, you start to thinking..."hey..maybe when I finally get a job...they probably are not using SQLite..it might be
good experience to do your development with some other database.  Two of the most popular are PostgreSql and MySql.

I installed and set up both on my MAC Yosemite.

## MySQL
Here is the deal.  I previously was playing with PHP and I had MAMP installed, which basiscally gives you a PHP/Apache/MySQL stack.  I figured
why not just use THAT MYSQL instance instead of installing a separate one.

Besides.  I was not able to use MYSQL with my Rails applications ANYWAY until i sorted things out.  The MAMP version the the MYSQL2 gem were
not working together.  Now..if you really want to get into the details...look at the code for the MYSQL2 gem.  I am sure that you can just
change some setting in there, and you would be fine.  But I learned that after the fact.

Lets cut to the chase.  If don't want to uninstall your MAMP application(because...yeah...you are thinking that some day you will return to PHP!) then
here is what you need to know.

{% highlight ruby linenos %}
def use_MAMPs_MYSQL
default: &default
  adapter: mysql2
  encoding: utf8
  pool: 5
  username: root
  password: root
  host: localhost
  socket: /Applications/MAMP/tmp/mysql/mysql.sock

development:
  <<: *default
  database: rails_mysql_development
  socket: /Applications/MAMP/tmp/mysql/mysql.sock

end
{% endhighlight %}

If you get some error in your rails setup like "Can't connect to local MySQL server through socket '/tmp/mysql.sock' " it's
because when you installed MAMP it has it's own directories and location for the mysql.sock file.

I found that by just changing the config/database.yml to point to the correct mysql.sock file it works fine.
Now..in my case, I had also installed a version of MYSQL with Homebrew.  I did not bother to uninstall it.  So I had the mysql.sock
in another location.  But..I think the mysql2 GEM looks for it in the default location anyway.

If you are having trouble with rails connecting, and you are using MAMP...try this.

## PostGres
Coming from my notes   ..too tired right now..gotta paint.
