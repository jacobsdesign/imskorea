---
layout: base
title: 이슈리포트
permalink: /issueReport/
---
{% include header.html type="page" %}
<h2 class="text-center">{{page.title}}</h2>
<div class="container" role="main">
  <div class="col-md-offset-1">
  {% assign issueByYear = site.data.issueReport | group_by:"year"%}
  {% for issue in issueByYear %}
  {% if forloop.index <= 1 %}
  <div class="row">
  <h3>{{issue.name}}</h3>
  {% for item in issue.items %}
    <div class="col-sm-3">
      <div class="panel card text-center">
      <a href="{{item.pdf_path}}" target="_blank">
      {% if item.img_path %}
      <img src="{{item.img_path}}" width="75" height="103" class="img-thumbnail"></a>
      {% else %}
      <img src="http://lib.keris.or.kr/image/ko/common/noImageM.gif" width="75" height="103" class="img-thumbnail"></a>
      {% endif %}
      <div class="caption" >
      <a href="{{item.pdf_path}}" target="_blank">{{item.title}}</a>
      </div>
      </div>
    </div>
    {% endfor %}
    </div>
    <hr/>
    <div class="row">
    {% else %}
    <h3 class="col-md-1">{{issue.name}}</h3>
    {% for item in issue.items %}
      <div class="col-sm-3">
        <div class="panel card text-center">
        <a href="{{item.pdf_path}}" target="_blank">
        {% if item.img_path %}
        <img src="{{item.img_path}}" width="75" height="103" class="img-thumbnail"></a>
        {% else %}
        <img src="http://lib.keris.or.kr/image/ko/common/noImageM.gif" width="75" height="103" class="img-thumbnail"></a>
        {% endif %}
        <div class="caption" >
        <a href="{{item.pdf_path}}" target="_blank">{{item.title}}</a>
        </div>
        </div>
      </div>
      {% endfor %}
    {% endif %}
    {% endfor %}

  </div>
</div>
