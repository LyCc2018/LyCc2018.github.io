---
layout: page
title: 归档
image: 13.jpg
bar: true
---
<blockquote>归档目录</blockquote>
<div style="text-align: left">
    <ul>
        {% for post in site.posts %}
        {% capture ym %}{{ post.date | date:"%Y 年 %m 月" }}{% endcapture %}
        {% if yearmonth != ym %}
        {% assign yearmonth = ym %}
        <li>
            <a href="#{{ ym }}">{{ ym }}</a>
        </li>
        {% endif %}
        {% endfor %}
    </ul>
</div>
<hr>
<div style="text-align: left">
    {% for post in site.posts %}
    {% capture ym %}{{ post.date | date:"%Y 年 %m 月" }}{% endcapture %}
    {% if yearmonth != ym %}
    {% assign yearmonth = ym %}
    <blockquote id="{{ ym }}">{{ ym }}</blockquote>
    {% endif %}
    <ul>
        <li>
            <!-- <time datetime="{{ post.date | date_to_string }}">{{ post.date | date_to_string }}</time> -->
            <span>{{ post.date | date:"%d 日" }}</span>
            <a href="{{ post.url }}" title="{{ post.title }}">{{ post.title }}</a>
        </li>
    </ul>
    {% endfor %}
</div>
<br>
<br>
<br>
<br>