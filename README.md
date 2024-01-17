# Davide Legacci - Research


## 🏠 [Home](https://davidelegacci.it/)


{% for post in site.posts %}
<h2>{{ post.title }}</h2>
{{ post.excerpt }}
<a href=".{{ post.url }}">{{➡️ post.title }}</a>
{% endfor %}

