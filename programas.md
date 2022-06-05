[Voltar](./index.md)

{% for dado in site.data.dados %}

  <div style="border: 1px solid green;">
    {{ dado.name }} • {{ dado.date }} • <a href="{{ dado.link }}" target="_blank">Link</a><br>
  </div>

{% endfor %}


{% for dado in site.data.dados %}

> {{ dado.name }} • {{ dado.date }} • <a href="{{ dado.link }}" target="_blank">Link</a><br>

{% endfor %}
