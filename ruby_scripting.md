---
layout: page
title: Ruby Scripting
---
I stumbled across and bought(support authors when you can!)  really good book [Text Processing with Ruby by Rob Miller] [1] which is about..well..
**ruby**...you see so many examples of ruby code on the web...little snippets on arrays or hashes...but really what is ruby for?

Ruby the language(before Rails) basically is a replacement for PERL.  Now...why Perl had to be replaced...or for that matter...any language..is
still a bit of a mystery to me especially when you get down to the code and see base libraries carried over from one to the next.

Maybe computer languages are like money...money needs to flow they say in order to do what it does.  Maybe computer languages have to change
or in a sense flow also to stay alive.

This section of my blog is about using ruby then in the context of scripting.  It will highlight and ideally pass on what I have learned
about ruby scripting that I would like to a) remember and b) remember.

My main goal for working with ruby at all is because it is the
language that Ruby on Rails is created in, but for me...hey..its all good.  And who knows...maybe this stuff will come in handy someday.


## Concepts of interest

* Why scripting?

<cite>"I've always found it more satisfying to extract some sort of meaning from a jumble of low-quality data than to design an algorithm or create an elegant formal proof.
 There's something pleasingly tangible about this sort of work..." </cite>   </br>
  ( Rob Miller - Text Processing with ruby blog.)


### The Shebang

Ever wonder how it is that you can just enter commands in the shell and they run?  Well within the context of a ruby script, to do that you need to do the following.

 - At the top of your script, put the *shebang*  with the following format, which allows us to call our script directly without prefixing the call with  *ruby*.
 - To be able to call your script from anywhere, put it in a directory within your path.  A common place might be */usr/local/bin*

{% highlight ruby %}
  #!/usr/bin/env ruby
{% endhighlight %}

The unix **ENV** command tells the shell to use ruby, and to *locate* it as different systems might have it in different places.

- Make sure the file is executable in terms of authority.  One version of CHMOD to do that is as follows:

{% highlight ruby %}
  $ chmod +x  scriptname
{% endhighlight %}

### ruby arguments
(Thanks to  [ Rob Miller] [1]  for these code examples)

Within the context of ruby scripting, the ruby interpreter accepts some very useful and practical arguments.    This is useful in the sense that you don't
always have to write and keep a script in a file particularly for one-time jobs.  Also of course, when you are designing or trying out ideas for a script, it
gives you the ability to start experimenting with what can be done from the shell.

##### The -e  argument
ruby normally assumes that it is being passed a file.  With the -e argument you can pass code to ruby that will be *evaluated*.

{% highlight ruby %}
$ ruby -e 'puts "Hello world"'    # Hello world
{% endhighlight %}

##### The -n argument

This allows us to read from STDIN without coding it in our actual script, or specifying it in the -e code.
This means that the code we pass in the -e argument is executed once for each line in our input.
The content of the line is stored in the $_ variable.

So the following snippets are equivalent(from Ruby scripting)

{% highlight ruby %}

$ printf "foo\nbar\n" | ruby -e 'STDIN.each { |line| puts line.upcase }'

$ printf "foo\nbar\n" | ruby -ne 'puts $_.upcase'  # shorted code with $_ variable

{% endhighlight %}

It's like the -n arguement creates a "do while" get over standard input.

{% highlight ruby %}
while  gets_stdin
execute -e code
end
{% endhighlight %}

One nice thing about the global variable $_ is that many useful methods have it as their **default** to further simplify things.

For example *print* called with no arguments will default to $_   so you can say:
{% highlight ruby %}
 $ printf "foo\nbar\n" | ruby -ne 'print'  #using default
 printf "foo\nbar\n" | ruby -ne 'print if $_.start_with? "f"' #foo(show only starting with f
 printf "foo\nbar\n" | ruby -ne 'print if /^f/' #use a regexp
{% endhighlight %}

The 2nd example uses ```$_.start_with? ``` to select certain lines. Cool.    And even coooooler...regular expressions work with
$_ as shown in the third example.    Another shortcut....```.gsub also defaults to $_ ```  !

##### The -p  argument
The -p does everything the -n does PLUS it prints also!  Too much!

##### Text line processing notes
Within the context of text process it is common to use the following terms :

-  conditional output:  the output is based on a condition, like a regexp
-  filtering: this is where we modify the output, say with the *cut* method.

 [1]: https://robm.me.uk/text-processing-with-ruby/



