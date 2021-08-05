{% assign root={{include.root}} %}

# {{page.title}}

{% for section in page.sections %}
{% assign sectionIndex = forloop.index %}

[{{sectionIndex}} {{section.title}}](#{{section.title}})

{% for subSection in section.sections %}
{% assign subSectionIndex = forloop.index %}

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[{{sectionIndex}}.{{subSectionIndex}} {{subSection.title}}](#{{subSection.title}})

{% endfor %}
{% endfor %}

{% for section in page.sections %}
{% assign sectionIndex = forloop.index %}

## {{sectionIndex}} {{section.title}}

{% if section.content != null and section.content != "" %}
{% include {{root}}{{section.content}} %}
{% endif %}

{% for subSection in section.sections %}
{% assign subSectionIndex = forloop.index %}

## {{sectionIndex}}.{{subSectionIndex}} {{subSection.title}}
{% include {{root}}{{subSection.content}} %}

{% endfor %}
{% endfor %}
