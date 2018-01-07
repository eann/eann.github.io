---
title: Home
---

# About me
-----------

I'm a physicist turned to computational neuroscience, with an
interest on biologically inspired computation. In this blog
I will talk about the different aspects of my work and about
the techniques and tricks I happen to learn in time.

# Blog Articles
-----------

{% for category in site.categories %}
### {{category | first}}
{% for posts in category %}
{% for post in posts %}
{% if post.url %}
- [{{post.title}}]({{post.url}})
{% endif %}
{% endfor %}
{% endfor %}
{% endfor %}
