---
layout: default
title: Home
---

{% include nav.html %}

{% comment %}
About is embedded on the home page now.
Source: _includes/about.md
{% endcomment %}

<div id="about">
![Me at my desk]({{ site.baseurl }}/at-my-desk.jpg){: width="67" height="67" }

{% capture about_md %}{% include about.md %}{% endcapture %}
{{ about_md | markdownify }}
</div>

---

## Resume

- [Resume]({{ site.baseurl }}/resume/)
