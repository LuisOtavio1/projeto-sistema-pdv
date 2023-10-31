# API PDV (Ponto de Venda)

## Sobre o Projeto

Este é um projeto piloto de uma API para um PDV (Frente de Caixa) com a capacidade de gerenciar categorias, clientes, pedidos, produtos e usuários. A API possui funcionalidades robustas, incluindo cadastro, atualização, listagem e exclusão de itens relacionados ao PDV.

**Importante:** A API segue rigorosamente as validações de requisições e as respostas contém códigos de erro e mensagens adequadas.

## Como Usar

Antes de começar, certifique-se de instalar todas as dependências necessárias executando:

```bash
npm install
```

## Banco de Dados

Para utilizar a API, é necessário criar um banco de dados PostgreSQL. O arquivo SQL contendo os comandos de criação das tabelas e inserção das categorias está disponível no projeto.

## Endpoints Principais

### Usuários

- `POST` `/usuario`: Cadastra um novo usuário no sistema.
- `POST` `/login`: Permite o login de um usuário cadastrado.

### Produtos

- `POST` `/produto`: Cadastra um novo produto no sistema.
- `PUT` `/produto/:id`: Atualiza as informações de um produto existente.
- `GET` `/produto`: Lista todos os produtos cadastrados, com opção de filtrar por categoria.
- `GET` `/produto/:id`: Obtém detalhes de um produto específico.
- `DELETE` `/produto/:id`: Exclui um produto do sistema (não é permitido se estiver vinculado a um pedido).

### Clientes

- `POST` `/cliente`: Cadastra um novo cliente no sistema.
- `PUT` `/cliente/:id`: Atualiza informações de um cliente existente.
- `GET` `/cliente`: Lista todos os clientes cadastrados.
- `GET` `/cliente/:id`: Obtém detalhes de um cliente específico.

### Pedidos

- `POST` `/pedido`: Cadastra um novo pedido no sistema, incluindo produtos vinculados.
- `GET` `/pedido`: Lista todos os pedidos cadastrados, com opção de filtrar por cliente.
  
## Recurso Adicional
- **Imagens de Produto:** É possível vincular uma imagem a um produto. O campo `produto_imagem` é opcional e, se fornecido, a imagem é processada e armazenada em um servidor de armazenamento, com a URL retornada na resposta.

**ATENÇÃO:** Durante a exclusão de produtos, a imagem vinculada ao produto é automaticamente removida do servidor de armazenamento.
