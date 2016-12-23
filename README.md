{% assign url_parts = page.url | split: '/' %}
{% assign url_parts_size = url_parts | size %}
{% assign rm = url_parts | last %}
{% assign base_url = page.url | replace: rm %}

<ul>
{% for node in site.pages %}
  {% if node.url contains base_url %}
    {% assign node_url_parts = node.url | split: '/' %}
    {% assign node_url_parts_size = node_url_parts | size %}
    {% assign filename = node_url_parts | last %}
    {% if url_parts_size == node_url_parts_size and filename != 'index.html' %}
      <li><a href='{{node.url}}'>{{node.title}}</a></li>
    {% endif %}
  {% endif %}
{% endfor %}
</ul>


## World's information on Alzheimer's

[Alzheimer's Wiki Site](https://github.com/moqri/alzheimers/wiki)
