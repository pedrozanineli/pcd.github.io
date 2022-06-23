![logo ilum](https://github.com/pedrozanineli/pcd.github.io/blob/main/logo1.png)

## Projeto Final de Práticas em Ciências de Dados
  
Desenvolvimento de Web Scraping em Python de estágios, bolsas de estudo, programas de verão, programas de “work and study” para produção de um site

No presente repositório, o arquivo `projeto-final.ipynb` são as etapas do desenvolvimento do projeto e do desenvolvimento do *web scrapping*, ao passo de que `index.md` e `programas.md` fazem parte da construção do site. Por fim, os arquivos `config.yml` e o diretório `_data` estão relacionados com a configuração e dados das páginas, respectivamente. 

Para a realização do projeto, a descrição completa pode ser encontrada no artigo existente no repositório, assim como um Jupyter Notebook com todas as etapas seguidas. De maneira simplificada, a estrutura do projeto é descrita a seguir.

## Biblioteca *feedparser*

Como ponto de partida, a biblioteca *feedparser* é utilizada com o intuito de realizar a coleta dos dados a serem inseridos no site, apoiando-se em sites do tipo RSS. Quando um link é passado, é realizado um parse, permitindo o armazenamento em uma variável.

```python
current_feed = feedparser.parse(links[0])
```

A partir disso, é possível buscar algumas estruturas do site que são do interesse para o desenvolvimento do site, sendo, no caso, o título, o link e a data de publicação da matéria. Para tanto, podemos utilizar o seguinte formato:

```python
current_feed.feed.title,current_feed.feed.link,current_feed.feed.description
```


---

```python
trans.translate('Hello, world!',dest='pt').origin,trans.translate('Hello, world!',dest='pt').text
```

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

Trabalho desenvolvido por Artur H. Kimura, Débora V. P. Chaves, Pedro T. Ferreira, Pedro H. M. Zanineli.
