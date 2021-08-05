---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: default
---

# Current Lessons:
{% for page in {{site.pages}} %}
{% if {{page.type}} == "lesson" %}
[{{page.title}}]({{site.url}}{{site.baseurl}}{{page.url}})
{% endif %}
{% endfor %}

# Lesson Ideas:
{% include ideas.md %}