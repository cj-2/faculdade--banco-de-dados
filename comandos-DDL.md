# DDL - Data Definition Language

Significa "Linguagem de definição de dados". DDL é uma linguagem usada para definir estruturas 
de dados e modificar dados. Por exemplo, os comandos DDL podem ser usados ​​para adicionar, 
remover ou modificar tabelas dentro de um banco de dados.

Fonte: https://techlib.wiki/definition/ddl.html

```sql
-- Criação da Tabela
create table PAIS (
    cd_pais number (2),
    nm_pais char (45),
    ds_nacionalidade char(35),
    constraint pais_cd_pais_pk primary key (cd_pais),
    constraint pais_nm_pais_uk unique (nm_pais)
)

-- Insert
insert into PAIS (cd_pais, nm_pais) values (1, 'Brasil')
insert into PAIS (cd_pais, nm_pais, ds_nacionalidade) values (2, 'Argentina', null)
insert into PAIS (cd_pais, nm_pais, ds_nacionalidade) values (3, 'Portugal', null)

-- Update
update PAIS set nm_pais = 'Brasil', ds_nacionalidade = 'Brasileiro' where cd_pais = 1

-- Delete
delete from PAIS where cd_pais = 3

-- Seleção
select * from PAIS
select cd_pais, nm_pais from PAIS
select cd_pais "Número", nm_pais "Nome" from PAIS

-- Seleção sem duplicatas e ordenadas
select distinct nm_pais from PAIS order by nm_pais

-- Selecão verificando uma lista
select fist_name from employees where manege_id in (101, 102, 103)

-- Listando itens que comecem com 'Bra'
select nm_pais from PAIS where nm_pais like 'Bra%'

-- Pesquisas com múltiplas condições.
select first_name, last_name from EMPLOYEES where salary between 2000 and 3000 and job_id = 'ST_CLERK'

```

## Where

A clásula **WHERE** inidica a condição para o **SELECT**.

### Operadores Boolenaos

| Operador | Descrição      |
| -------- | -------------- |
| =        | Igual          |
| <>       | Diferente      |
| \>       | Maior          |
| <        | Menor          |
| \>       | Maior ou igual |
| <=       | Menor ou igual |

#### Operadores SQL

| Operador            | Descrição                              |
| ------------------- | -------------------------------------- |
| between ... and ... | Compara uma faixa de valores           |
| in (lista)          | Comparar uma lista de valroes          |
| like                | Compara parâmetro alfanumérico (texto) |
| is null             | É um valor nulo                        |

Utilizando: Oracle