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
<table>
  <tr>
    <th>release</th>
    <th>date</th>
  </tr>
  {% for chart in all_charts %}
    {% unless chart.version contains "-" %}
    <tr>
      <td>
      <a href="{{ chart.urls[0] }}">
          {{ chart.name }}-{{ chart.version }}
      </a>
      </td>
      <td>
      <span class='date'>{{ chart.created | date_to_rfc822 }}</span>
      </td>
    </tr>
    {% endunless %}
  {% endfor %}
</table>

<h2>Development releases: JupyterHub</h2>
<table>
  <tr>
    <th>release</th>
    <th>date</th>
  </tr>
  {% for chart in jupyterhub %}
    <tr>
      <td>
      {% unless chart.version contains "-" %}<b>{% endunless %}
      <a href="{{ chart.urls[0] }}">
          {{ chart.name }}-{{ chart.version }}
      </a>
      {% unless chart.version contains "-" %}</b>{% endunless %}
      </td>
      <td>
      <span class='date'>{{ chart.created | date_to_rfc822 }}</span>
      </td>
    </tr>
  {% endfor %}
</table>
<h2>Development releases: BinderHub</h2>
<table>
  <tr>
    <th>release</th>
    <th>date</th>
  </tr>
  {% for chart in binderhub %}
    <tr>
      <td>
      {% unless chart.version contains "-" %}<b>{% endunless %}
      <a href="{{ chart.urls[0] }}">
          {{ chart.name }}-{{ chart.version }}
      </a>
      {% unless chart.version contains "-" %}</b>{% endunless %}
      </td>
      <td>
      <span class='date'>{{ chart.created | date_to_rfc822 }}</span>
      </td>
    </tr>
  {% endfor %}
</table>
</body>
</html>
