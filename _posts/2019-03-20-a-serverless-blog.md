---
title: "Blogging with Jekyll, GitHub Pages and THRON platform"
excerpt: "How to implement simple blog using the free Github service, a static site generator and the THRON DAM platform to centralize and deliver multimedia content"
header: 
  teaser: "https://hub-view.thron.com/api/xcontents/resources/delivery/getThumbnail/hub/640x0/aa24c371-6146-4d5a-a186-7361207baf3e.jpg"
  header_description: "THRON and GitHub"
  caption: "Photo credit: THRON spa"
categories:
  - posts
tags: 
 - tech 
 - THRON 
 - github
 - serverless
 - jekyll
---

My goal is to create a simple blog, a place where I can share the FisherTransalp experience with my friends in a easy way, without duplicate contents between platform and channels.
A place where I can publish photos and videos that I will carry out every day during the FischerTransalp from Livigno (IT) to Innsbruck (AT).

# My goal

* *easy*: setup a Blog platform easy of use in writing and publishing content
* *serverless*: No pain with servers, hosting plans and other stuff
* *use THRON*: try to use the THRON platform, because I can easily publish all kind of contents, without pains about delivery and storage.

# What I chose
- [Github pages](https://pages.github.com/) It allows to host static and serverless pages (without the need for a hosting plan, and database)
- [minimal mistake tempalte](https://mmistakes.github.io/minimal-mistakes/): a flexible two column Jekyll template
- [THRON](https://www.thron.com): an intelligent DAM, where to store and deliver images and video.

# How to setup
I quickly describe the steps that I followed for the creation of the blog and the integration with the contents managed by THRON

## Clone the repository
Start by cloning the [minimal-mistake-repository](https://mmistakes.github.io/minimal-mistakes/docs/quick-start-guide/)

## Include the THRON Player
Create a *thronplayer.html* file in _include folder where to define customize the [Player](https://help.thron.com/hc/en-us/articles/115003098433-THRON-Universal-Player)

{% highlight html %} 
<div class="wrapper">
<iframe id="4fmms" width="100%" height="100%" 
src="https://<clientId>-cdn.thron.com/shared/plugins/embed/current/clientId/contentId/pkey" frameborder="0" scrolling="no" allowfullscreen>
</iframe>
</div>
{% endhighlight %}

## Upload your images and video in THRON
This is a simple guide how to upload contents in THRON [link](https://help.thron.com/hc/en-us/articles/203722971-How-to-create-new-content)

## Create a new post and use your images/video
Create a new post and include the THRON content using the *player*.
Here some examples:

A responsive image embedded on the page
{% highlight javascript %} 
{{ "{% include thronplayer.html 
contentId=<thron contentId> pkey=<share key> clientId=<thron serviceId>" }}%}
{% endhighlight %}

{% include thronplayer.html contentId="lagorai" divId="image1" pkey="a8yszh" clientId="hub" padding="75%" %}

And the same code for embedding a video content 

{% include thronplayer.html contentId="1ab78b0f-caed-4daa-944e-b03ff36f2d4b" divId="video1" pkey="1kvrf0" clientId="hub" padding="75%" %}
