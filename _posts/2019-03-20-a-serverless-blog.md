---
title: "Blogging with Jekyll, GitHub Pages and Thron platform"
excerpt: "How to implement simple blog using the free Github service, a static site generator and the Thron DAM platform to centralize and deliver the multimedia content"
categories:
  - posts
tags: 
 - tech 
 - thron 
 - github
 - serverless
 - jekyll
header: 
  teaser: "https://hub-cdn.thron.com/delivery/public/image/hub/1ab78b0f-caed-4daa-944e-b03ff36f2d4b/1kvrf0/std/0x0/header.jpg"
header_description: "some example"
---

The goal is to create a simple blog, a place where I can share the FisherTransalp experience with my friends in a easy way, without duplicate contents between platform and channels.
A place where I can publish the photos and videos that I will carry out every day during the days where we are crossing the Alps from Livigno (IT) to Innsbruck (AT).

My desire:
* *easy*: a Blog platform ease of use in writing and publishing content
* *serverless*: I have no desire or resources to configure hosting plans and domains
* *use THRON*: since I work there and is designed to manage content, and has an integrated delivery. Test a different way to integration with blogging platform

# What I chose
- [Github pages](https://pages.github.com/) It allows to host static and serverless pages (without the need for a hosting plan, and database)
- [minimal mistake tempalte](https://mmistakes.github.io/minimal-mistakes/): a flexible two columb Jekyll template
- [Thron](https://www.thron.com): an intelligent DAM, where to store and deliver images and video.

# How to guide
I quickly describe the steps that I followed for the creation of the blog and the integration with the contents managed by THRON

## Clone the repository
Start by cloning the [minimal-mistake repository] (https://mmistakes.github.io/minimal-mistakes/docs/quick-start-guide/)

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
Create a new post and include the thron content using the *player*.
Here some examples:

A responsive image embedded on the page
{% highlight javascript %} 
{{ "{% include thronplayer.html 
contentId=<thron contentId> pkey=<share key> clientId=<thron serviceId>" }}%}
{% endhighlight %}

{% include thronplayer.html contentId="lagorai" divId="image1" pkey="a8yszh" clientId="hub" padding="75%" %}

And the same code for embedding a video content 

{% include thronplayer.html contentId="1ab78b0f-caed-4daa-944e-b03ff36f2d4b" divId="video1" pkey="1kvrf0" clientId="hub" padding="75%" %}
