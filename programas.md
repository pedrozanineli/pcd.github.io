[Voltar](./index.md)

Teste

<ul>
{% for dado in site.data.dados %}
  <li>
    {{ dados.name }}
    {{ dados.date }}
    {{ dados.link }}
  </li>
{% endfor %}
</ul>
