# State of Mind

## Navigation
<ul>
  {% for item in site.data.navigation %}
    <li>
      <a href="/{{ item.link }}"> {{ item.name }} </a>
    </li>
  {% endfor %}
</ul>
