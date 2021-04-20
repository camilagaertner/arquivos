Tabelas usadas no exemplo de cada comando SQL:


---------------TABELA MARCA----------
CREATE TABLE Marca (
	id INT NOT NULL AUTO_INCREMENT,
  	descricao VARCHAR(256) NOT NULL,
         PRIMARY KEY (id),
         UNIQUE (descricao)
);

---------------TABELA TAMANHO----------
CREATE TABLE Tamanho (
	id INT NOT NULL AUTO_INCREMENT,
  	sigla VARCHAR(4) NOT NULL,
  	descricao VARCHAR(256),
         PRIMARY KEY (id),
         UNIQUE (sigla)
);


---------------TABELA COR----------
CREATE TABLE Cor (
	id INT NOT NULL AUTO_INCREMENT,
  	hexa VARCHAR(6) NOT NULL,
  	descricao VARCHAR(256),
         PRIMARY KEY (id),
         UNIQUE (hexa)
);


---------------TABELA TIPO----------
CREATE TABLE Tipo (
	id INT NOT NULL AUTO_INCREMENT,
  	descricao VARCHAR(256) NOT NULL,
         PRIMARY KEY (id),
         UNIQUE (descricao)
);


---------------TABELA CATALOGO----------
CREATE TABLE Catalogo (
	id INT AUTO_INCREMENT NOT NULL,
	id_marca INT NOT NULL,
  	id_tamanho INT NOT NULL,
  	id_cor INT NOT NULL,
  	id_tipo INT NOT NULL,
  	preco DECIMAL NOT NULL,
  	PRIMARY KEY (id),
  	FOREIGN KEY (id_marca) REFERENCES Marca(id),
         FOREIGN KEY (id_tamanho) REFERENCES Tamanho(id),
         FOREIGN KEY (id_cor) REFERENCES Cor(id),
         FOREIGN KEY (id_tipo) REFERENCES Tipo(id),
	UNIQUE (id_marca, id_tamanho, id_cor, id_tipo)
);
