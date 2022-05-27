[Voltar](./index.md)

<ul>
{% for dado in site.data.dados %}
  <li>
    <span>{{ dados.name }} - {{ dados.date }}</span>
    <a href="{{ dados.link }}">
      Link
    </a>
  </li>
{% endfor %}
</ul>
