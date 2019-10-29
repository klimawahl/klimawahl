---
title: Archiv
layout: page
---

<ul class="posts">
  {% for post in site.posts %}

    {% unless post.next %}
      <h3>{{ post.date | date: '%Y' }}</h3>
    {% else %}
      {% capture year %}{{ post.date | date: '%Y' }}{% endcapture %}
      {% capture nyear %}{{ post.next.date | date: '%Y' }}{% endcapture %}
      {% if year != nyear %}
        <h3>{{ post.date | date: '%Y' }}</h3>
      {% endif %}
    {% endunless %}

    <li itemscope>
      <a href="{{ site.github.url }}{{ post.url }}">{{ post.title }}</a>
<!--      <p class="post-date"><span><i class="fa fa-calendar" aria-hidden="true"></i> {{ post.date | date: "%B %-d" }} - <i class="fa fa-clock-o" aria-hidden="true"></i> {% include read-time.html %}</span></p>  -->
     <p class="post-date"><span> von 
     <a href="https://klimawahl.org/menu/about.html">  
     {% if post.author %}
       {{ post.author }}
      {% else %}
      {{ site.data.settings.author.name }}
     {% endif %} </a> 
     &nbsp;|&nbsp;
     {{ post.date | date: "%-d.%m.%Y" }} &nbsp;|&nbsp; 
     {% for tag in post.tags %}{{ tag }} &nbsp; {% endfor %}</span></p>
    </li>
    
    

  {% endfor %}
</ul>
