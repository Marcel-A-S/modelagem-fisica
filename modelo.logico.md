# Criação do modelo lógico


```sql
CREATE DATABASE microblog CHARACTER SET utf8mb4;
```


## Criação da tabela usuario

``` sql
CREATE TABLE usuario(
    id INT NOT NULL AUTO_INCREMENT PRIMARY KEY,
    nome VARCHAR(100) NOT NULL,
    email TEXT,
    senha DECIMAL(10, 2) NOT NULL,
    tipo_usuario INT NOT NULL
);
```

 
## Criação da tabela noticia

``` sql
CREATE TABLE noticia(
    id INT NOT NULL PRIMARY KEY AUTO_INCREMENT,
    titulo VARCHAR(200) NOT NULL,
    resumo VARCHAR(500)NOT NULL,
    texto_completo TEXT NOT NULL,
    nome_imagem VARCHAR(100) NOT NULL,
    data_publicacao DATETIME NOT NULL,
    destaque ENUM('sim', 'nao') NOT NULL,
    id_usuario INT NOT NULL,
    id_categoria INT NOT NULL,

    FOREIGN KEY (id_categoria) REFERENCES usuario (id),
    FOREIGN KEY (id_categoria) REFERENCES categoria (id)
);
```

## Criação da tabela categoria


``` sql
CREATE TABLE categoria (
    id INT NOT NULL,
    nome VARCHAR(100)NOT NULL

);
```



