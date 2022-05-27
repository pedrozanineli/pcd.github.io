[Voltar](./index.md)

{% for dado in site.data.dados %}

<div style="border:1px;">
  {{ dado.name }} - {{ dado.date }}
  <br><a href="{{ dado.link }}">Link</a>
</div>

{% endfor %}
