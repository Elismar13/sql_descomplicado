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
        ```SQL
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
        ```SQL
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
        ```SQL
        SELECT coluna_1
        FROM nome_da_tabela
        WHERE coluna_1 operador valor;
        ```
- O comando INSERT
    - Serve para adicionar uma nova linha no banco de dados. Vem acompanhado com o comando __INTO__
    - Você pode usar o comando de duas formas: 
        - Inserir em uma ordem específica (você especifica as colunas):
            ```SQL
            INSERT INTO nome_da_tabela (coluna_1, coluna_2, coluna_n)
            VALUES (valor_1, valor_2, valor_n);
            ```
        - Inserir seguindo a ordem padrão das colunas (certifique-se que os valores __ESTÃO NA MESMA ORDEM__ das colunas):
            ```SQL
            INSERT INTO nome_da_tabela 
            VALUES (valor_1, valor_2, valor_n);
            ```

- O comando UPDATE
    - Usado para editar/atualizar linhas específicas na tabela.
    - Importante: A clásula WHERE espeficia uma condição para atualização. Uma vez esquecida, todos os dados da tabela serão atualizados.
    - Sintaxe:
        ```SQL
        UPDATE nome_da_tabela
        SET coluna_1 = valor_1, coluna_2 = valor_2, coluna_n = valor_n 
        WHERE condição; 
        ```

- O comando DELETE
    - Usado para deletar linas específicas na tabela.
    - Use sempre junto com a clásula __WHERE__, pois sem ela o comando __DELETE__ pode apagar o banco de dados inteiro.
    - Sintaxe:
        ```SQL
            DELETE FROM nome_da_tabela 
            WHERE condicao;
        ```
- O comando GROUPBY
    - Usado para agrupar linhas que tem os mesmos valores em linhas de resumo.
    - Para realizar o agrupamento, o __GROUP BY__ depende de uma _função de agregação_: COUNT, MAX, MIN, SUM, AVG.
    - Sintaxe:
        ```SQL
            SELECT funcao_agregacao(coluna_x) coluna_n 
            FROM nome_da_tabela
            GROUP BY coluna_n
        ```

### Chave estrangeira

- Chave estrangeira, também conhecido como ___foreign key___, é uma chave que tem como função ligar duas tabelas, quando o conteudo é complementar.
- Por exemplo, vamos supor que temos a seguinte tabela de clientes de uma loja:

    ID_usuário | Nome | Idade
    --  | -- | --
    1 | João | 45
    2 | Maria | 52
    3 | Carlos | 27

- E temos o seguinte problema: Precisamos criar uma tabela que associe __um ou mais__ ordem de serviços.
- Podemos, então, criar uma tabela que apresente a descrição de uma ordem de serviço:

    ID_servico | Descricao | Aparelho
    --  | -- | --
    1 | Máquina não funciona | Notebook Acer
    2 | Fonte queimada | PC Gamer
    3 | Troca de memória | Desktop 
    4 | Reparo preventivo | Notebook Sansung

- Como podemos associar as duas tabelas, sendo que cada __serviço__ deve ser associado a um __usuário__? Vamos criar uma nova chave estrangeira com o nome __ID_usuário__:

    ID_servico | Descricao | Aparelho | ID_Usuario
    --  | -- | -- | --
    1 | Máquina não funciona | Notebook Acer | 1
    2 | Fonte queimada | PC Gamer | 1
    3 | Troca de memória | Desktop | 3
    4 | Reparo preventivo | Notebook Sansung | 2
