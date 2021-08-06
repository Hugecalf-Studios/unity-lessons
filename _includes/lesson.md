{% assign root={{include.root}} %}

# {{page.title}}

{% for section in page.sections %}
{% assign sectionIndex = forloop.index %}

[{{sectionIndex}} {{section.title}}](#{{section.id}})

{% for subSection in section.sections %}
{% assign subSectionIndex = forloop.index %}

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[{{sectionIndex}}.{{subSectionIndex}} {{subSection.title}}](#{{subSection.id}})

{% endfor %}
{% endfor %}

{% for section in page.sections %}
{% assign sectionIndex = forloop.index %}

## {{sectionIndex}} {{section.title}}
{: #{{section.id}} }

{% if section.content != null and section.content != "" %}
{% include {{root}}{{section.content}} %}
{% endif %}

{% for subSection in section.sections %}
{% assign subSectionIndex = forloop.index %}

### {{sectionIndex}}.{{subSectionIndex}} {{subSection.title}}
{: #{{subSection.id}} }
{% include {{root}}{{subSection.content}} %}

{% endfor %}
{% endfor %}
