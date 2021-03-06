# Tabelas YQL para extração de dados da [wikipedia](http://wikipedia.org).

## 1) Extração de dados sobre cores: [cores.xml](https://github.com/teles/yql-tables/blob/master/wikipedia.org/cores.xml)

Utiliza a url [https://pt.wikipedia.org/wiki/Lista_de_cores](https://pt.wikipedia.org/wiki/Lista_de_cores) para extrair informações sobre cores.

Essas informações são:

| Informações                   | nome do elemento | Observação                        |
|-------------------------------|------------------|-----------------------------------|
| Nome da cor em português      | nome             |                                   |
| Valor hexadecimal da cor      | hexadecimal      |                                   |
| Nome css da cor               | nomecss          | Informação nem sempre disponível  |
| Quantidade de vermelho na cor | red              |                                   |
| Quantidade de verde na cor    | green            |                                   |
| Quantidade de azul na cor     | blue             |                                   |
| Matiz da cor                  | hue              |                                   |
| Saturação da cor              | saturation       |                                   |
| Valor da cor                  | value            |                                   |

Endereço do arquivo xml da tabela: [http://yql-tables.surge.sh/wikipedia.org/cores.xml](http://yql-tables.surge.sh/wikipedia.org/cores.xml)
Para utilizar essa tabela em seu código YQL utilize a notação:

```use "http://yql-tables.surge.sh/wikipedia.org/cores.xml" as cores;``` 

Exemplos de uso:

* Selecionar todos os dados sobre cores:
* [use "http://yql-tables.surge.sh/wikipedia.org/cores.xml" as cores; select * from cores;](https://developer.yahoo.com/yql/console/#h=use+%22http%3A%2F%2Fyql-tables.surge.sh%2Fwikipedia.org%2Fcores.xml%22+as+cores%3B+select+*+from+cores%3B)

* Selecionar todos os dados sobre cores que tem nome começado em *Azul*:
* [use "http://yql-tables.surge.sh/wikipedia.org/cores.xml" as cores; select * from cores where cor.nome like "Azul%"](https://developer.yahoo.com/yql/console/#h=use+%22http%3A%2F%2Fyql-tables.surge.sh%2Fwikipedia.org%2Fcores.xml%22+as+cores%3B+select+*+from+cores+where+cor.nome+like+%22Azul%25%22)

* Selecionar nome em português para a cor *dimgray*:
* [use "http://yql-tables.surge.sh/wikipedia.org/cores.xml" as cores; select cor.nome from cores where cor.nomecss = "dimgray"](https://developer.yahoo.com/yql/console/#h=use+%22http%3A%2F%2Fyql-tables.surge.sh%2Fwikipedia.org%2Fcores.xml%22+as+cores%3B+select+cor.nome+from+cores+where+cor.nomecss+%3D+%22dimgray%22)
