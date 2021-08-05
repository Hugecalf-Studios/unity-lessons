---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: default
---

# Current Lessons:
{% assign count = 1 %}
{% for page in site.pages %}
{% if page.type == "lesson" %}
## [{{count}} {{page.title}}]({{site.url}}{{site.baseurl}}{{page.url}})
{% assign count = count | plus: 1 %}
{% endif %}
{% endfor %}

# Lesson Ideas:
{% include ideas.md %}