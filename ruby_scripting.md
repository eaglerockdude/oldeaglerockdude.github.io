---
layout: page
title: Ruby Scripting
---
I stumbled across and bought(support authors when you can!)  really good book [Text Processing with Ruby by Rob Miller] [1] which is about..well..
ruby...you see so many examples of ruby code on the web...little snippets on arrays or hashes...but really what is ruby for?

Ruby the language(before Rails) basically is a replacement for PERL.  Now...why Perl had to be replaced...or for that matter...any language..is
still a bit of a mystery to me especially when you get down to the code and see base libraries carried over from one to the next.

This section of my blog is about using ruby then in the context of scripting.  It will highlight and ideally pass on what I have learned
about ruby scripting that I would like to a) remember and b) remember.

My main goal for working with ruby at all is because it is the
language that Ruby on Rails is created in, but for me...hey..its all good.  And who knows...maybe this stuff will come in handy someday.

Maybe computer languages are like money...money needs to flow they say in order to do what it does.  Maybe computer languages have to change
or in a sense flow also to stay alive.

## Concepts of interest

* Why scripting?

<cite>"I've always found it more satisfying to extract some sort of meaning from a jumble of low-quality data than to design an algorithm or create an elegant formal proof.
 There's something pleasingly tangible about this sort of work..." </cite>
  ( Rob Miller - Text Processing with ruby blog.)


### The Shebang

Ever wonder how it is that you can just enter commands in the shell and they run?  Well within the context of a ruby script, to do that you need to do the following.

 - At the top of your script, put the *shebang*  with the following format, which allows us to call our script directly without prefixing the call with  *ruby*.

```
 #!/usr/bin/env ruby
```
The unix ENV command tells the shell to use ruby, and to *locate* it as different systems might have it in different places.

- Make sure the file is executable in terms of authority.  One version of CHMOD to do that is as follows:

```
 $ chmod +x  scriptname
```

- To be able to call your script from anywhere, put it in a directory within your path.  A common place might be */usr/local/bin*
 [1]: https://robm.me.uk/text-processing-with-ruby/



