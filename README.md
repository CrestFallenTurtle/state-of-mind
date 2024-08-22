# State of Mind

## Navigation
<ul>
  {% for item in site.data.root_nav %}
    <li>
      <a href="{{ site.url }}{{ site.baseurl }}{{ item.link }}"> {{ item.name }} </a>
    </li>
  {% endfor %}
</ul>
