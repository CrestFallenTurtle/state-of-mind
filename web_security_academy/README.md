# State of Mind

## Navigation
<ul>
  {% for item in site.web_security_academy.data.navigation %}
    <li>
      <a href="{{ item.link }}"> {{ item.name }} </a>
    </li>
  {% endfor %}
</ul>
