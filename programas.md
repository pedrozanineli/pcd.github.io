[Voltar](./index.md)

Teste

<ul>
{% for dado in site.data.dados %}
  <li>
    {{ dados.name }}
  </li>
  <li>
    {{ dados.date }}
  </li>
  <li>
    {{ dados.link }}
  </li>
{% endfor %}
</ul>
