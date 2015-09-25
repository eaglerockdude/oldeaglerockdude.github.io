---
layout: post
title: github pages with iPage
category: tools
---

<div class="message">
  <cite> "As Strother Martin once said in cool hand luke...What we've got here...is a failure to communicate..."</cite>
</div>

## So u wanna free(relatively) blog

So..you downloaded Jekyll, or Octopress, or some other "hacker" blogging software cause you are a hacker...well...a least a developer. For me
well, I was just trying to save some money.

If you had a wordpress or something blog in the past, and you have your own domain name, and when someone enters that domain name,
you want your github pages website to display, then read on.

I will skip the part where you went to github, and created a repository named username.github.io, where username is your github username or
organization.  I mean, that's why you are here right?  [Github stuff](https://pages.github.com/)

## subdomain
Here is something weird. As an example.  www.kenmcfadden...well...the www part is using my domain name as a subdomain.  So is
blog.kenmcfadden, or thedude.kenmcfadden.  All subdomains.  If your website has a url something like that, you are on the subdomain path.
This post is for the other thing.

## apex domain

The simple way to determine this ...well if its not a subdomain then....

I like to think of it as having no prefixes.  not blog.kenmcfadden, or www.kenmcfadden.  Just kenmcfadden.com
That is an apex domain.

Okay here is what you do.


- In the root of your Jekyll project, create a file called CNAME.
- Inside that file, put your domain name in capital letters, with no HTTP or WWW. Just the name.  For me that was kenmcfadden.com
- Github says it has to be capital letters, but mine was not and it works.  Go figure.Now...do you have a subdomain, or an apex domain?
- Go to where your domain name is hosted.  Mine is at iPage.  Go to  `control panel > domain central > DNS`
- You need to configure an **A record**.  From the dropdown select that.
- You will make TWO entries.  You will EDIT the domain name record(in my case kenmcfadden.com) and the * record.
- Use the IP address that github is currently recommending.

 `192.30.252.153`  <br/>
 `192.30.252.154`

You can see these at  [Github IP addresses](https://help.github.com/articles/tips-for-configuring-an-a-record-with-your-dns-provider/)

Supposedly it takes 24 hours for this to take affect, so it won't work right away.  Go to bed, and when you awake in the morning run
over to your computer and type in your domain name.

Ideally...is should work.  My intention was to just address the scenario where someone is using specifically ipage.

## caveat

DNS A-records require that an IP address be hard-coded into your application’s DNS configuration. This prevents your infrastructure provider from assigning your app a new IP address.

A CNAME record does not require hard-coded IP addresses.  If you have a scenario where the IP address changes, you can set up a subdomain
 and then use a CNAME record.  At some point I may do that if i have issues, but for now...My site is up!









