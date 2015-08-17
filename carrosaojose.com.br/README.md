# Tabela YQL com fnformações dos carros disponíveis no site carrosajose.com.br

Os arquivos xml contidos nesse diretório contém tabelas yql que descrevem informações sobre carros e revendas existentes no site [carrosaojose.com.br](http://www.carrosaojose.com.br).

## O que é uma tabela YQL?

Uma tabela YQL é um arquivo xml lido pelo [YQL](https://developer.yahoo.com/yql/console/), que descreve um certo tipo de informação disponível na internet e o disponibiliza acesso a essa informação através de uma sintaxe muito parecida com o SQL.
Isto é, com YQL é possível criar queries do tipo, "SELECT * FROM CARROS" onde CARROS é uma tabela YQL.

## Url das tabelas "revenda" e "carros"

Para serem utilizadas corretamente e com o content-type certo, as tabelas revenda e carros podem ser chamadas através dos endereços:

* http://yql-tables.surge.sh/carrosaojose.com.br/revenda.xml
* http://yql-tables.surge.sh/carrosaojose.com.br/carro.xml

## Exemplos de uso

### Selecione todas as informações básicas da revenda 3639.
[use "http://yql-tables.surge.sh/carrosaojose.com.br/revenda.xml" as revenda; select * from revenda where id = "3639";](https://developer.yahoo.com/yql/console/#h=use+%22http%3A%2F%2Fyql-tables.surge.sh%2Fcarrosaojose.com.br%2Frevenda.xml%22+as+revenda%3B+select+*+from+revenda+where+id+%3D+%223639%22%3B)

### Selecione telefones da revenda 3639.
[use "http://yql-tables.surge.sh/carrosaojose.com.br/revenda.xml" as revenda; select telefones from revenda where id = "3639";](https://developer.yahoo.com/yql/console/#h=use+%22http%3A%2F%2Fyql-tables.surge.sh%2Fcarrosaojose.com.br%2Frevenda.xml%22+as+revenda%3B+select+telefones+from+revenda+where+id+%3D+%223639%22%3B)

### Selecione todas as informações de um determinado carro.
[use "http://yql-tables.surge.sh/carrosaojose.com.br/carro.xml" as carro; select * from carro where url="http://www.carrosaojose.com.br/veiculos/2250047-volkswagen-gol-1.0-16v-4p-1998.html";](https://developer.yahoo.com/yql/console/#h=use+%22http%3A%2F%2Fyql-tables.surge.sh%2Fcarrosaojose.com.br%2Fcarro.xml%22+as+carro%3B+select+*+from+carro+where+url%3D%22http%3A%2F%2Fwww.carrosaojose.com.br%2Fveiculos%2F2250047-volkswagen-gol-1.0-16v-4p-1998.html%22)

### Selecione informações de todos os carros da revenda 3639.
[use "http://yql-tables.surge.sh/carrosaojose.com.br/revenda.xml" as revenda; use "http://yql-tables.surge.sh/carrosaojose.com.br/carro.xml" as carro; select * from carro where url in (select carros.carro.href from revenda where id = "3639")](https://developer.yahoo.com/yql/console/#h=use+%22http%3A%2F%2Fyql-tables.surge.sh%2Fcarrosaojose.com.br%2Frevenda.xml%22+as+revenda%3B+use+%22http%3A%2F%2Fyql-tables.surge.sh%2Fcarrosaojose.com.br%2Fcarro.xml%22+as+carro%3B+select+*+from+carro+where+url+in+\(select+carros.carro.href+from+revenda+where+id+%3D+%223639%22\))






