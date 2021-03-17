---
layout: page
title: Testimonials
permalink: /testimonials/
desctiption: "A simple testimonials page where you can show reviews on jekyll theme."
---

<div id="team" class="testimonials">
  <div class="testimonial-container">
    <div class="row">
      <div class="col-md-12">
        <h6 class="double-u">{{page.title}}</h6>
      </div>
    </div>
    <div class="row">
      {% for item in site.data.testimonials %}
      <div class="col-12 review border rounded mb-4">
        <div class="row">
          <div class="col-12 col-md-4 text-center">
            <img width="150" height="150" class="team-image rounded-circle" src="{{item.image | relative_url}}"
              alt="{{item.name}}">
            <h4 class="name font-weight-bold mb-2">{{item.name}}</h4>
            <p class="position"><small>{{item.designation}}</small></p>
            <ul class="review-social">
              {% if item.twitter %}
              <li><a href="{{item.twitter}}"><i class="fa fa-twitter-square fa-2x"></i></a></li>
              {% endif %}
              {% if item.facebook %}
              <li><a href="{{item.facebook}}"><i class="fa fa-facebook-official fa-2x"></i></a></li>
              {% endif %}
              {% if item.linkedin %}
              <li><a href="{{item.linkedin}}"><i class="fa fa-linkedin-square fa-2x"></i></a></li>
              {% endif %}
            </ul>
          </div>
          <div class="col-12 col-md-8 font-italic my-auto lead">
            {{item.comment}}
          </div>
        </div>
      </div>
      {% endfor %}
    </div>
  </div>
</div>
