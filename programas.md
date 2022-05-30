[Voltar](./index.md)

{% for dado in site.data.dados.teste %}

> {{ dado.name }} • {{ dado.date }} • <a href="{{ dado.link }}">Link</a><br>

{% endfor %}
