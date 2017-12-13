<html>
<body>

<p>See installation instructions at:</p>

<ul>
<li><a href="https://zero-to-jupyterhub.readthedocs.io">JupyterHub</a></li>
<li><a href="https://binderhub.readthedocs.io">BinderHub</a></li>
</ul>

<h2>Stable releases</h2>
{% assign jupyterhub = site.data.index.entries.jupyterhub | sort: 'created' | reverse %}
{% assign binderhub = site.data.index.entries.binderhub | sort: 'created' | reverse %}
{% assign all_charts = jupyterhub | concat: binderhub %}
<ul>
  {% for chart in all_charts %}
    {% unless chart.version contains "-" %}
    <li>
      <a href="{{ chart.urls[0] }}">
          {{ chart.name }}-{{ chart.version }}
      </a>
      <span class='date'>{{ chart.created | date_to_long_string }}</span>
    </li>
    {% endunless %}
  {% endfor %}
</ul>

<h2>Development releases: JupyterHub</h2>
<ul>
  {% for chart in jupyterhub %}
    <li>
      {% unless chart.version contains "-" %}<b>{% endunless %}
      <a href="{{ chart.urls[0] }}">
          {{ chart.name }}-{{ chart.version }}
      </a>
      <span class='date'>{{ chart.created | date_to_long_string }}</span>
      {% unless chart.version contains "-" %}</b>{% endunless %}
    </li>
  {% endfor %}
</ul>
<h2>Development releases: BinderHub</h2>
<ul>
  {% for chart in binderhub %}
    <li>
      {% unless chart.version contains "-" %}<b>{% endunless %}
      <a href="{{ chart.urls[0] }}">
          {{ chart.name }}-{{ chart.version }}
      </a>
      <span class='date'>{{ chart.created | date_to_long_string }}</span>
      {% unless chart.version contains "-" %}</b>{% endunless %}
    </li>
  {% endfor %}
</ul>
</body>
</html>
