---
layout: default
permalink: index.html
title: A Fighter Journey
description: "Blogging on ...."
---

## O que é este blog

Olá, meu nome é Kaio Magalhães e há alguns anos venho tentando me tornar um lutador amador. Hoje faço parte da [Alliance](https://www.bjjheroes.com/tag/alliance-bjj) que é um dos maiores times do mundo.

Aqui nesse blog vocês poderão acompanhar todos os meus passos nessa jornada.

![cara de paçoca](/images/moments/07-21-2017.jpg)

Eu sou aquele do lado esquerdo com uma camiseta vermelha embaixo do kimono e cara de paçoca.

![cara de paçoca má](/images/moments/07-26-2017.jpg)

E nesse treino sem kimono sou o ultimo do lado esquerdo

<div class="posts">
  {% for post in site.categories.featured limit:2 %}
  <div class="post">
    <h1 class="post-title">
      <a href="{{ site.url }}{{ post.url }}">
        {{ post.title }}
      </a>
    </h1>

  {% if post.modified.size > 2 %}<span class="post-date indexpg" itemprop="dateModified" content="{{ post.modified | date: "%Y-%m-%d" }}"><i class="fa fa-edit" title="Last updated"> {{ post.modified | date_to_string }}</i> <a href="{{ site.url }}/featured" title="Featured posts"><i class="fa fa-paperclip" title="Featured" class="social-icons"></i></a></span>{% else %}<span class="post-date indexpg" itemprop="datePublished" content="{{ post.date | date: "%Y-%m-%d" }}"><i class="fa fa-calendar" title="Date published"> {{ post.date | date_to_string }}</i> <a href="{{ site.url }}/featured" title="Featured posts"><i class="fa fa-paperclip" title="Featured" class="social-icons"></i></a></span>{% endif %}

 {% if post.description.size > 140 %}{{ post.description | markdownify | remove: '<p>' | remove: '</p>' }}{% else %}{{ post.excerpt | markdownify | remove: '<p>' | remove: '</p>' }}{% endif %} <a href="{{ site.url }}{{ post.url }}" title="Read more"><strong>Read more...</strong></a>
  </div>
  <hr class="transp">
  {% endfor %}
</div>

<div class="posts">
  {% for post in site.posts limit:2 %}
  {% unless post.category contains "featured" %}
  <div class="post">
    <h1 class="post-title">
      <a href="{{ site.url }}{{ post.url }}">
        {{ post.title }}
      </a>
    </h1>

  {% if post.modified.size > 2 %}<span class="post-date indexpg" itemprop="dateModified" content="{{ post.modified | date: "%Y-%m-%d" }}"><i class="fa fa-edit" title="Last updated"> {{ post.modified | date_to_string }}</i></span>{% else %}<span class="post-date indexpg" itemprop="datePublished" content="{{ post.date | date: "%Y-%m-%d" }}"><i class="fa fa-calendar" title="Date published"> {{ post.date | date_to_string }}</i></span>{% endif %}

 {% if post.description.size > 140 %}{{ post.description | markdownify | remove: '<p>' | remove: '</p>' }}{% else %}{{ post.excerpt | markdownify | remove: '<p>' | remove: '</p>' }}{% endif %} <a href="{{ site.url }}{{ post.url }}" title="Read more"><strong>Read more...</strong></a>
  </div>
  {% unless forloop.last %}<hr class="transp">{% endunless %}
  {% endunless %}
  {% endfor %}
</div>
<h3 class="post-title">
<div class="pagination" style="margin: 0.5rem;">
    <a class="pagination-item older" href="{{ site.url }}/blog"><i class="fa fa-edit"> Blog</i></a>
    <a class="pagination-item newer" href="{{ site.url }}/tags"><i class="fa fa-tags"> Tags</i></a>
</div>
</h3>
