---
layout: base
title: Horizon Report
permalink: /horizon/
---
{% include header.html type="page" %}
<h2 class="text-center">{{page.title}}</h2>
<div class="container" role="main">
  <div class="col-md-offset-1">
  {% assign horizonByYear = site.data.horizon | group_by:"year"%}
  {% for horizon in horizonByYear %}
  <div class="row">
  <h3>{{horizon.name}}</h3>
  {% for item in horizon.items %}
    <div class="col-sm-3">
      <div class="panel card text-center">
      <a href="{{item.pdf_path}}" target="_blank"><img src="{{item.img_path}}" width="150" height="150" class="img-thumbnail"></a>
      <div class="caption" >
      <a href="{{item.pdf_path}}" target="_blank">{{item.title}}</a>
      </div>
      </div>
    </div>
    {% endfor %}
    </div>
    <hr/>
    {% endfor %}
  </div>
</div>


<!-- {% assign postsByYear =
site.categories.conference | group_by_exp:"post", "post.date | date: '%Y'" %}
{% for year in postsByYear %}
<a data-toggle="collapse" href="#post-item{{ year.name }}"><span class="name">{{ year.name }}</span> <span class="badge">{{ year.size }}</span></a>
<br />
<div class="collapse" id="post-item{{ year.name }}">
  {% for post in year.items %}
  <p><a href="{{ post.url }}">{{ post.title }}</a></p>
  {% endfor %}
</div>
{% endfor %} -->
