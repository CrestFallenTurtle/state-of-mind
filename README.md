# State of Mind
<a href="{{ site.url }}"> Home</a>

<i><b>Note</b>You can reach the rendered website <a href="https://crestfallenturtle.github.io/state-of-mind">here</a></i>

### Navigation
<ul>
  {% for item in site.data.root_nav %}
    <li>
      <a href="{{ site.url }}{{ site.baseurl }}{{ item.link }}"> {{ item.name }} </a>
    </li>
  {% endfor %}
</ul>
