---
layout: post
title: Hosting your Site 
---

-----
*I teach web development at the University of Louisville. Because of this, I am often asked what is the best way for a new web developer to host a site. The question is almost always followed with a statement like: "Free if possible!" So as I wanted to redo my own server for doing prototype work with docker (that's a blog for another day), I thought I would discuss what I did for hosting my own site with the thought that it may help someone else wanting something similar.*

-----

The typical answer I give when I'm asked about hosting a site is to visit companies like: 

* [godaddy](http://www.godaddy.com)
* [arvixe](http://www.arvixe.com)

...or any of the 100's of companies out there that will sell you a hosted site for usually under $5 per month. Here try it yourself: [Link](http://lmgtfy.com/?q=web+hosting+cheap)

When you purchase server space this way (it's called shared hosting), you typically get a set amount of space, bandwidth, a couple of ftp accounts, and usually a MySQL (or SqlServer) instance you can use. On most services, you even get one-click install options for blogs, portals, wiki's and tons more cool features. Not too bad when you consider, you are paying around $4 / month. The drawback of course is that you are sharing the space with 100's of other people. Normally, it's not much of an issue, but  when you do have an issue there's no way of really knowing. You call and complain, but, without access to the server, you are limited in your troubleshooting. Still, shared hosting get's you moving with a very low barrier to entry into everything you need to run and manage your own environment. Most folks are fine stopping right there.

From here, you can branch into Virtual Private Servers (VPS), co-located servers, and cloud offerings from a variety of amazing companies. Each of these options offers different capabilities and cost models (ranging from expensive to free). Typically, with more options comes more complexity. Now rather than clicking a button to install Wordpress, you might have to install MySql and a web container before you can install your blog. Then, of course, you have to remember to patch those boxes at the operating system, container, and application levels. All of these steps are incredibly useful skills in the software profession, and you **should** be able to do this. But sometimes you want to go the other direction. Sometimes, you don't need all that power, options, or headache. Sometimes, what you need is a dead simple solution to host your presence online. It's these times that is the focus of this article.

### The Rise of Static Websites

The first time I heard of static websites was likely with Amazon S3. Amazon has amazing cloud offerings and handle just about every need you might have within a cloud environment. Amazon S3 is no exception. Amazon S3 (Simple Storage Service) is an online file storage web service offered by Amazon Web Services. Amazon S3 provides storage through web services interfaces (REST, SOAP, and BitTorrent). Several years ago, developers discovered that if your site was simple enough and you only used client-side script with JavaScript, you could completely host your site within S3. The idea caught on and Amazon began providing support. Soon, with very little effort and cost, even your custom domains could point to your Amazon bucket. Not only did the solution provide simplicity, but it also allowed developers to leverage the incredible power of content delivery networks (CDN's). 

Now for little or no cost, you can distribute your website across cloud provider servers and have it staged worldwide. Totally awesome!

Today, just about every cloud provider is in the game today. You can get static websites from [Amazon S3](http://docs.aws.amazon.com/AmazonS3/latest/dev/WebsiteHosting.html), [Google Cloud Storage](https://cloud.google.com/storage/docs/website-configuration), [Rackspace](http://docs.rackspace.com/files/api/v1/cf-devguide/content/Create_Static_Website-dle4000.html), and many more that I couldn't even begin to name. 

My personal favorite (and the one I recently migrated too) is [github](https://pages.github.com/).  

### Implementing your Site on GitHub

I love github. No really, I love github. 

Setting aside for just a second that Github uses git (my personal favorite version control system), I don't think it's an exaggeration to say Github is *where collaboration takes place with code today*. 

> *Github is where collaboration takes place with code today*

Companies from Microsoft to jQuery all host code repositories in the open. Why is that so special? Any project on github, allows you to freely see the source code and, even, fork it (the name with give to creating your own editable copy). Find an error in a your favorite library? Chances are it's on github. Fork the repo, correct the issue, and make a pull request to the maintainer. You have made the world a better place. You have fixed and offered help to others using that same library. That is the power of open source and is at the heart of collaboration in software. Github while not unique in the space, is the defacto standard for today's open source developers. 

One of the features github offers is github pages. Github pages are static websites that are either: disconnected branches with your project's source code and a user/organization website created following the pattern <username>.github.io. It essentially allows you to host your site using the version control power of git. As developers are already in github, it becomes trivial to host your content next to the source code.
	
Without trying to go too deep here (you can find much more detail on [github pages](https://pages.github.com/) here), here's the basics steps I went through to get started with my site on github:

1. Create a new github repository called wesreisz.github.io (use your username in place of mine)
1. Clone a starter template you like (I used bootstrap and a project template from [here](http://startbootstrap.com/)).
1. Committed the project and pushed my site.
1. Waited about 20-30 minutes before I could view it at wesreisz.github.io. After the initial deployment, site pushes are almost immediate.
1. Customized my site the why I wanted it
1. Added a CNAME file and updated my DNS to point to github

### Adding a blog to your static site

So that's cool, but you can't do anything real with a static site right? Don't be so sure. With the move to more and more javascript, we are moving processing from the server back to the client. So depending on your needs, it is entirely possible that you can host everything a simple site needs locally.

Once challenge I came on with moving my site to github wasn't really with dynamic content per say. It really was how can I implement a blog without a server-side database. I vaguely remembered a talk a couple years ago, where someone mentioned a tool called [jekyll](http://jekyllrb.com/), so I started there. Turns out, Jekyll was the perfect solution, and one the community as a whole is embracing.

Jekyll is a dirt simple static site generation system that uses [markdown](http://en.wikipedia.org/wiki/Markdown) and the local file system. What does all this mean? It means it's a super simple system for blogging. Setting everything up is done with a ruby gem, so installing Jekyll and running it is as easy as:

![Installing Jekyll](/images/moving_to_github/install.png)

That last part is particularly interesting. 
```
jekyll serve 
```
starts a webserver that you can view locally and adding
```
jekyll serve --watch
```
allows you to make realtime changes as you go and get immediate feedback. How cool is that? All that was left was for me to integrate into my newly designed sight. (...and of course push to github.)

### Recap
So let's recap. I have:

* hosting space that costs me exactly nothing.
* a fully customizable blog engine
* markdown for editing of my blog content
* git version control for my blog and website 
* local development environment where I can see changes

Not bad! [http://www.wesleyreisz.com](http://www.wesleyreisz.com)

	
	










