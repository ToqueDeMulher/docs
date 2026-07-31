# Fluxos Principais do Sistema

Os fluxos principais representam as jornadas mais importantes executadas na plataforma Toque de Mulher.

Eles envolvem a comunicação entre frontend, backend, banco de dados e serviços externos.

## Cadastro e login

1. O usuário acessa a tela de cadastro ou login.
2. O frontend coleta os dados informados.
3. Os dados são enviados para a API backend.
4. O backend valida as informações recebidas.
5. No cadastro, a senha é protegida por hash criptográfico.
6. No login, o backend verifica as credenciais.
7. Em caso de autenticação válida, o sistema gera um token JWT.
8. O frontend mantém a sessão do usuário autenticado.
9. O usuário passa a acessar recursos protegidos.

## Consulta do usuário autenticado

1. O frontend envia o token de autenticação.
2. O backend valida o token.
3. O sistema identifica o usuário associado.
4. Os dados permitidos são retornados.
5. O frontend apresenta as informações no perfil.

## Fluxo de compra

1. O usuário navega pelo catálogo.
2. Seleciona um produto.
3. Adiciona o produto ao carrinho.
4. O usuário pode alterar quantidades ou remover itens.
5. A plataforma calcula os valores do carrinho.
6. O usuário inicia o checkout.
7. O sistema valida os dados da compra.
8. O backend verifica a disponibilidade dos produtos.
9. O pedido é criado.
10. O pagamento é iniciado.
11. O serviço de pagamento processa a transação.
12. O status do pedido é atualizado após a confirmação.
13. O estoque deve ser atualizado de acordo com a compra.

## Fluxo de pagamento

1. O backend cria a solicitação de pagamento.
2. Os dados são enviados ao Mercado Pago.
3. O serviço externo retorna as informações da transação.
4. O usuário conclui ou interrompe o pagamento.
5. O Mercado Pago envia uma confirmação ou webhook.
6. O backend valida a notificação.
7. O status do pagamento é atualizado.
8. O status do pedido também é atualizado.

## Fluxo administrativo

1. O administrador acessa a área administrativa.
2. O sistema verifica o token de autenticação.
3. A permissão administrativa é validada.
4. O administrador acessa as funcionalidades permitidas.
5. Ele pode cadastrar ou alterar produtos.
6. Pode gerenciar fornecedores.
7. Pode registrar movimentações de estoque.
8. As alterações são persistidas no banco.
9. O catálogo deve refletir os dados atualizados.

## Fluxo de estoque

1. Um produto é cadastrado ou associado ao estoque.
2. A quantidade disponível é registrada.
3. Entradas e saídas geram movimentações.
4. O sistema atualiza o saldo.
5. Durante uma compra, a disponibilidade deve ser validada.
6. Após a confirmação do pedido, o estoque deve ser reduzido.
7. Alterações administrativas devem permanecer registradas.

## Situação de validação

Os fluxos de registro, login e consulta do usuário autenticado possuem integração documentada como funcional.

Os fluxos de catálogo, endereço, pedidos, pagamento e baixa automática de estoque ainda precisam de evidências completas de validação de ponta a ponta.