{% if include.skiptitle != "true" %}
# {{ page.title }}
{% endif %}
<div class="lead">{{ include.blurb | markdownify }}</div>
{% if include.tag == "all" %}
{% bibliography %}
{% else %}
{% assign tag = include.tag %}
{% assign query = {{ "" | append: "@*[keywords~=" | append: tag | append: "]*" }} %}
{% bibliography -q {{ query }} %}
{% endif %}
