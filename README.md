<h1 align="center">SQL Descomplicado</h1>
<p align="center">:construction: Em construção :construction:</p>

Decidi apelidar este repositório com minhas anotações referente à linguagem SQL como "SQL Descomplicado", pois sempre soube SQL mas nunca havia estudado e dado importância como damos a outras linguagens. Por isso, dessa vez, irei priorizar exclusivamente SQL - e não apenas usar como estudo em segundo plano, haha.

### 🤔 O que é SQL?

- SQL, do inglês, Structured Query Language, é o conjunto de instruções com as quais todos os programas e usuários acessam dados em um banco de dados. Com ele podemos trabalhar com banco de dados de forma relacional. (Oracle)
- O SQL permite a padronização ao acesso de banco de dados a partir das famosas __queries__, estas podem ser vistas como uma linha de código que permite que o cliente crie, acesse ou modifique diretamente no BD.
- Existe uma variaedade de RDBMS (Relational Database Management Systems). Alguns irei citar aqui.

### :grey_question: Quando usar?

- :construction: em construção :construction:

### :mag: Principais RDBMS

- [MySQL](https://www.mysql.com/) 
- [Postgree](https://www.postgresql.org/)
- [SQLite](https://sqlite.org/index.html)
- [SQLServer](https://www.microsoft.com/en-us/sql-server)

### :page_facing_up: Tipos de dados

Um conjunto de dados suportados pelo SQL Server pode ser encontrado [aqui](https://docs.microsoft.com/pt-br/sql/t-sql/data-types/data-types-transact-sql?view=sql-server-ver15). Lembrando que, dependendo do banco de dados utilizado, o nome pode de alguns tipos podem mudar.

- Mas alguns que não posso deixar de citar são:

    - Numéricos:
        - INTEGER - Número inteiro
        - BIGINT - Numero inteiro grande
        - FLOAT - Número decimal com pequena precisão
        - DOUBLE - Número decimal com alta precisão
    - Não numéricos:
        - VARCHAR - Que seria uma forma de representar cadeias de caracteres.
        - TEXT - Para textos grandes
    - Data e hora:
        - DATE - Data no formato YYYY-MM-DD hh:mm:ss
        - TIME - Tempo no formato hh:mm:ss 
        - TIMESTAMP - Tempo em segundos desde 1970-01-01

### :memo: Principais Comandos para CRUD

- O comando CREATE TABLE
    - Utilizado para criar uma nova tabela.
    - Sintaxe:
        ```
        CREATE TABLE nome_da_tabela (
            coluna_1 tipo_do_dado,
            coluna_2 tipo_do_dado,
            coluna_3 tipo_do_dado,
            coluna_n tipo_do_dado,
        );
        ```

- O comando SELECT
    - Permite buscar dados diretamente do banco de dados. __QUASE TODAS__ query se inicia com SELECT, por isso é um dos comandos mais utilizados.
    - Permite selecionar uma ou mais colunas
    - Sintaxe: 
        ```
        SELECT coluna_1, coluna_2, coluna_n
        FROM nome_da_tabela;
        ```

- Cláusula WHERE
    - Pode ser usado como filtro de valores em certos campos.
    - Pode receber uma ou mais condições.
    - Os operadores podem ser:
        - Aritméticos:
            - __=__ , __<>__ , __>__ ,  __>__ , __>=__ , __<=__
        - Outros:
            - BETWEEN, LIKE, IN
    - Sintaxe:
        ```
        SELECT coluna_1
        FROM nome_da_tabela
        WHERE coluna_1 operador valor;
        ```

- O comando UPDATE

- O comando DELETE

- O comando GROUPBY

