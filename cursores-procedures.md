# Cursores e Procedures

## PL/SQL

A `Program Language SQL` é a linguagem de programação da `Oracle` que objetvia
processar informações no banco de dados e possibilita a criação programas completos 
que operam dentro dos bancos de dados. 

Possibilitando:

- A utilização de `if`, `while` e `for` dentro dos códigos.
- A criação de variáveis
- A criação de cursores para tratamento de resultados de queries.
- A criação de registros para armazenamento dos cursores
- Tratar erros

### Sintaxe

- `DECLARE` (opcional) - Comando de declaração
  - Variáveis, cursores, constantes, tabelas, estruturas e exceptions.
- `BEGIN` (obrigatório) - Abre o código
- `EXCEPTION` (opcional) - Usado para abrir uma tratativa de error.
- `END` (obrigatório) - Fecha o código.

## Cursores

São áreas compostas de linhas e colunas em memoria (como uma tabela virtual) 
que servem para armazenar o resultado de uma seleção que retorne 0 ou mais linhas.

A busca dos dados é linha por linha do cursor.

Links de Referência

- https://www.redspark.io/cursor-no-sql-server/

## Stored Procedure

É um subprograma que é compilado e armazenado no servidor, e que pode ser chamado
a partir de um comando SQL.

- São blocos de PL/SQL armazenados no banco de dados de forma compiladas.
- Podem ou não receber parâmetros

    Stored Procedure, que traduzido significa Procedimento Armazenado, 
    é uma conjunto de comandos em SQL que podem ser executados de uma só vez, 
    como em uma função. Ele armazena tarefas repetitivas e aceita parâmetros 
    de entrada para que a tarefa seja efetuada de acordo com a necessidade individual.

Fonte: https://www.devmedia.com.br/introducao-aos-stored-procedures-no-sql-server/7904