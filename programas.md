<div id="voltar"> <a href="./index.md">Voltar</a></div>

{% for dado in site.data.dados %}

> {{ dado.name }} • {{ dado.date }} • <a href="{{ dado.link }}">Link</a><br>

{% endfor %}

<a href="#voltar">Voltar para cima</a>
