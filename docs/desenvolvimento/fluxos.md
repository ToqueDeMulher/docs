# Fluxos Principais do Sistema

**Última atualização:** 20 de setembro de 2026
**Referência:** implementação atual dos repositórios de frontend e backend.

Este documento descreve as principais jornadas da plataforma Toque de Mulher, incluindo a comunicação entre frontend, backend, banco de dados e serviços externos.

Os fluxos apresentados representam a arquitetura e o comportamento documentados do sistema. Quando uma etapa ainda depende de implementação complementar ou validação integrada, essa condição é indicada explicitamente.

## 1. Visão geral dos fluxos

| Fluxo | Finalidade |
| --- | --- |
| Cadastro e login | Criar contas e autenticar usuários |
| Consulta do usuário autenticado | Recuperar informações da conta com acesso autorizado |
| Carrinho e compra | Selecionar produtos e iniciar a finalização do pedido |
| Pagamento | Iniciar o checkout da Stripe e processar o resultado do pagamento |
| Administração | Controlar o acesso às funcionalidades administrativas |
| Estoque | Registrar entradas, ajustes e movimentações relacionadas aos produtos |

## Cadastro e login

### Cadastro

1. O usuário acessa a tela de cadastro.
2. O frontend coleta os dados informados.
3. Os dados são enviados à API do backend.
4. O backend valida as informações recebidas.
5. A senha é protegida por hash criptográfico.
6. O sistema registra a conta do usuário.
7. O frontend apresenta o resultado do cadastro.

### Login convencional

1. O usuário informa suas credenciais.
2. O frontend envia os dados à API.
3. O backend valida as credenciais.
4. Em caso de autenticação válida, o backend gera um access token.
5. O token é identificado com `type=access`.
6. O frontend recebe o token e mantém a sessão conforme a implementação atual.
7. O usuário passa a acessar os recursos protegidos permitidos para sua conta.

### Login com Google

1. O usuário inicia a autenticação com Google.
2. O fluxo de autenticação é processado pela integração correspondente.
3. O backend valida as informações necessárias.
4. Em caso de autenticação válida, o backend retorna um access token.
5. O frontend utiliza o token para acessar os recursos protegidos.

### Atualização técnica da autenticação

Em setembro de 2026, o fluxo de refresh token foi removido do frontend e do backend porque não havia um mecanismo ativo de renovação utilizando esse token.

O frontend passou a trabalhar apenas com access token e a limpar eventuais refresh tokens antigos que permanecessem armazenados localmente.

O backend passou a identificar os access tokens com `type=access` e a rejeitar tokens de outros tipos nas rotas protegidas.

**Importante:** a remoção do refresh token não significa que o access token tenha validade ilimitada. O comportamento após sua expiração deve seguir o fluxo efetivamente implementado e ser incluído nos testes de autenticação.

## Consulta do usuário autenticado

### Etapas

1. O usuário acessa uma área privada, como o perfil.
2. O frontend envia o access token na requisição à API.
3. O backend valida a autenticidade e o tipo do token.
4. O sistema identifica o usuário associado ao token.
5. O backend verifica as permissões necessárias.
6. Os dados permitidos são retornados.
7. O frontend apresenta as informações na interface.

### Regras de segurança

* O usuário deve possuir autenticação válida.
* Tokens de outros tipos não devem ser aceitos como access token.
* Um usuário não deve conseguir consultar informações privadas de outra conta sem autorização.
* O frontend não substitui as verificações de autenticação e autorização realizadas pelo backend.

## Fluxo de compra

### Etapas

1. O usuário navega pelo catálogo.
2. Seleciona um produto.
3. Adiciona o produto ao carrinho.
4. Pode alterar quantidades ou remover itens.
5. O frontend apresenta os valores correspondentes aos itens selecionados.
6. O usuário inicia o checkout.
7. O sistema reúne os dados necessários para a compra.
8. O backend valida as informações recebidas.
9. O backend verifica a disponibilidade dos produtos e a validade do endereço utilizado.
10. O sistema inicia a operação de checkout e pagamento.
11. O usuário prossegue para o ambiente de pagamento.
12. O resultado do pagamento é processado pelo backend.
13. Os registros de pedido e pagamento são atualizados conforme o resultado da operação.

### Pontos de atenção

A existência do carrinho, do checkout e da integração com pagamento não comprova, isoladamente, que todos os cenários da compra foram validados de ponta a ponta.

A integração entre confirmação de pagamento, atualização do pedido e movimentação automática de estoque permanece como ponto de acompanhamento específico.

## Fluxo de pagamento

### Etapas

1. O usuário inicia o checkout no frontend.
2. O frontend envia os dados necessários ao backend.
3. O backend valida as informações da compra, incluindo endereço e disponibilidade de estoque.
4. O backend cria a operação de checkout na Stripe.
5. O sistema registra as informações de pagamento necessárias à operação.
6. O frontend direciona o usuário ao Stripe Hosted Checkout.
7. O usuário conclui ou interrompe o pagamento.
8. A Stripe envia os eventos correspondentes ao backend por meio de webhook.
9. O backend processa o evento recebido e atualiza os registros pertinentes.
10. O frontend apresenta o resultado da jornada conforme o estado retornado pela aplicação.

### Regras importantes

* A confirmação do pagamento não deve depender exclusivamente do redirecionamento do navegador.
* O backend deve processar os eventos recebidos da Stripe conforme as regras implementadas.
* Os dados do pagamento devem permanecer associados à operação correspondente.
* A movimentação de estoque deve respeitar o estado efetivo da compra e evitar alterações duplicadas.

### Decisão de integração

A implementação atual utiliza Stripe Hosted Checkout.

A descrição histórica de uma task de frontend mencionava Stripe Elements. Caso a equipe decida manter Hosted Checkout como solução oficial, a task correspondente deve ser atualizada para refletir essa decisão.

## Fluxo administrativo

### Etapas

1. O administrador acessa uma rota administrativa.
2. O frontend verifica a condição de autenticação e a permissão necessária para apresentar a área.
3. As requisições às funcionalidades administrativas são enviadas ao backend com o access token.
4. O backend valida o token e a autorização do usuário.
5. O administrador acessa as operações permitidas.
6. Pode gerenciar produtos, fornecedores e estoque conforme as funcionalidades disponíveis.
7. O backend valida os dados recebidos.
8. As alterações são persistidas no banco de dados.
9. O frontend atualiza as informações apresentadas.

### Upload de imagem de produto

O upload de imagem de produto integra o gerenciamento administrativo.

Após a revisão de segurança de setembro de 2026, o endpoint de upload passou a exigir permissão administrativa no backend.

A proteção da rota no frontend contribui para a experiência de navegação, mas não substitui a autorização exigida pela API.

### Dashboard administrativo

O dashboard administrativo apresenta informações da operação, incluindo dados reais relacionados a pedidos e pagamentos, conforme os endpoints integrados.

## Fluxo de estoque

A gestão de estoque utiliza três estruturas principais:

| Estrutura | Responsabilidade |
| --- | --- |
| `Stock` | Armazenar a quantidade atual de um produto |
| `StockBatch` | Registrar lotes de entrada, incluindo informações relacionadas a fornecedor, custo e validade quando aplicável |
| `StockMovement` | Registrar o histórico de movimentações do estoque |

Os tipos de movimentação previstos são `IN`, `OUT`, `ADJUSTMENT` e `RETURN`.

### 7.1. Entrada de estoque - `IN`

1. O administrador registra uma entrada de produtos.
2. O backend valida o fornecedor e os produtos informados.
3. O sistema localiza ou cria o registro principal de estoque, conforme necessário.
4. A quantidade disponível é atualizada.
5. Um lote é registrado em `StockBatch`.
6. A movimentação de entrada é registrada em `StockMovement`.

### Consulta e ajuste - `ADJUSTMENT`

1. O administrador consulta o estoque de um produto.
2. O backend retorna as informações disponíveis.
3. Quando necessário, o administrador informa um ajuste.
4. O backend valida a nova quantidade.
5. O saldo é atualizado.
6. A movimentação de ajuste é registrada no histórico.

O sistema deve impedir quantidades negativas, conforme as regras de integridade implementadas.

### Saída relacionada à compra - `OUT`

**Situação:** integração automática ainda precisa de conclusão e validação.

O comportamento esperado é:

1. O sistema confirma o evento da compra que determina a saída do estoque.
2. Identifica os produtos e as quantidades envolvidos.
3. Registra a movimentação `OUT`.
4. Atualiza o saldo disponível.
5. Mantém a referência ao pedido correspondente.
6. Impede que o mesmo evento gere baixa duplicada.

O momento exato da baixa deve seguir a regra oficial adotada pela equipe para o ciclo de pagamento.

### Cancelamento ou expiração do pagamento

**Situação:** regra de restauração ainda precisa de conclusão e validação.

Quando uma compra for cancelada ou um pagamento expirar, o sistema deve verificar se houve reserva ou redução anterior do estoque.

Caso exista quantidade a restaurar, a operação deve seguir a regra definida para recomposição do saldo, preservando o histórico e evitando devoluções duplicadas.

Se não houve redução ou reserva anterior, o sistema não deve acrescentar estoque indevidamente.

### Devolução - `RETURN`

**Situação:** movimentação ainda precisa de conclusão e validação.

O fluxo esperado é:

1. Uma devolução é registrada conforme as regras do negócio.
2. O backend identifica o pedido e os produtos correspondentes.
3. Valida as quantidades elegíveis para retorno ao estoque.
4. Registra a movimentação `RETURN`.
5. Atualiza o saldo quando aplicável.
6. Preserva a rastreabilidade da operação.

## Segurança e integridade nos fluxos

A revisão técnica de setembro de 2026 reforçou controles utilizados em diferentes jornadas da plataforma.

### Autenticação e autorização

* Access tokens são identificados com `type=access`.
* Tokens de outros tipos não autenticam usuários nas rotas protegidas.
* O upload de imagem de produto exige autorização administrativa no backend.

### Tratamento de erros

Respostas de erro relacionadas ao Supabase foram ajustadas para reduzir a exposição de detalhes internos.

### Integridade do banco de dados

Foram adicionadas ou reforçadas validações para evitar:

* quantidades negativas;
* preços negativos;
* múltiplos endereços padrão quando a regra exigir unicidade;
* múltiplos métodos de pagamento padrão quando a regra exigir unicidade.

Essas regras devem ser verificadas nos testes de integração e regressão.

---

## Situação de implementação e validação

| Fluxo | Estado documentado | Validação a acompanhar |
| --- | --- | --- |
| Cadastro e login | Implementados; autenticação simplificada para access token | Login convencional, Google, expiração e rejeição de tokens inadequados |
| Consulta do usuário | Implementação existente | Autenticação, autorização e dados retornados |
| Carrinho | Implementação existente | Consistência de itens, quantidades e valores |
| Checkout e Stripe | Integração com Hosted Checkout e processamento de webhook existentes | Cenários completos de sucesso, falha, cancelamento e atualização de registros |
| Administração | Área administrativa e proteção de acesso existentes | Autorização no frontend e backend |
| Upload de imagem | Implementação existente; autorização administrativa reforçada | Upload permitido para administrador e negado para usuário sem permissão |
| Estoque | Entradas, consultas, ajustes, lotes e movimentações existentes | Saída automática, cancelamento, expiração, devolução e consistência com pedidos |

**Nota:** esta tabela registra o estado informado e as verificações necessárias. Resultados de testes devem ser vinculados às respectivas evidências, sem presumir aprovação de cenários que ainda não foram comprovados.

## Próximas validações prioritárias

1. Confirmar o funcionamento do login convencional e do login com Google após a remoção do refresh token.
2. Verificar o comportamento da aplicação quando o access token expirar.
3. Testar a rejeição de tokens de outros tipos nas rotas protegidas.
4. Confirmar a autorização administrativa no upload de imagem.
5. Validar o checkout e o processamento dos eventos da Stripe.
6. Concluir e testar a movimentação `OUT` relacionada às compras.
7. Validar restauração de estoque em cancelamentos e expirações, quando aplicável.
8. Concluir e testar a movimentação `RETURN`.
9. Executar testes de regressão nas funcionalidades afetadas pela limpeza técnica.
