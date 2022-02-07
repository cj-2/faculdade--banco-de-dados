# Alterando Tabelas

Acrescentar campos em uma tabela

    ALTER TABLE CLIENTE
    ADD ( IE_FISICA_JURIDICA CHAR(1))

Alterando obrigatoriedade de atributos em uma tabela.

    ALTER TABLE CLIENTE
    MODIFY (nm_cliente not null);

Modificando o tipo de atributos em uma tabela.

    ALTER TABLE CLIENTE
    MODIFY (DS_ENDERECO NUMBER(3));

Modificando o tamanho dos atributos em uma tabela.

    ALTER TABLE CLIENTE
    MODIFY (NR_CEP VARCHAR2(12));

Acrescentar restrições a uma tabela.

    ALTER TABLE CLIENTE
    ADD(CONSTRAINT CLIENTE_IE_FISICA_JURIDICA_CK
    CHECK(IE_FISICA_JURIDICA IN(‘F’,’J’)));

Desabilitar uma restrição de uma tabela.

    ALTER TABLE CLIENTE
    DISABLE CONSTRAINT CLIENTE_IE_FISICA_JURIDICA_CK;

Excluir uma restrição de uma tabela.

    ALTER TABLE CLIENTE
    DROP CONSTRAINT CLIENTE_IE_FISICA_JURIDICA_CK

Exclusão de Tabela

    DROP TABLE CLIENTE