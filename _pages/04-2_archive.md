---
layout: base
title: 행사자료
permalink: /archive/
---
{% include header.html type="page" %}
<h2 class="text-center">{{page.title}}</h2>
<div class="container" role="main">
  <div class="col-md-offset-1">
  {% assign archiveByYear = site.data.archive | group_by:"year"%}
  {% for archive in archiveByYear %}
  <div class="row">
  <h3>{{archive.name}}</h3>
  {% for item in archive.items %}
    <ul style="list-style-type:none">
      <li><i class="far fa-file-pdf" style="color:IndianRed"></i> <a href="{{item.pdf_path}}" target="_blank">{{item.title}}</a> - <i class="fas fa-user-alt"></i> {{item.author}}</li>
      </ul>
      {% endfor %}
        <hr/>
      </div>
        {% endfor %}
      </div>
    </div>
