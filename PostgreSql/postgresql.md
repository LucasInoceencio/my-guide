# O que é SQL?

*Structured Query Language.*

# O que o comando abaixo faz ?

```sql 
SELECT NOW();
```
	
*Retorna um timestamp do momento em que a Query foi executada.*

# Quais as duas formas de se criar um banco de dados?

*Pode ser criado através do SQL ou através de um SGDB como o PGAdmin.*


## Como criar via sql?

```sql 
CREATE DATABASE nomeBanco;
```

## Como criar via sql passando informações como encoding, owner e connection limit?
	
```sql
CREATE DATABASE nomeBanco
WITH 
	ENCODING = UTF8,
	OWNER = postgres,
	CONNECTION LIMIT = -1;
```
		

# Qual o comando utilizado no PGSql para visualizar os bancos que estão criados no server?

```\l```

# Como apagar um banco de dados via SQL?
	
```sql
DROP DATABASE nomeBanco;
```

# Quais os principais dados que uma tabela pode ter?

`integer`

`real` (casas decimais, com até 6 digitos de precisão)

`serial` (igual ao inteiro com incremento automático)

`numeric` (pode definir a quantidade de casas decimais)

`varchar(n)` (texto com um tamanho pré-determinado)

`char(n)` (tamanho exato que irá receber, como o cpf)

`text` (quando não se tem ideia do tamanho que o campo irá ter)

`boolean` (para informar true or false)

`date`

`time`

`timestamp` (data e hora)


# Como criar uma tabela via SQL?

```sql
CREATE TABLE nomeTabela(
	id SERIAL
	nome VARCHAR(255),
	cpf CHAR(11),
	observacao TEXT
	idade INTEGER,
	dinheiro NUMERIC(10,2), -- 12345678,90 ou seja 10 números com duas casas decimais
	altura REAL,
	ativo BOOLEAN,
	data_nascimento DATE,
	hora_aula TIME,
	matriculado_em TIMESTAMP
);
```

# Como eu posso excluir uma tabela via SQL?

```sql
DROP TABLE nomeTabela;
```


# Como selecionar todos os dados de uma tabela X via SQL?

```sql
SELECT * FROM X;
```


# Como eu posso incluir uma informação em uma tabela via SQL?

```sql
INSERT INTO nomeTabela (campo1, campo2)
VALUES (value1, value2);
```

# Qual símbolo/caracter é utilizado para separar as casas decimais?

*É utilizado o . (ponto).*

# Qual a formatação de data ao fazer um insert via SQL?

*'YYYY-MM-DD'*

# Qual a formatação da hora ao fazer um insert via SQL?

*'HH24:MI:SS'*

# Qual a formatação do timestamp ao fazer um insert via SQL?

*'YYYY-MM-DD HH24:MI:SS'*

# Como eu posso alterar um dado de uma tabela via SQL?
```sql
UPDATE nomeTabela 
SET 
	coluna1 = valor1,
	coluna2 = valor2
WHERE condição;
```

# Pra que serve o WHERE ao fazer operações via SQL?

*Para restringir as operações para os registros que atendam a cláusula WHERE.*

# Como eu posso excluir um registro de uma tabela via SQL?

```sql
DELETE FROM nomeTabela
WHERE condição;
```

# Pra que serve o SELECT?

*Serve para fazer uma consulta, ou seja selecionar dados de uma tabela.*

# Como eu posso fazer um SELECT trazendo somente algumas colunas específicas?

```sql
SELECT coluna1, coluna2 
FROM nomeTabela;
```

# Pra que serve um ALIAS em SQL?

*Serve para dar apelidos para colunas ou tabelas em suas operações com SQL.*

# Como eu posso fazer um ALIAS para uma coluna ao fazer um SELECT via SQL?

```sql
SELECT colunas AS AliasQueEuQuero 
FROM nomeTabela;
```

# Como definir um ALIAS com espaços no nome, exemplo "Data de nascimento"?

```sql 
SELECT coluna AS "Data de nascimento" 
FROM nomeTabela;
```

# Como eu posso filtrar registros em uma consulta SQL onde o nome deve ser igual 'Antonio'?

```sql
SELECT * FROM nomeTabela 
WHERE nome = 'Antonio';
```

# Como eu posso filtrar registros em uma consulta SQL onde o nome deve ser diferente de 'Isabela'?

```sql
SELECT * FROM nomeTabela WHERE nome <> 'Isabela';
SELECT * FROM nomeTabela WHERE nome != 'Isabela';
```

# Pra que serve o operador LIKE?

*É um operador especial de pesquisa, vai filtrar resultados parecidos.*

# Pra que serve o `_` ao utilizar o LIKE?

*O `_` serve para ignorar o caracterer na posição onde o mesmo está.*

*Exemplo:*
	
```sql
SELECT * FROM nomeTabela 
WHERE nome LIKE 'D_ego';
```

*Nesse caso ele traria resultados como Diego e Diogo.*

# Pra que serve o NOT LIKE?

*É como se fosse o diferente, é o operador de negação do LIKE.*
	
# Pra que serve o `%` ao utilizar o LIKE?

*Serve para pesquisar qualquer coisa até certo ponto.*
	
*Exemplos:*

```sql
SELECT * FROM nomeTabela 
WHERE nome LIKE 'D%';
-- Iria trazer tudo o que começa com D, independente do que seja.

SELECT * FROM nomeTabela 
WHERE nome LIKE '%s';
-- Iria trazer tudo o que termina com s, independente do início.

SELECT * FROM nomeTabela 
WHERE nome LIKE '% %';
-- Iria trazer tudo o que tivesse espaço, pois ele traz qualquer coisa antes, um espaço e qualquer coisa depois.

SELECT * FROM nomeTabela 
WHERE nome LIKE '%i%a%';
-- Iria trazer qualquer nome que tenha i e a como "Vinicius Dias";
```

# Pra que serve o `IS NULL` e o `IS NOT NULL`?

*Serve para verificar se um campo é nulo ou não.*

# Posso utilizar o `=` para verificar se uma coluna é nula ou não?

*Não pode, deve usar o IS NULL ou o IS NOT NULL.*

*Exemplo errado:*

```sql
SELECT * FROM nomeTabela 
WHERE coluna = null;
```

# Pra que serve o operador >= ?

*Serve para verificar se maior ou igual.*

# Pra que serve o operador <= ?
	
*Serve para verificar se é menor ou igual.*

# Pra que serve o operador <?

*Serve para verificar se é menor.*

# Pra que serve o operador >?

*Serve para verificar se é maior.*

# O operador `!=`, `>=`, `<=` traz resultados que sejam `NULL`?

*Esses operadores não trazem resultados que sejam `NULL`.*

*Exemplo:*

```sql
SELECT * FROM nomeTabela 
WHERE idade <> 36;
```

# Pra que serve o `BETWEEN`?

*Serve para verificar se um determinado valor está entre dois valores.*

*Exemplo:*

```sql
SELECT * FROM nomeTabela 
WHERE idade BETWEEN 10 AND 40;
```

# Quais operadores posso usar com valores `BOOLEAN`?

*É possível utilizar o `=`, `<>`, `IS NULL` e o `IS NOT NULL`.*

# Pra que serve o operador `AND` e `OR`?

*São operadores lógicos.*

*O `AND` é o e o que significa que retorna `TRUE` quando ambas condições são verdadeiras.*

*O `OR` é o ou o que significa que retornar `TRUE` quando ao menos uma das condições seja verdadeira.*

# O que é uma chave primária?

*É quando uma coluna ou um grupo de colunas podem ser utilizadas para identificar uma linha única na tabela.*


# Como especificar que uma determinada coluna não pode receber o valor `NULL`?

*Ao criar a tabela defina que tal coluna seja `NOT NULL`.*

# Como especificar que uma determinada coluna seja única na tabela?

*Ao criar a tabela defina que tal coluna seja `UNIQUE`.*

# Quais as características de uma chave primária?

*Não pode ser nulo e deve ser único.*

# Ao criar a tabela abaixo, poderíamos substituir o NOT NULL UNIQUE pelo que?

```sql
CREATE TABLE nomeTabela (
	coluna1 INTEGER NOT NULL UNIQUE, 
	coluna2 VARCHAR(255));
```
	
*Pode substituir por `PRIMARY KEY`.*

# É possível ter uma chave primária com mais de uma coluna? Como fazer isso?

*Sim, é possível.*

*Exemplo:*
```sql
CREATE TABLE nomeTabela( 
	coluna1 INTEGER, 
	coluna2 INTEGER, 
	PRIMARY KEY (coluna1, coluna2));
```

# Pode-se utilizar `SERIAL` juntamente com o `PRIMARY KEY`?

*Não só pode como deve.*

# O que são chaves estrangeiras? Quais os seus benefícios?

*São valores em uma coluna ou grupo de colunas que precisam corresponder ao valor de alguma linha de outra tabela.*
	
*Manter a consistência do banco de dados.*

# Como eu posso criar uma tabela com chave estrangeira via SQL?

```sql
CREATE TABLE aluno_curso(
	aluno_id INTEGER,
	curso_id INTEGER,
	PRIMARY KEY (aluno_id, curso_id),
	FOREIGN KEY (aluno_id)
		REFERENCES aluno (id),
	FOREIGN KEY (curso_id)
		REFERENCES curso (id));
```

# Como fazer uma consulta SQL que traga dados de mais de uma tabela, onde uma contém uma chave estrangeira para outra?

*Exemplo:*

```sql
SELECT * FROM aluno
JOIN aluno_curso 
	ON aluno_curso.aluno_id = aluno.id
JOIN curso 
	ON aluno_curso.curso_id = curso.id
```

# Qual a característica principal do JOIN?

*Os dados devem existir em ambas as tabelas.*

*Exemplo:*

*Tabela aluno_curso ao fazer o `JOIN` só irá trazer resultados caso os resultados existam nas duas tabelas, se alguma coluna for nula ou tiver um id inexistente esse dado não será retornado.*

# Como eu poderia retornar dados de mais de uma tabela, onde uma contém uma chave estrangeira para outra mas alguns registros não possuem vínculo com outra tabela?

*Poderia utilizar o `LEFT JOIN` ou o `RIGHT JOIN`.*

# Qual a diferença entre o `LEFT JOIN`, `RIGHT JOIN`, `FULL JOIN` e `CROSS JOIN`?

*O `LEFT JOIN` irá retornar `NULL` quando a tabela a direita não possuir relacionamento com a tabela da esquerda. Mas os dados da tabela da esquerda continuarão retornando, por isso `LEFT` no nome.*

*O `RIGHT JOIN` irá retornar `NULL` quando a tabela da esquerda não possuir relacionamento com a tabela da direita. Mas os dados da tabela da direita continuarão retornando, poir isso `RIGHT` no nome.*

*O `FULL JOIN` não importa se o dado existe na tabela da esquerda ou da direita, ele irá trazer mesmo que não tenha o relacionamento.*

*O `CROSS JOIN` irá fazer todas as combinações possíveis entre as tabelas.*

# Pra que serve a o `ON` no `LEFT JOIN`, `RIGHT JOIN` E `FULL JOIN`?

*Serve para indicar qual parâmetro deve ser verificado ao fazer a junção.*

# Qual a diferença ao fazer o SQL de um CROSS JOIN para os demais JOINS?

*O `CROSS JOIN` não há necessidade da cláusula `ON`.*

# Qual é o comportamento padrão ao tentar excluir um dado que está referenciado em outra tabela?

*É uma restrição que não permite a exclusão.*

# Como eu poderia fazer para excluir esse dado mesmo que ele esteja referenciado em outra tabela?

*Você poderia mudar o tipo da `FOREIGN KEY` para `CASCADE`. Mas ao fazer isso o dado será excluído na tabela onde o mesmo está referenciado.*

*Exemplo:*

```sql
CREATE TABLE aluno_curso(
	aluno_id INTEGER,
	curso_id INTEGER,
	PRIMARY KEY (aluno_id, curso_id),
	FOREIGN KEY (aluno_id)
		REFERENCES aluno (id)
		ON DELETE CASCADE, -- Faz com que o dado seja excluído onde ele tá referenciado
	FOREIGN KEY (curso_id)
		REFERENCES curso (id)
		ON DELETE RESTRICT); -- Esse é o comportamente padrão
```

# Qual é o comportamente padrão ao tentar atualizar uma coluna que está sendo referenciada por outra tabela?

*É uma restrição que não irá permitir a atualização das informações.*

# Como eu poderia fazer para atualizar esse dado mesmo que esteja sendo referenciado em outra tabela?

*Você poderia mudar o tipo da `FOREIGN KEY` para `CASCADE`. Mas ao fazer isso o dado será atualizado na tabela onde o mesmo está referenciado.*

```sql
CREATE TABLE aluno_curso(
	aluno_id INTEGER,
	curso_id INTEGER,
	PRIMARY KEY (aluno_id, curso_id),
	FOREIGN KEY (aluno_id)
		REFERENCES aluno (id)
		ON DELETE CASCADE -- Faz com que o dado seja excluído onde ele tá referenciado
		ON UPDATE CASCADE, -- Faz com que o dado seja atualizado onde ele tá referenciado
	FOREIGN KEY (curso_id)
		REFERENCES curso (id)
		ON DELETE RESTRICT -- Esse é o comportamento padrão
		ON UPDATE RESTRICT); -- Esse é o comportamente padrão
```

# Como eu posso fazer para ordernar uma consulta em SQL?

*Basta utilizar a cláusula `ORDER BY` passando a coluna que deseja ordernar.*

# Como eu posso fazer a ordenação em ordem decrescente?

*Basta utilizar a cláusula `ORDER BY` passando a coluna e `DESC` para informar o tipo da ordenação.*

# É possível utilizar mais de uma coluna ao fazer a ordenação?

*Sim, basta informar as colunas separadas por vírgula.*

```sql
SELECT * FROM nomeTabela 
ORDER BY coluna1, coluna2;
```

# Qual outra forma de informar qual deve ser a ordenação da consulta?

*Pode informar através de números, lembrando que o índice das colunas começa em 1.*

# A coluna passada no `ORDER BY` precisa estar no `SELECT`?

*Sim, senão não irá funcionar.*


# Poderia informar que o tipo da ordenação deve ser ascendente? Como fazer isso?

*Basta colocar `ASC` na frente da coluna que deseja ordenar.*

```sql
SELECT * FROM nomeTabela 
ORDER BY coluna1 ASC;
```

# O tipo da ordenação é por coluna ou para todo a cláusula `ORDER BY`?

*É por coluna, é possível especificar o tipo de ordernação por coluna.*

```sql
SELECT * FROM nomeTabela 
ORDER BY coluna2 DESC, coluna1 ASC
```

# Como eu poderia especificar por qual coluna eu devo especificar em casos de `JOIN`?

*Você pode utilizar o nome da tabela ou o alias antes de informar a coluna a ser ordenada.*

# Como eu posso limitar a quantidade de registros a trazer numa consulta SQL?

*Você pode utilizar a cláusula `LIMIT` seguida da quantidade de registros que deseja trazer.*

```sql
SELECT * FROM nomeTabela LIMIT 5;
```

# Qual recurso eu poderia utilizar para fazer uma paginação?

*Poderia utilizar o recurso `OFFSET` pois ele irá andar a quantidade de registros pra frente.*

```sql
SELECT * FROM nomeTabela 
LIMIT 5 OFFSET 2; -- Está pulando dois registros e pegando os próximos 5.
```

# Quais as principais funções de agregações e pra que serve cada uma?

```sql
-- COUNT - Retorna a quantidade de registros
SELECT COUNT() FROM nomeTabela;
SELECT COUNT(nomeColuna) FROM nomeTabela;
SELECT COUNT(*) FROM nomeTabela;
SELECT COUNT(1) FROM nomeTabela; -- Versão mais performática. Sempre que for usar o COUNT usar nesse formato aqui.

-- SUM - Retorna a soma dos registros
SELECT SUM(nomeColuna) FROM nomeTabela;

-- MAX - Retorna o maior valor dos registros
SELECT MAX(nomeColuna) FROM nomeTabela;

-- MIN - Retorna o menor valor dos registros
SELECT MIN(nomeColuna) FROM nomeTabela;

--AVG - Retorna a média dos registros
SELECT AVG(nomeColuna) FROM nomeTabela;
```

# Como eu faço pra fazer com que os dados de uma consulta SQL não se repitam?

*Posso utilizar o `DISTINCT` ou o `GROUP BY`.*

# Quando é necessário utilizar o `GROUP BY` ao invés do `DISTINCT`?

*Quando é necessário utilizar alguma função de agregação.*

# Dê um exemplo de uso do GROUP BY.

```sql
SELECT 
	coluna1,
	coluna2,
	COUNT(1)
FROM
	nomeTabela
GROUP BY coluna1, coluna2
ORDER BY coluna1;
```

# Posso utilizar funções de agregação dentro de um cláusula `WHERE`?
	
*Não é possível fazer tal ação.*

# Existe algum outro comando para que eu possa utilizar as funções de agregação como filtro? Se sim, qual seria?

*Sim, existe o `HAVING`.*

# Dê um exemplo de uso do HAVING.

```sql
SELECT 
	curso.nome
	COUNT(aluno.id)
FROM curso
LEFT JOIN aluno_curso ON aluno_curso.curso_id = curso.id
LEFT JOIN aluno ON aluno.id = aluno_curso.aluno_id
GROUP BY 1 -- curso.nome
HAVING COUNT(aluno.id) = 0;
```


# Como eu faço um comentário em linha em SQL?

*Basta utilizar `--`*

# Como eu faço um comentário em bloco em SQL?

*Basta utilizar o `*/` para abrir o bloco de comentário e depois utilizar `/*` para fechar o bloco de comentário.*


# Eu consigo arredondar valores de ponto flutuante numa consulta SQL? Se sim, o que devo utilizar?

*É possível utilizar através da cláusula `ROUND`.*

*Exemplo:*

```sql
SELECT ROUND(valor, 2) FROM nomeTabela;
```

*O segundo parâmetro é para informar a quantidade de casas decimais que deve ter o arredondamento.*


----
----
---- 


# Dica para criação de referências:

Sempre criar as referências da chave estrangeira com as chaves primárias das outras tabelas.

# O que é cardinalidade?

O grau de relacionamento entre as tabelas.

# O que é um para muitos?

Uma categoria pode ter vários cursos, ou seja, um para muitos

# O que é muitos para um?

Muitos cursos podem estar na mesma categoria.

# O que é muitos para muitos?

Quando aluno tem muitos cursos e cursos pode ter muitos alunos.

# Em qual tipo de relacionamento é necessário uma tabela de junção?

Muitos para muitos.

# O que é um para um?

Relacionamento um pouco mais raro, mas dando um exemplo:

Um aluno só pode ter um endereço e um endereço só pode ter um aluno.

# Pra que serve o operador `IN`?

Serve para verificar se um campo do filtro está numa determinada lista de possibilidades. É como se fosse vários OR.

# O que são queries aninhadas ou sub querie?

É uma querie dentro de outra, podendo ser usada como um where ou até mesmo uma outra tabela.

# Pra que serve o operador `||` ? Ele funciona em qualquer banco?

Serve para concacenar e é uma função expecífica do postgres.

# O que acontece se eu utilizar o `||` juntando string com algum campo nulo?

Irá retornar nulo, mesmo que o primeiro campo tenha informação.

# Tem alguma outra função que eu possa utilizar para realizar concatenção mesmo que tenha alguma coluna que seja nula?

Pode-se utilizar a função `CONCAT` passando os parâmetros e separando por vírgula.

# Pra que serve a função `UPPER` e a função `LOWER`?

Serve respectivamente para deixar toda a string em maiúsculo e minúsculo.

# Pra que serve a função `TRIM`?

Serve para remover espaços no início ou no fim da string.

# Pra que serve a função `NOW`?

Serve para retornar um timestamp do instante atual.

# Como eu posso converter um timestamp para um date?

```sql
SELECT NOW()::DATE;
```

# Pra que serve a função `AGE`?

Serve para calcular a idade.

# Pra que serve a função `EXTRACT`?

Serve para extrair uma parte de uma data, como o ano.

```sql
EXTRACT(YEAR FROM AGE(data_nascimento))
```

# Fale uma função matemática e o que ela faz:

```sql
SELECT Pi();
```

# Pra que serve a função `TO_CHAR`?

Serve para formatar e realizar a conversão de textos.

# Pra que serve a view?

É uma tabela virtual que pode ser criado com o select. É uma forma de nomear as consultas.

```sql
CREATE VIEW nome SELECT * FROM ....
```

Recomendado começar com vw, de view.

# Quais as vantagens e desvantagens de se utilizar uma view?

Uma vantagem é a segurança e a comodidade.
Desvantagem é que nem sempre é tão performático.

# O que são os schemas?

É uma separação dentro do mesmo banco de dados.

# Qual é o schema padrão?

É o schema public.

# Como eu posso acessar outro schema?

Basta colocar o nome do schema antes da tabela, seguido por um ponto final.
administrativo.clientes.

# Em schemas diferentes é possível ter tabelas com nomes iguais?

Sim, é possível.

# Como eu posso renomear o nome de uma tabela?

```sql
ALTER TABLE nome_atual RENAME TO nome_novo
```

# O que é DDL? Cite algumas ações que usam o DDL?

Data Definition Language. Create, alter, drop. Tudo o que envolve a estrutura do banco.

# O que é DML? Cite algumas ações que usam o DML?

Data Manipulation Language. Insert, update, delete and select.

# Diferença de ' e "?

' delimitam valores e " delimitam campos.

# Como eu crio uma tabela temporária?

```sql
CREATE TEMPORARY TABLE nome_tabela (campos com seus tipos);
```

# Como eu posso alimentar uma tabela temporária recém criada?

Posso utilizar um select. Mas é importante que as ordens estejam corretas.

# É possível misturar schemas ao manipular dados?

Sim, é possível por exemplo criar uma tabela em um schema A e utilizar o schema B para alimentar a tabela recém criada.

# Pra que serve o comando COPY?

Serve para realizar a exportação e o importação de dados. Mas pode se utilizar a interface.

# É possível atualizar os dados de uma tabela com informações de outra? Mesmo em schemas diferentes?

Sim, é possível. Basta fazer o relacionamento no `WHERE`.

# O que é atomicidade em banco de dados?

É a capacidade dos comandos serem únicos e serem executados por inteiros, não tem como executar apenas metade de um comando. Ou executa tudo ou não executa nada.

# O que são as transações?

É a capacidade de controlar essa atomicidade, ou seja de confirmar se realmente deseja executar tal comando.

# Como eu faço uma transação?

Pode-se utilizar o `START TRANSACTION` ou `BEGIN`.

# Pra que serve o `commit` e o `rollback`?

O `rollback` desfaz tudo o que foi feito naquela transação e o `commit` confirma tudo o que foi feito na transação.

# O que acontece por baixo dos panos com o tipo serial?

O postgres define o valor da sequencia e sempre que ele usa ele incrementa esse valor. Por isso que dá erro ao inserir valores de forma manual.

# Qual a diferença do `CURRVAL` e do `NEXTVAL`?

O `CURRVAL` vai retornar o valor atual. O `NEXTVAL` vai retornar o valor atual e incrementar. Ou seja, ao chamar novamente vai estar incrementado.

# O que é o tipo `Enum`?

Delimita o tipo de valores que pode ter em uma tabela.
```sql
CREATE TYPE classificacao AS ENUM ('LIVRE', '12_ANOS');
```

# Pra que serve o `CHECK`?

Vai verificar se o valor está dentro de uma lista possível de valores.

# Pra que serve o `IF NOT EXISTS`?

Permite que não dê erro e pare a execução de um script.

# O que são as constraints?

São restrições.

# O que são valores `default`?

É um valor que vai ser inserido caso não seja informado um valor para a coluna.