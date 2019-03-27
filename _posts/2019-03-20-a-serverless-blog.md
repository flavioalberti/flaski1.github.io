---
title: "An easy blog page"
excerpt: "How to write and deploy a simple blog page with Github, Thron and jekyll framework"
categories:
  - posts
tags: 
 - tech 
 - thron 
 - github
 - serverless
---
# Perchè?

Ho creato questo semplice blog, per poter pubblicare e condividere la fatastica esperinza della Fischer Transalp.
Cercavo una soluzione semplice che mi permettesse di raccogliere foto e video, ma che non mi costringesse a gestire tutta la parte di infrastuttura necessaria (hosting php + cms etc) per la pubblicazione dei singoli post.

Ho quindi pensato ad utilizzare la piattaforma THRON (per la gestione di tutti i contenuti multimediali), mentre Github pages per la gestione dei post e dell'impaginazione.
Vediamo brevemente come è stato realizzato

## Github (*www.github.com*)

Ho creato un nuovo repositoy pubblico in github, come clone del minimal-mistake repo, a progetto open basato sul framework jekyll per la generazione statica di pagine html.

Github pages supporta l'integrazione con XXX, e l'utilizzo di jekyll è molto utilizzato per la realizzazione di semplici pagine



## THRON
La piattaforma THRON (an Intelligent DAM), è stata utilizzata per la gestione di tutti gli asset multimediali (video ed immagini). La gestione di questi contenuti solitamente non viene maicentralizzati, e tali si trovano suddivisi tra piattaforme video e Gestori di immagini. Thron è una piattaforma che gestisce e distribuisce qualsiasi tipo di contenuto, quidi ho utilizzato questa. 

# How to
Seguiago velocemente i semplici passi che ho dovuto effettuare per la realizzazione del blog.

1. clone del repository
2. configurazione: segui questa semplice guida
3. include il player di thron
4. pubblica i contenuti in THRON e condividili 
5. crea un post ed includi i contenuti immagini

## immagine

{% highlight javascript %} 
{{ "{% include thron-player.html 
contentId=<thron contentId> pkey=<share key> clientId=<thron serviceId>" }}%}
{% endhighlight %}

Il codice definito in thron-player.html

{% highlight html %} 
<div class="wrapper">
<iframe id="{{include.divId}}" width="100%" height="100%" 
src="https://{{include.clientid}}-cdn.thron.com/shared/plugins/embed/current/{{include.clientId}}/{{include.contentId}}/{{include.pkey}}" frameborder="0" scrolling="no" allowfullscreen>
</iframe>
</div>

{% endhighlight %}


{% include thronplayer3.html contentId="lagorai" divId="image1" pkey="a8yszh" clientId="hub" padding="75%" %}

In questo esempio viene embeddato un'imamgine sfruttando il player di thron, l'immagine visualizzata è responsiva, il player si adatta alla pagina in base allo spazio definito per la visualizzazione.


### video
{% include thronplayer3.html contentId="1ab78b0f-caed-4daa-944e-b03ff36f2d4b" divId="video1" pkey="1kvrf0" clientId="hub" padding="75%" %}


In questo esempio è stato embeddato un semplice contenuto video, attraverso il player di thron che si adatta in modo responsivo alla dimensione del div in pagina








