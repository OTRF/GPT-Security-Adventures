{% for summary in summaries %}
Report {{loop.index}}

{{summary}}
{% if not loop.last %}

{% endif %}

{% endfor %}