# Criação do modelo lógico

              --comando para criar banco de
```sql
CREATE DATABASE microblog CHARACTER SET utf8mb4;
```


## Criação da tabela usuario

``` sql
CREATE TABLE usuario(
    id INT NOT NULL AUTO_INCREMENT PRIMARY KEY,
    nome VARCHAR(100) NOT NULL,
    email VARCHAR(150) NOT NULL UNIQUE,
    senha VARCHAR(255) NOT NULL,
    tipo_usuario ENUM('admin', 'editor') NOT NULL
);
```

 
## Criação da tabela categoria

``` sql
    CREATE TABLE categoria (
    id INT NOT NULL PRIMARY KEY AUTO_INCREMENT,
    nome VARCHAR(100)NOT NULL

);
```

## Criação da tabela noticia


``` sql
CREATE TABLE noticia (
     id INT NOT NULL PRIMARY KEY AUTO_INCREMENT,
    titulo VARCHAR(200) NOT NULL,
    resumo TEXT NOT NULL,
    texto_completo TEXT NOT NULL,
    nome_imagem VARCHAR(100) NOT NULL,

    -- Automaticamente obter a data/hora e registrar
    data_publicacao DATETIME NOT NULL DEFAULT DATETIME,
    destaque ENUM('sim', 'nao') NOT NULL,

    -- Nomeclatura recomendada
    -- nometabelasingular_nomecolunapk
    id_usuario INT NOT NULL,
    id_categoria INT NOT NULL,

    -- Cria relacionamentos e chave estrangeira (FK)
    -- Caso um usuario seja excluido, as notícias ficarão setadas como null
    -- (ou seja, sem associação com nenhum usúario)
    FOREIGN KEY (id_usuario) REFERENCES usuario (id) ON DELETE SET NULL,
    FOREIGN KEY (id_categoria) REFERENCES categoria (id) ON DELETE SET NULL
);
```