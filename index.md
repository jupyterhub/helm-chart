## See installation instructions for:

- [JupyterHub](https://zero-to-jupyterhub.readthedocs.io)
- [BinderHub](https://binderhub.readthedocs.io)

Jump to:
{% for chartmap in site.data.index.entries -%}
- [Development Releases: {{ chartmap[0] }}](#development-releases-{{ chartmap[0] | slugify }})
{% endfor %}


## Stable releases

{% for chartmap in site.data.index.entries %}
  {% if site.stablecharts contains chartmap[0] %}
### {{ chartmap[0] }}

| Release | Date | Application version |
|---------|------|---------------------|
  {%- assign sortedcharts = chartmap[1] | sort: 'created' | reverse -%}
    {%- for chart in sortedcharts -%}
      {%- unless chart.version contains "-" %}
| [{{ chart.name }}-{{ chart.version | remove_first: "v" }}]({{ chart.urls[0] }}) | {{ chart.created | date_to_rfc822 }} | {{ chart.appVersion }} |
      {%- endunless -%}
    {% endfor %}
  {% endif %}
{% endfor %}


{% for chartmap in site.data.index.entries %}
### Development releases: {{ chartmap[0] }}

| Release | Date | Application version |
|---------|------|---------------------|
  {% assign sortedcharts = chartmap[1] | sort: 'created' | reverse -%}
  {% for chart in sortedcharts -%}
| [{{ chart.name }}-{{ chart.version | remove_first: "v" }}]({{ chart.urls[0] }}) | {{ chart.created | date_to_rfc822 }} | {{ chart.appVersion }} |
  {% endfor %}
{% endfor %}
