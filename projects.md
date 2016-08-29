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
        <span class="stTitle">PROJECTS</span>
        <div class="stories-caption">
        $ python -m "wall of fame"
        </div>
      </div>

    
{% for post in site.posts%}
{% for category in post.categories %}
{% if category == "project" %}
<div class="post postContent">



  <div class="postTitle">
  <a class='postLink' target="blank" href="{{post.project_url}}">{{post.title}}</a>
  </div>
  <center class="postType">{{post.project_type}}</center>
  <div class="postExt">

 {{ post.content | strip_html }}
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
{% endif %}
{% endfor %}
{% endfor %}
