# Modelo Físico de Dados (MFD)

## Descrição do MFD
Este arquivo apresenta o Modelo Físico de Dados (MFD) para um sistema de gerenciamento de pedidos e entregas. Ele foi projetado para atender os seguintes requisitos principais:
- Gerenciar usuários com diferentes tipos (cliente, gestor, cozinha, motoboy).
- Categorização de pratos (prato principal, sobremesa, bebida).
- Registro de pedidos e itens associados.
- Rastreamento de entregas realizadas por motoboys.

O modelo é composto pelas seguintes tabelas:

- **Usuário**: Contém informações de todos os usuários do sistema, incluindo clientes e funcionários.
- **Categoria**: Define as categorias de pratos.
- **Prato**: Representa os pratos disponíveis, com preços e categorias associadas.
- **Pedido**: Armazena os pedidos realizados pelos clientes.
- **Itens do Pedido**: Lista os itens relacionados a um pedido.
- **Entrega**: Controla as entregas realizadas por motoboys.

## Estrutura das Tabelas
Cada tabela possui os seguintes atributos principais:

### Usuário
- `id_usuario` (PK): Identificador único do usuário.
- `nome`: Nome do usuário.
- `tipo`: Tipo de usuário (cliente, gestor, cozinha, motoboy).


### Categoria
- `id_categoria` (PK): Identificador único da categoria.
- `nomeCat`: Nome da categoria.

### Prato
- `id_prato` (PK): Identificador único do prato.
- `nomePrato`: Nome do prato.
- `preco`: Preço do prato.
- `imagem_url`: URL da imagem do prato.
- `id_categoria` (FK): Identificador da categoria associada.

### Pedido
- `id_pedido` (PK): Identificador único do pedido.
- `id_cliente` (FK): Identificador do cliente associado.
- `status`: Status do pedido (enviado, em preparo, para entrega, entregue).


### Itens do Pedido
- `id_item` (PK): Identificador único do item.
- `id_pedido` (FK): Identificador do pedido associado.
- `id_prato` (FK): Identificador do prato associado.
- `quantidade`: Quantidade do prato.
- `pratoTotal`: Preço de todos os pratos.

### Entrega
- `id_entrega` (PK): Identificador único da entrega.
- `id_pedido` (FK): Identificador do pedido associado.
- `id_motoboy` (FK): Identificador do motoboy responsável pela entrega.
- `endereco_cliente`: Endereço do cliente.

## Passos para Execução no MySQL

1. Certifique-se de que o MySQL está instalado e funcionando corretamente em sua máquina.

2. Abra o MySQL Workbench ou outro cliente de sua preferência.

3. Crie um banco de dados para o projeto:
   ```sql
   CREATE DATABASE sistema_pedidos;
   USE sistema_pedidos;
   ```

4. Execute o script SQL (DDL) que cria as tabelas e define os relacionamentos. Certifique-se de que o script está salvo em um arquivo `.sql` ou copie e cole diretamente no cliente MySQL.

5. Verifique se as tabelas foram criadas corretamente:
   ```sql
   SHOW TABLES;
   ```

6. Insira dados iniciais ou utilize scripts de testes para validar o funcionamento do banco de dados.

