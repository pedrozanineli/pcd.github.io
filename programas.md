[Voltar](./index.md)

{% for dado in site.data.dados %}

{{ dados.name }} - {{ dados.date }}
<a href="{{ dados.link }}">Link</a>

{% endfor %}
