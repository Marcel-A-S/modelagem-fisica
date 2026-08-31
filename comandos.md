# Referências de comandos SQL para modelagem Física

## Criação do banco de dados

```sql
CREATE DATABASE flybynight CHARACTER SET utf8mb4;
```


## Criação databela fornecedor

``` sql


CREATE TABLE fornecedor(
    id INT PRIMARY KEY AUTO_INCREMENT,
    nome VARCHAR(100) NOT NULL
);



```