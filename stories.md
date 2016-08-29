---
layout: default
---

<style>

#footer {
  position: relative!important;
  bottom: 0;
  left: 0;
  right: 0;
  height: 50px;
  padding-top: 2em;
}
</style>
<section id="story-title">
  <div class="">
    <div class="row">
      <center>
      <div class="stories-title">
      <span class="stTitle"><a class="stTitle" href="/stories">STORIES</a></span>
        <div class="stories-caption">
          wanderer's journal about living, non living &amp; animation
        </div>
      </div>

  
{% for post in site.posts%}
{%  if  post.categories contains 'project' %}{% else %}
<div class="post postContent">



  <div class="postTitle">
  <a class='postLink' href="{{ post.url }}">{{post.title}}</a>
  </div>
  <div class="postExt">
 {{ post.content | strip_html | truncatewords:10}}
  </div>

  <div class="container dateAndStuff">
    <div class="row">
        POSTED ON
       <span class="posted-on">

         {{ post.date | date: "%A, %B %-d, %Y" }}
       </span>
       <span class="in">
         in
       </span>
       <span class="categories-on">
         {% for category in post.categories%}
         {{category}} &nbsp;{% if forloop.last %}{% else %},{% endif %}
         {% endfor %}
       </span>



    </div>
  </div>
</div>
{%  endif %}

{% endfor %}
