[Voltar](./index.md)

{% for dado in site.data.dados %}

  <div style="margin-top:4px;border: 0.5px solid grey;border-radius: 5px;">
    <div style="padding:8px;">
      <strong>{{ dado.name }}</strong><br>
      {{ dado.date }} • <a href="{{ dado.link }}" target="_blank">Link</a>
    </div>
  </div>
  <br>
{% endfor %}

<br>

{% for dado in site.data.dados %}

> {{ dado.name }} • {{ dado.date }} • <a href="{{ dado.link }}" target="_blank">Link</a><br>

{% endfor %}
