[Voltar](./index.md)

{% for dado in site.data.dados %}

  <div style="margin-bottom:6px;border: 0.5px solid grey;border-radius: 5px;">
    <div style="padding:10px;">
      <strong>{{ dado.name }}</strong><br>
      *{{ dado.date }} • <a href="{{ dado.link }}" target="_blank">Link</a>*
    </div>
  </div>
{% endfor %}
