# State of Mind

## Navigation
<ul>
  {% for item in site.data.navigation %}
    <li>
      <a href="{{ site.url }}{{ site.baseurl }}{{ item.link }}"> {{ item.name }} </a>
    </li>
  {% endfor %}
</ul>
