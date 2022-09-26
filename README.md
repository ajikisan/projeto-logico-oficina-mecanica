[oficina.sqlite.zip](https://github.com/ajikisan/projeto-logico-oficina-mecanica/files/9642568/oficina.sqlite.zip)
### Desafio Construa um Projeto Lógico de Banco de Dados do Zero - Oficina Mecânica
<p>Aluna: Mirian Ajiki Molicawa </p>
<p>Digital Innovation One </p>
<p>Instrutora:Juliana Mascarenhas </p>

<h2> Tecnologias </h2>
<br> - [x] Navegador Google Chrome
<br> - [x] ![SQL Online IDE](https://sqliteonline.com/) 
<br> - [x] ![BD Oficina-Mecânica](https://github.com/ajikisan/bd_oficina_mecanica/)

<h2>Criação de Tabelas</h2>
<b>Cliente</b>
<p>
create table clientes (
ID_Cliente integer auto_increment,
Nome_Cliente varchar(255),
CPF varchar(11),
Endereco varchar(250),
Telefone integer(15),
Email varchar(200),
RG integer,
Data_Cadastro date);


<p>
<b>Mecanico</b>
create table mecanicos (
ID_Mecanico integer auto_increment,
Codigo_Mecanico integer,
Nome_Mecanico varchar(255),
Endereco varchar(255),
Telefone integer(15),
Especialidade varchar(255));
<p>

<b>Endereco</b>
create table enderecos (
ID_Endereco integer auto_increment,
Bairro varchar(100),
Cidade varchar(100),
Estado varchar(100),
CEP varchar(10),
Complemento varchar(255),
ID_Cliente integer);
<p>
<b>Veiculo e Moto</b>
create table veiculo_moto (
ID_Veiculo_Moto integer auto_increment,
Marca varchar(255),
Modelo varchar(255),
Ano_Fabricacao date,
Nome_Cliente varchar(255),
ID_Cliente integer);
<p>

<b>Ordem_Servico</b>
create table ordem_servico (
ID_Ordem_Servico integer auto_increment,
Descricao varchar(255),
Valor_Ordem_Servico float,
Data_Emissao_OS date,
Forma_Pagamento varchar(45),
Status_Ordem_Servico varchar(45),
Numero_Ordem_Servico integer,
Data_Conclusao_OS date,
Tipo_Ordem_Servico varchar(255),
Autorizacao_OS boolean default false,
Valor_Pagamento_OS float,
ID_Cliente integer,
ID_Mecanico integer);
<p>

<b>Produtos_Automotivos</b>
create table produto_automotivo (
ID_Produto_Automotivo integer auto_increment,
Descricao_Produto varchar(255),
Categoria_Produto varchar(255),
Valor_Produto float,
Quantidade integer(3),
ID_Cliente integer);

<b>Servicos_Automotivos</b>
create table servicos_automotivos (
ID_Servico_Automotivo integer auto_increment,
Descricao_Servico_Automotivo varchar(255),
Valor_Servico_Automotivo float,
Data_Servico_Automotivo date,
ID_Cliente integer);

<b>Mao_Obra</b>
create table mao_obra (
ID_Mao_Obra integer auto_increment,
Descricao_Mao_Obra varchar(255),
Data_Mao_Obra date,
Valor_Total float,
ID_Ordem_Servico integer,
ID_Produto_Automotivo integer,
ID_Servico_Automotivo integer,
ID_Cliente integer);




![BD_Oficina_Mecanica](https://user-images.githubusercontent.com/91148791/192184340-786e298a-4d23-4513-9c11-b41e7235bfec.png)


Inserção de Valores
-- Tabela de Clientes
insert into clientes (
ID_Cliente,
Nome_Cliente,
CPF, 
Endereco,
Email,
Telefone,
RG,
Data_Cadastro)
VALUES (1,
'Fulano', '29724237044',
'Endereco', 'fulano@email.com',
'216545555',265177583,
'25012022');

Insert INTO clientes
VALUES (2,
'Sicrano', '54917136008',
'Endereco 2', 'sicrano@email.com',
'546545575', 431449983,'29012021');

Insert INTO clientes
VALUES (3,
'Beltrano', '88914588050',
'Endereco 2', 'beltrano@email.com',
'1165445585', 190723671,'31012022');  

=====
Inserção de Mecânicos

INSERT into mecanicos (
ID_Mecanico,
Codigo_Mecanico,
Nome_Mecanico,
Endereco,
Telefone,
Especialidade)
Values (1, 100, 'Joao', 'Rua da Oficina', 146546546,'Limpeza de bicos injetores');

INSERT into mecanicos 
Values (2, 101,'Paulo', 'Rua da Oficina', 146546587,'Troca de Escapamentos');

  INSERT into mecanicos 
Values (3, 102, 'Marcos', 'Rua da Oficina', 146546125,'Troca de Pneus');

  INSERT into mecanicos 
Values (4, 102, 'Thiago', 'Rua da Oficina', 146546125,'Motos e Carros');


==========
--Inserção na Tabela de Endereços
Insert into enderecos (
ID_Endereco,
Bairro,
Cidade,
Estado,
CEP,
Complemento,
ID_Cliente)
VALUES (
1, 'Moreninhas', 'Campo Grande', 'MS', 79000-000, 'Casa Condomínio', 1); 
  
 Insert into enderecos Values ( 
  2, 'Taquarussu', 'Corumbá', 'SP', 780700-000, 'Em frente ao Shopping', 2);
 
  Insert into enderecos Values (   
  3, 'São Bento', 'Goiânia', 'GO', 79000-000, 'Casa Condomínio', 3);

========

--Inserção na Tabela de Veículos e Motos
Insert into veiculo_moto (
ID_Veiculo_Moto,
Marca,
Modelo,
Ano_Fabricacao,
Nome_Cliente,
ID_Cliente)
VALUES(1, 'Chevrolet','Onix','01012020','Fulano',1) 

Insert into veiculo_moto
VALUES(2, 'Honda','Biz','01032021','Sicrano',2)

Insert into veiculo_moto
VALUES(3, 'Toyota','Prius','02052022','Beltrano',3)    


==

-- Inserção na tabela Ordem de Serviço
insert into ordem_servico (
ID_Ordem_Servico,
Descricao,
Valor_Ordem_Servico ,
Data_Emissao_OS,
Forma_Pagamento ,
Status_Ordem_Servico,
Numero_Ordem_Servico,
Data_Conclusao_OS,
Tipo_Ordem_Servico,
Autorizacao_OS,
Valor_Pagamento_OS,
ID_Cliente,
ID_Mecanico)

Values(1,'óleo vencido',80.00,'01092022','Cartão Crédito','Concluído', 2001, '01092022','Servico', true, 80.00, 1, 1);

Values(2,'escapamento emanando fumaça cinza',150.00, '03092022','Transferência Eletrônica','Concluído', 2003, '03092022', 'Produto',true, 150.00, 2, 4);
       
Values(3,'pneu furado',1700.00, '02092022','Pix', 'Concluído', 2002, '02092022', 'Produto',true, 1700.00, 3, 3);

 Values(4,'escapamento rachado',450.00, '04092022','Pix', 'Concluído', 2002, '04092022', 'Produto',true, 450.00, 3, 2);

=======

--Inserção na tabela de Produto Automotivo
Insert into produto_automotivo (
ID_Produto_Automotivo,
Descricao_Produto,
Categoria_Produto,
Valor_Produto,
Quantidade,
ID_Cliente)
Values (1, 'Pneu Aro 13', 'Automotivo', 330.00, 5, 3);

Insert into produto_automotivo
Values (2, 'Bico Injetor', 'Automotivo', 775, 1, 1);

Insert into produto_automotivo
Values (3, 'Óleo 20W50 Mobil Super Api Sl 1L', 'Automotivo', 40.00, 2, 2);

Insert into produto_automotivo
Values (4, 'Escapamento Moto Pro Tork Powercore 3 Steel Technology XR 250 Tornado', 'Automotivo', 370.00, 1,2);

=======
--Inserção na tabela de Serviços Automotivos

Insert into servicos_automotivos (
ID_Servico_Automotivo,
Descricao_Servico_Automotivo,
Valor_Servico_Automotivo,
Data_Servico_Automotivo,
ID_Cliente)
Values
( 1, 'Troca de óleo do carro', 30.00, '01092022', 1);

Insert into servicos_automotivos
VAlues ( 2, 'Troca de 5 pneus de carro', 50.00, '02092022', 3);

Insert into servicos_automotivos
VAlues ( 3, 'Troca de 2 pneus de moto', 50.00, '02092022', 2);

Insert into servicos_automotivos
Values (4, 'Escapamento Moto Pro Tork Powercore 3 Steel Technology XR 250 Tornado', 
        'Automotivo', 80.00, 2);
