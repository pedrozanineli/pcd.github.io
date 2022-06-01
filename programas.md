[Voltar](./index.md)

<br>

{% for dado in site.data.dados %}

> {{ dado.name }} • {{ dado.date }} • <a href="{{ dado.link }}">Link</a><br>

{% endfor %}
