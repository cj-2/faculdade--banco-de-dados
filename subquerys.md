# Subquery ou Inner Query

A subquery é um comando de `select` dentro de outro comando `select`, que pode retornar
uma ou mais linhas com o objetivo de stisfazer uma condição do `where`.

Exemplo:

    // Query principal
    Quais funcionarios possuem um salário maior que o de Abel?

    // Subquery
    Qual o salário de Abel?

É necessário primeiro saber o salário do Abel para fazer um a verificação de quem
possui um salário maior que o dele, sabendo disso, podemos fazer:

```sql
select last_name, salary from EMPLOYEES
where salary > (
    select salary from EMPLOYEES 
    where last_name = 'Abel'
)
```

Outros Exemplos:

Moster o sobrenome e o cargo dos funcionarios que possuem o mesmo cargo que 
o funcionario com o id de número 150.

```sql
select last_name, job_id from EMPLOYEES
where job_id = (
    select job_id from EMPLOYEES
    where employee_id = 150
)

```

## Operadores de comparação para múltiplas linhas.

| Operador | Significado                                            |
| -------- | ------------------------------------------------------ |
| IN       | Igual a qualquer membro da lista.                      |
| ANY      | Qualquer um da lista.                                  |
| ALL      | Compara com todos os valores retornados pela subquery. |
| EXISTS   | Trata se um valor existe na list.                      |

### ANY

A expressão:

A condição de comparação ANY é usada para comparar um valor a uma lista 
ou consulta. Ele deve ser precedido por: =, !=, >, <, <=, >= E seguidos 
por uma lista ou consulta também.

Fonte: http://aprendaplsql.com/oracle/operadores-oracle-any-all-some-como-eles-funcionam/

```sql
select empno, sal 
from emp
where sal > ANY(2000, 3000, 4000);
```

Equivale:

```sql
select empno, sal 
from emp
where sal > 2000 or sal > 3000 or sal > 4000;
```

### ALL

Parecido com o ANY, porem é interpretado como um `AND`.

```sql
select empno, sal 
from emp
where sal > ALL(2000, 3000, 4000);
```

Equivale:

```sql
select empno, sal 
from emp
where sal > 2000 and sal > 3000 and sal > 4000;
```

## Funções de Decisão

### DECODE

Temos duas formas de trabalhar com condição dentro de consultas em `Oracle SQL`, 
são elas o Case e o Decode. Os dois tem a mesma função, que é permitir de forma 
dinâmica e pratica como obter um retorno de uma coluna com base em uma condição, 
ou seja, ter a possibilidade de usar condições semelhantes ao IF-THEN-ELSE em 
consultas.

https://www.devmedia.com.br/decode-x-case/4952

```sql
select first_name, job_id,
decode (
    job_id, -- condição ou coluna  
        'IT_PROG', -- se for igual
        'PROGAMADOR', -- se for igual
        'FI_ACCOUNT', -- se for igual
        'CONTADOR', -- se for igual
        'INDEFINIDO' -- caso nada tenha sido igual
) decode_cargo -- nome da coluna que recebe o decode.
```

A coluna `decode_cargo` só terá os valores definidos nas strings, com o último sendo o padrão.

### CASE

Permite o processamento de condicionais com várias hipóteses.

```sql
select first_name, job_id, salary,
    case
        when salary < 5000
            then 'AUMENTO' -- retorna
        when salary > 10000
            then 'VERIFICAR' -- retorna
        else 'NÃO AUMENTAR' -- padrao
    END classificacao -- nome da coluna que rece o case.
from EMPLOYEES
```