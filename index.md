<html>
<body>

<p>See installation instructions at:</p>

<ul>
<li><a href="https://zero-to-jupyterhub.readthedocs.io">JupyterHub</a></li>
<li><a href="https://binderhub.readthedocs.io">BinderHub</a></li>
</ul>

<h2>Stable releases</h2>
<ul>
    {% for chart in site.static_files reversed %}
        {% if chart.extname == '.tgz' %}
            {% assign chart_splitted = chart.basename | split: "-" %}
            {% if chart_splitted.size == 2 %}
            <li> <b><a href="{{ site.url }}/helm-chart{{ chart.path }}"> {{ chart.basename }} </a> </b></li>
            {% endif %}
        {% endif %}
    {% endfor %}
</ul>

<h2>Development releases: Jupyterhub</h2>
<ul>
    {% for chart in site.static_files reversed %}
        {% if chart.extname == '.tgz' and chart.basename contains "jupyterhub" %}
            <li>
            {% assign chart_splitted = chart.basename | split: "-" %}
            {% if chart_splitted.size == 2 %}<b>{% endif %}
            <a href="{{ site.url }}/helm-chart{{ chart.path }}"> {{ chart.basename }} </a>
            {% if chart_splitted.size == 2 %}</b>{% endif %}
            </li>
        {% endif %}
    {% endfor %}
</ul>
<h2>Development releases: BinderHub</h2>
<ul>
    {% for chart in site.static_files reversed %}
        {% if chart.extname == '.tgz' and chart.basename contains "binderhub" %}
            <li>
            {% assign chart_splitted = chart.basename | split: "-" %}
            {% if chart_splitted.size == 2 %}<b>{% endif %}
            <a href="{{ site.url }}/helm-chart{{ chart.path }}"> {{ chart.basename }} </a>
            {% if chart_splitted.size == 2 %}</b>{% endif %}
            </li>
        {% endif %}
    {% endfor %}
</ul>
</body>
</html>
