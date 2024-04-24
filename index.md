## JupyterHub helm charts
{:.no_toc}

See installation instructions for:

- [JupyterHub](https://zero-to-jupyterhub.readthedocs.io)
- [BinderHub](https://binderhub.readthedocs.io)

Jump to:

- this list will be replaced with the table of contents
{:toc}


## Stable releases

{% for chartmap in site.data.index.entries %}
  {% if site.stableCharts contains chartmap[0] %}
### {{ chartmap[0] }}

| Version | Date | App. version |
|---------|------|---------------------|
    {%- assign sortedcharts = chartmap[1] | sort: 'created' | reverse -%}
    {%- for chart in sortedcharts -%}
      {%- unless chart.version contains "-" %}
| [{{ chart.version }}]({{ chart.urls[0] }}) | {{ chart.created | date_to_long_string }} | {{ chart.appVersion }} |
      {%- endunless -%}
    {%- endfor %}
  {%- endif %}
{% endfor %}

## Development releases

Development releases older than one year aren't listed below,
but can still be installed with `helm`.

{%- assign year_ago = 'now' | date: "%s" | minus: 31536000 %}

{% for chartmap in site.data.index.entries %}
### Development releases: {{ chartmap[0] }}

| Version | Date | App. version |
|---------|------|---------------------|
  {%- assign sortedcharts = chartmap[1] | sort: 'created' | reverse %}
  {%- for chart in sortedcharts %}
    {%- assign created_timestamp = chart.created | date: "%s" | plus: 0 %}
    {%- if created_timestamp >= year_ago %}
| [{{ chart.version }}]({{ chart.urls[0] }}) | {{ chart.created | date_to_long_string }} | {{ chart.appVersion }} |
    {%- endif %}
  {%- endfor %}
{% endfor %}
