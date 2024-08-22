# State of Mind

## Navigation
<ul>
  {% for item in site.data.navigation %}
    <li>
      <a href="{{ page.url }}{{ item.link }}"> {{ item.name }} </a>
    </li>
  {% endfor %}
</ul>
