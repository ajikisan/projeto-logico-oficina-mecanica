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
