# Comandos CRUD SLQ

## Resumo da sigla
- C = CREATE (INSERT, Inserir dodos)
- R = READ (SELECT, leitura de dados)
- U = UPDATE (UPDATE, atualizar dados)
- D = DELETE (DELETE, excluir dados)

## INSERT fabricantes (versão completa)
INSERT into fabricantes(nome) VALUES('Asus');
INSERT into fabricantes(nome) VALUES('Dell');
INSERT into fabricantes(nome) VALUES('Aple');
INSERT into fabricantes(nome) VALUES('LG');

### INSERT fabricantes (versão simplificada)
INSERT into fabricantes(nome)
VALUES('Samsung'),('Microsoft'), ('Brastemp');



## INSERT produtos
INSERT into produtos(nome, preco, quantidade, descricao, fabricante_id)
VALUES('TV Led', 2000, 5, 'TV de última geração', 5);

INSERT into produtos(nome, preco, quantidade, descricao, fabricante_id)
VALUES('iPhone', 5500.79, 8, 'Smartphone caro pra caramba', 3);


INSERT INTO produtos(nome, preco, quantidade, descricao, fabricante_id) VALUES
(
    'Geladeira',
    1500,
    10,
    'Refrigerador Frost-free com acesso à Internet das Coisas e bla bla bla',
    7 -- Brastemp
),
(
    'iPad Mini',
    5000,
    8,
    'Tablet Apple com tela retina display de 4k, memória interna de 64GB, acesso ao iCloud.',
    3 -- Apple
),
(
    'Xbox',
    2500,
    6,
    'Console de última geração com acesso aos melhores jogos e bla bla',
    6 -- Microsoft
),
(
    'Ultrabook',
    4500.68,
    12,
    'Equipamento com processador AMD Ryzen5, 12GB de RAM, placa de vídeo RTX',
    1 -- Asus
),
(
    'Headset',
    120,
    9,
    'Fone de ouvido USB com alta qualidade',
    6 -- Microsoft
),
(
    'Tablet Android',
    4999,
    3,
    'Tablet com a versão 12 do sistema operacional da Google, possui tela de 10 polegadas e armazenamento de 64GB.',
    5 -- Samsung
);



## SELECT (simples)
SELECT nome, preco FROM produtos;

SELECT nome, preco FROM produtos WHERE preco < 3000 and preco > 2000

SELECT nome, preco FROM produtos 
WHERE fabricante_id = 3 or fabricante_id = 1;

SELECT nome, descricao FROM produtos ORDER BY nome; -- Ordem crescente (PADRÃO)

SELECT nome, descricao FROM produtos ORDER BY preco DESC; -- Ordem decrescente

## Selecionar duas tabelas juntas (INNER JOIN e ON)Indicar maneira como as tabelas são juntadas

## Comando que permite dar apelido para as colunas (AS)
SELECT 
    produtos.nome AS Produto, 
    fabricantes.nome AS Fabricante, 
    produtos.preco AS Preço, 
    produtos.quantidade AS Quantidade
    FROM produtos INNER JOIN fabricantes
    ON produtos.fabricante_id = fabricantes.id;


## UPDATE
UPDATE fabricantes SET nome = 'LG do Brasil'
WHERE id = 4; -- SEMPRE use WHERE e SEMPRE dê uma CONDIÇÃO!!

## DELETE
DELETE FROM produtos WHERE id = 5; -- SEMPRE use WHERE e SEMPRE dê uma CONDIÇÃO!!