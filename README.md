# Refinando um projeto conceitual de banco de dados para E-commerce

## Projeto elaborado para mostrar de forma gráfica e visual o funcionamento de um banco de dados para E-commerce

## Legendas:

# 📌 Relações e Cardinalidades

|Entidade 1| Relacionamento | Entidade 2 |Cardinalidade|	                                   Explicação                                             |
|----------|----------------|------------|-------------|-------------------------------------------------------------------------------------------|
| Cliente	 |    Possui	    | Endereço	 |    1:N	     | Um cliente pode ter vários endereços, mas cada endereço pertence a um único cliente       |
|----------|----------------|------------|-------------|-------------------------------------------------------------------------------------------|
| Pedido	 |É realizado por | Cliente	   |    N:1	     | Um cliente pode fazer vários pedidos, mas cada pedido pertence a um único cliente         |
|----------|----------------|------------|-------------|-------------------------------------------------------------------------------------------|
| Pedido	 |    Tem	        | Produto	   |    N:M	     | Um pedido pode conter vários produtos, e um mesmo produto pode estar em vários pedidos    |
|----------|----------------|------------|-------------|-------------------------------------------------------------------------------------------|
| Pedido	 |    Tem	        | Pagamento  |    1:N	     | Um pedido pode ter múltiplos pagamentos (ex.: parcelamento), mas cada pagamento pertence  |
|          |                |            |             | a um único pedido                                                                         |
|----------|----------------|------------|-------------|-------------------------------------------------------------------------------------------|
| Pedido	 |    Tem um      | Endereço   |    1:1	     | Cada pedido tem um único endereço de entrega                                              |
|----------|----------------|------------|-------------|-------------------------------------------------------------------------------------------|
| Produto	 |    Tem um	    | Fornecedor |	   N:1	   | Um produto tem apenas um fornecedor, mas um fornecedor pode fornecer vários produtos      |
|----------|----------------|------------|-------------|-------------------------------------------------------------------------------------------|
| Produto	 |    Está em     | Estoque	   | 1:1 ou 1:N	 | Se o estoque for centralizado, é 1:1. Se houver múltiplos locais de estoque, é 1:N        |
|----------|----------------|------------|-------------|-------------------------------------------------------------------------------------------|
| Produto	 |    Pode ter	  | Recall	   |    1:N	     | Um produto pode ter múltiplos recalls, mas cada recall pertence a um único produto        |
|----------|----------------|------------|-------------|-------------------------------------------------------------------------------------------|
| Produto	 | É vendido por	| Vendedor	 |    N:M	     | Um produto pode ser vendido por diferentes vendedores, e um vendedor pode vender vários   |
|          |                |            |             | produtos. Para isso, há a entidade associativa Produto_Vendedor                           |
|----------|----------------|------------|-------------|-------------------------------------------------------------------------------------------|
| Entrega	 |Está associada a|	Pedido	   |    1:1	     | Cada pedido tem uma única entrega                                                         |
|----------|----------------|------------|-------------|-------------------------------------------------------------------------------------------|
| Entrega	 |     Tem	      | Status     |    1:1	     | Cada entrega tem um status e um código de rastreamento único                              |
|          |                | e Código   |             |                                                                                           |
|          |                | de Rastreio|             |                                                                                           |
|----------|----------------|------------|-------------|-------------------------------------------------------------------------------------------|
                                    
# 📝 Notas Importantes

- A relação Produto_Vendedor é uma entidade associativa para representar a relação N:M entre Produto e Vendedor.

- O Pedido pode estar vinculado a mais de um pagamento (caso haja parcelamento ou múltiplas formas de pagamento).

- O Estoque pode ser 1:1 ou 1:N, dependendo da forma como ele é gerenciado.

- A Entrega está vinculada ao Pedido (1:1) porque um pedido tem um único processo de entrega.
