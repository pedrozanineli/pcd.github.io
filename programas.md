[Voltar](./index.md)

{% for dado in site.data.infos %}

> {{ dado.name }} • {{ dado.date }} • <a href="{{ dado.link }}">Link</a><br>

{% endfor %}
