![logo ilum](https://github.com/pedrozanineli/pcd.github.io/blob/main/logo1.png)

## Projeto Final de Práticas em Ciências de Dados
  
Desenvolvimento de Web Scraping em Python de estágios, bolsas de estudo, programas de verão, programas de “work and study” para produção de um site

No presente repositório, o arquivo `projeto-final.ipynb` são as etapas do desenvolvimento do projeto e do desenvolvimento do *web scrapping*, ao passo de que `index.md` e `programas.md` fazem parte da construção do site. Por fim, os arquivos `config.yml` e o diretório `_data` estão relacionados com a configuração e dados das páginas, respectivamente. O arquivo Artigo - "Webscrapping" e Programas de Estudo refere-se ao trabalho desenvolvido para o programa elaborado.

Para a realização do projeto, a descrição completa pode ser encontrada no artigo existente no repositório, assim como um Jupyter Notebook com todas as etapas seguidas. De maneira simplificada, a estrutura do projeto é descrita a seguir.

## *Feedparser*

Como ponto de partida, a biblioteca *feedparser* é utilizada com o intuito de realizar a coleta dos dados a serem inseridos no site, apoiando-se em sites do tipo RSS. Quando um link é passado, é realizado um parse, permitindo o armazenamento em uma variável.

```python
current_feed = feedparser.parse(links[0])
```

A partir disso, é possível buscar algumas estruturas do site que são do interesse para o desenvolvimento do site, sendo, no caso, o título, o link e a data de publicação da matéria. Para tanto, podemos utilizar o seguinte formato:

```python
current_feed.feed.title,current_feed.feed.link,current_feed.feed.description
```
## *Google Translator*

Em seguida, levando em consideração que o site é destinado a estudantes brasileiros, é interessante a tradução do texto em inglês para o português, e, para tanto, foi usada a biblioteca Google Translator. Passamos como parâmetro da função `translate` da biblioteca a string a ser traduzida, seguida do seu destino, isto é, para que língua o texto deve ser traduzido.

```python
trans.translate('Hello, world!',dest='pt').origin
trans.translate('Hello, world!',dest='pt').text
```

Note que no código acima podemos buscar o texto original com a extensão `.origin` e o texto em si traduzido com `.text`.

## Implementação do código

Com base no exposto, finalmente podemos realizar a coleta dos dados e realizar uma inserção em um arquivo `.csv`, com as colunas "name", "date" e "link". No código a seguir, o loop é destinado por passar por todos os elementos encontrados e inserir no arquivo de destino.

```python
for link in links:
    current_feed = feedparser.parse(link)
    for n in range(len(current_feed.entries)-1):
        text = trans.translate((current_feed.entries[n].title),dest='pt').text 
        print(text)
        print(current_feed.entries[n].published[5:16])
        print(current_feed.entries[n].link)
        print()
```

Uma vez que o arquivo estava pronto, foi possível realizar a atualização de um arquivo já existente neste repositório (`\dados\dados.csv`) para que os dados desejados pudessem ser usados.

## Integração dos dados e site

Com o intuito de integrar os dados no site, foi utilizado o Liquid templating system, que é uma variável construída no próprio Jekyll. Como parte de perfumaria, os dados foram colocados dentro de um retângulo estilizado.

```md
{% for dado in site.data.dados %}

  <div style="margin-bottom:8px;border: 0.5px solid grey;border-radius: 5px;">
    <div style="padding:10px;">
      <strong>{{ dado.name }}</strong><br>
      {{ dado.date }} • <a href="{{ dado.link }}" target="_blank">Link</a>
    </div>
  </div>
{% endfor %}
```
---

Trabalho desenvolvido por Artur H. Kimura, Débora V. P. Chaves, Pedro T. Ferreira, Pedro H. M. Zanineli.
