# DML - Data Manipulation Language

Linguagem de Manipulação de Dados ( DML, de Data Manipulation Language) é uma família de 
linguagens de computador utilizada para a recuperação, inclusão, remoção e modificação de 
informações em bancos de dados.

Fonte: https://pt.wikipedia.org/wiki/Linguagem_de_manipula%C3%A7%C3%A3o_de_dados

```sql
-- Acrescentar campos em uma tabela
alter table CLIENTE
add ( IE_FISICA_JURIDICA char(1))

-- Alterando obrigatoriedade de atributos em uma tabela.
alter table CLIENTE
modify (nm_cliente not null);

-- Modificando o tipo de atributos em uma tabela.
alter table CLIENTE
modify (DS_ENDERECO number(3));

-- Modificando o tamanho dos atributos em uma tabela.
alter table CLIENTE
modify (NR_CEP varchar2(12));

-- Acrescentar restrições a uma tabela.
alter table CLIENTE
add(constraint CLIENTE_IE_FISICA_JURIDICA_CK
check(IE_FISICA_JURIDICA IN(‘F’,’J’)));

-- Desabilitar uma restrição de uma tabela.
alter table CLIENTE
disable constraint CLIENTE_IE_FISICA_JURIDICA_CK;

-- Excluir uma restrição de uma tabela.
alter table CLIENTE
drop constraint CLIENTE_IE_FISICA_JURIDICA_CK

-- Exclusão de Tabela
drop table CLIENTE

-- Modicando o nome da tabela.
rename PAIS to GRANDES_ILHAS

create table COPIA_PAIS as select * from PAIS
```

Utilizando: Oracle