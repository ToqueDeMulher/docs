# Fluxos Principais do Sistema

**Última atualização:** 22 de novembro de 2026  
**Referência:** implementação dos repositórios de frontend e backend e histórico de alterações até novembro de 2026.

Este documento descreve as principais jornadas da plataforma Toque de Mulher, incluindo a comunicação entre frontend, backend, banco de dados e serviços externos.

Os fluxos apresentados representam o comportamento documentado do sistema. Etapas que ainda dependem de validação integrada são identificadas separadamente.

---

## 1. Visão geral dos fluxos

| Fluxo | Finalidade |
|---|---|
| Cadastro e login | Criar contas e autenticar usuários. |
| Consulta do usuário autenticado | Recuperar informações da conta com acesso autorizado. |
| Catálogo e carrinho | Consultar produtos, verificar disponibilidade e organizar a compra. |
| Checkout e compra | Validar os dados da compra e iniciar o pagamento. |
| Pagamento | Processar operações com AbacatePay e receber eventos por webhook. |
| Frete e envio | Processar informações de entrega e operações relacionadas ao envio. |
| Administração | Controlar o acesso às funcionalidades administrativas. |
| Estoque | Registrar entradas, saídas, ajustes e movimentações relacionadas aos produtos. |

---

## 2. Cadastro e login

O fluxo de autenticação permite que o usuário crie uma conta ou acesse a plataforma utilizando suas credenciais.

A implementação utiliza access token, sem o fluxo anterior de refresh token.

### Cadastro

1. O usuário acessa a tela de cadastro.
2. O frontend coleta os dados informados.
3. Os dados são enviados à API do backend.
4. O backend valida as informações recebidas.
5. A senha é protegida por hash criptográfico.
6. O sistema registra a conta do usuário.
7. O frontend apresenta o resultado do cadastro.
8. O usuário segue o processo de confirmação de e-mail conforme as regras implementadas.

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
2. O fluxo é processado pela integração correspondente.
3. O backend valida as informações necessárias.
4. Em caso de autenticação válida, retorna um access token.
5. O frontend utiliza o token para acessar os recursos protegidos.

### Recuperação e redefinição de senha

1. O usuário solicita a recuperação de acesso.
2. O sistema inicia o processo de recuperação conforme a implementação do backend.
3. O usuário utiliza o mecanismo disponibilizado para redefinir sua senha.
4. O backend valida a solicitação e aplica as regras de segurança.
5. A senha é atualizada.
6. As sessões e os tokens afetados pela alteração são tratados conforme os mecanismos de revogação implementados.
7. O usuário realiza uma nova autenticação quando necessário.

### Atualizações de segurança

Em setembro de 2026, o fluxo de refresh token foi removido do frontend e do backend.

Em outubro e novembro, foram registradas melhorias relacionadas a:

- confirmação de e-mail;
- recuperação de senha;
- vinculação de tokens às contas e às versões de senha;
- gerenciamento de sessões após redefinição de senha;
- testes de regressão de autenticação.

A remoção do refresh token não significa que o access token tenha validade ilimitada. Seu comportamento após a expiração deve ser verificado conforme a implementação atual.

---

## 3. Consulta do usuário autenticado

Este fluxo permite recuperar informações da conta de um usuário autenticado.

### Etapas

1. O usuário acessa uma área privada, como o perfil.
2. O frontend envia o access token na requisição à API.
3. O backend valida a autenticidade e o tipo do token.
4. O sistema identifica o usuário associado.
5. O backend verifica as permissões necessárias.
6. Os dados permitidos são retornados.
7. O frontend apresenta as informações na interface.

### Regras de segurança

- O usuário deve possuir autenticação válida.
- Tokens de outros tipos não devem ser aceitos como access token.
- Informações privadas devem permanecer protegidas por verificações de autorização.
- O frontend não substitui as verificações realizadas pelo backend.

### Avatar do usuário

A implementação recebeu integração com Supabase Storage para persistência de avatares.

O fluxo envolve o envio da imagem, seu processamento conforme as regras do backend e a associação do arquivo à conta correspondente.

---

## 4. Catálogo e carrinho

O catálogo permite consultar produtos disponíveis e selecionar itens para compra.

### Consulta de produtos

1. O usuário acessa a loja ou uma categoria.
2. O frontend solicita as informações ao serviço de catálogo.
3. O serviço realiza a comunicação com a API.
4. O backend consulta os dados necessários.
5. A API retorna as informações dos produtos.
6. O frontend apresenta os resultados.
7. Estados de carregamento e falha são tratados pela interface.

### Carrinho

1. O usuário seleciona um produto.
2. A interface verifica as condições de disponibilidade.
3. O produto é adicionado ao carrinho.
4. O usuário pode alterar as quantidades.
5. O frontend atualiza os valores apresentados.
6. O usuário pode remover itens quando desejar.
7. O sistema organiza os dados necessários para o checkout.

### Atualizações de novembro

O frontend recebeu melhorias relacionadas a:

- validação de produtos sem estoque;
- gerenciamento de quantidades;
- prevenção da remoção involuntária da última unidade;
- responsividade do carrinho;
- tratamento dos dados utilizados no checkout.

As validações do frontend complementam as verificações do backend, mas não devem ser consideradas suficientes para garantir a disponibilidade de um produto.

---

## 5. Fluxo de compra e checkout

O fluxo de compra conecta o catálogo, o carrinho, os dados de entrega e o processamento de pagamento.

### Etapas

1. O usuário navega pelo catálogo.
2. Seleciona os produtos desejados.
3. Adiciona os itens ao carrinho.
4. Ajusta as quantidades.
5. Inicia o checkout.
6. Informa ou confirma os dados necessários para a compra.
7. O sistema utiliza as informações de endereço e entrega.
8. O frontend envia os dados da operação ao backend.
9. O backend valida os produtos, as quantidades e as demais informações recebidas.
10. O sistema inicia a operação de pagamento.
11. O usuário prossegue conforme o fluxo disponibilizado pelo provedor.
12. O backend processa os eventos relacionados ao pagamento.
13. Os registros da compra são atualizados conforme o resultado da operação.

### Integração com endereço

O frontend recebeu melhorias para aproveitar o CEP informado anteriormente no carrinho durante o preenchimento do endereço no checkout.

Essa integração busca reduzir o preenchimento repetitivo e manter a consistência dos dados de entrega.

### Pontos de atenção

A validação do checkout deve considerar:

- disponibilidade dos produtos;
- consistência das quantidades;
- validade dos dados da compra;
- estado do pagamento;
- prevenção de operações duplicadas;
- integração com estoque e envio.

A conclusão operacional do fluxo depende da validação dos cenários de compra.

---

## 6. Fluxo de pagamento com AbacatePay

Em novembro de 2026, foi incorporada uma integração com AbacatePay para operações de checkout e processamento de pagamentos.

### Etapas

1. O usuário inicia o checkout no frontend.
2. O frontend envia os dados necessários ao backend.
3. O backend valida as informações da compra.
4. O serviço de pagamento cria a operação correspondente no AbacatePay.
5. O backend registra os dados necessários para acompanhar a operação.
6. O frontend apresenta ou utiliza as informações retornadas para continuidade do pagamento.
7. O usuário conclui ou interrompe a operação.
8. O AbacatePay envia os eventos correspondentes ao endpoint de webhook.
9. O backend processa os eventos recebidos.
10. Os registros de pagamento e as operações relacionadas são atualizados conforme o resultado.

### Regras importantes

- A confirmação do pagamento não deve depender exclusivamente de uma resposta visual no frontend.
- Os eventos recebidos por webhook devem ser validados conforme as regras implementadas.
- Os registros de pagamento devem permanecer associados à operação correspondente.
- O sistema deve evitar processamento duplicado de eventos e operações.
- As etapas posteriores de estoque e envio devem considerar o estado efetivo do pagamento.

### Atualizações técnicas

As alterações registradas incluem:

- serviço de integração com AbacatePay;
- endpoint de webhook;
- atualizações nos modelos e esquemas de pagamento;
- adaptação das operações de checkout;
- migração relacionada aos pagamentos;
- tratamento de eventos e respostas;
- correções relacionadas a solicitações simultâneas de checkout;
- testes de integração.

### Integrações anteriores

A documentação de setembro descrevia Stripe Hosted Checkout.

A integração com AbacatePay foi incorporada posteriormente. A situação da Stripe deve ser confirmada no código antes de ser classificada como removida ou descontinuada.

---

## 7. Fluxo de frete e envio

O fluxo de envio relaciona as informações de entrega, o estado do pagamento e as operações necessárias para o processamento do frete.

### Etapas gerais

1. O usuário informa os dados necessários para entrega.
2. O sistema utiliza as informações do endereço e da compra.
3. O backend processa as operações de frete disponíveis.
4. As informações necessárias são retornadas à aplicação.
5. O usuário prossegue com a finalização da compra.
6. O pagamento é processado.
7. Antes da preparação e do pagamento da etiqueta, o backend revalida o estado do pagamento.
8. As operações de envio prosseguem conforme as regras implementadas.

### Atualizações de novembro

Foram registradas melhorias relacionadas a:

- integração dos serviços de envio;
- atualização das operações de frete;
- documentação técnica da integração;
- revalidação do pagamento AbacatePay antes da preparação e do pagamento de etiquetas.

### Pontos de atenção

O fluxo deve impedir que operações de envio dependentes de pagamento confirmado sejam executadas com base em estados incorretos ou desatualizados.

A validação integrada deve considerar os cenários de pagamento aprovado, pendente, cancelado ou expirado, conforme os estados efetivamente suportados.

---

## 8. Fluxo administrativo

A área administrativa reúne funcionalidades de gerenciamento da plataforma e deve ser acessível somente a usuários autorizados.

### Etapas

1. O administrador acessa uma rota administrativa.
2. O frontend verifica a condição de autenticação e a permissão necessária para apresentar a área.
3. As requisições são enviadas ao backend com o access token.
4. O backend valida o token e a autorização do usuário.
5. O administrador acessa as operações permitidas.
6. Pode gerenciar produtos, fornecedores e estoque conforme as funcionalidades disponíveis.
7. O backend valida os dados recebidos.
8. As alterações são persistidas no banco de dados.
9. O frontend atualiza as informações apresentadas.

### Gerenciamento de produtos

A aplicação possui funcionalidades administrativas relacionadas ao cadastro e gerenciamento de produtos.

As atualizações de outubro incluíram melhorias na integração entre o painel e a API de catálogo.

### Upload de imagem de produto

O upload de imagem integra o gerenciamento administrativo.

O endpoint exige permissão administrativa no backend.

A proteção da rota no frontend contribui para a navegação, mas não substitui a autorização exigida pela API.

### Dashboard administrativo

O dashboard apresenta informações da operação, incluindo dados relacionados a pedidos e pagamentos conforme os endpoints integrados.

---

## 9. Fluxo de estoque

A gestão de estoque utiliza estruturas para armazenar saldos, registrar lotes e manter o histórico de movimentações.

| Estrutura | Responsabilidade |
|---|---|
| `Stock` | Armazenar a quantidade atual de um produto. |
| `StockBatch` | Registrar lotes de entrada e informações relacionadas. |
| `StockMovement` | Registrar o histórico de movimentações. |

Os tipos de movimentação previstos incluem `IN`, `OUT`, `ADJUSTMENT` e `RETURN`.

### Entrada de estoque - `IN`

1. O administrador registra uma entrada de produtos.
2. O backend valida as informações recebidas.
3. O sistema identifica o registro de estoque correspondente.
4. A quantidade disponível é atualizada.
5. Os dados do lote são registrados quando aplicável.
6. A movimentação é registrada no histórico.

### Consulta e ajuste - `ADJUSTMENT`

1. O administrador consulta o estoque.
2. O backend retorna as informações disponíveis.
3. Quando necessário, o administrador solicita um ajuste.
4. O backend valida a operação.
5. O saldo é atualizado.
6. A movimentação é registrada.

### Saída relacionada à compra - `OUT`

O fluxo de saída de estoque está relacionado ao processamento das compras.

O comportamento esperado envolve:

1. identificação do evento da compra;
2. identificação dos produtos e quantidades;
3. validação do saldo;
4. registro da movimentação de saída;
5. atualização do estoque;
6. associação da operação ao pedido;
7. prevenção de baixas duplicadas.

As alterações de novembro incluíram melhorias na consistência dos saldos e no tratamento de operações concorrentes.

A execução completa desse fluxo deve ser confirmada pelos testes de integração.

### Cancelamento ou expiração

Quando uma operação de pagamento é cancelada ou expira, o sistema deve verificar se houve reserva ou redução anterior do estoque.

A recomposição do saldo, quando aplicável, deve preservar o histórico e evitar operações duplicadas.

Se não houve redução ou reserva anterior, não deve ocorrer acréscimo indevido de estoque.

### Devolução - `RETURN`

O fluxo de devolução deve identificar os produtos e quantidades envolvidos, validar a operação e registrar a movimentação correspondente.

A conclusão e a validação desse cenário devem ser acompanhadas conforme as regras implementadas.

### Melhorias de integridade

As atualizações de novembro incluíram:

- bloqueio e atualização dos saldos antes de alterações;
- testes de regressão para movimentações;
- migração para correção de registros de estoque ausentes;
- reforço das validações de valores monetários.

---

## 10. Segurança e integridade nos fluxos

A aplicação utiliza mecanismos de autenticação, autorização e validação de dados.

### Autenticação e autorização

- Access tokens são identificados com `type=access`.
- Tokens de outros tipos não devem autenticar usuários nas rotas protegidas.
- O upload de imagem de produto exige autorização administrativa.
- Os mecanismos de recuperação de senha receberam melhorias de segurança.
- Foram registradas alterações relacionadas à vinculação de tokens às contas e às versões de senha.

### Tratamento de erros

Respostas relacionadas a serviços internos devem evitar a exposição de informações sensíveis.

A revisão técnica também incluiu ajustes no tratamento de erros e respostas de integrações externas.

### Integridade do banco de dados

Foram adicionadas ou reforçadas validações relacionadas a:

- quantidades negativas;
- preços negativos;
- registros padrão de endereços;
- registros padrão de métodos de pagamento;
- valores monetários;
- consistência de saldos;
- operações concorrentes.

---

## 11. Situação de implementação e validação

| Fluxo | Estado documentado | Validação a acompanhar |
|---|---|---|
| Cadastro e login | Implementados, com melhorias de segurança. | Login, confirmação de e-mail, recuperação de senha e expiração de tokens. |
| Consulta do usuário | Implementação existente, com melhorias no gerenciamento de contas. | Autenticação, autorização e dados retornados. |
| Catálogo | Integrado à API, com melhorias de gerenciamento. | Consulta, busca, disponibilidade e administração. |
| Carrinho | Implementado e revisado. | Quantidades, valores e disponibilidade. |
| Checkout | Atualizado e integrado ao serviço de pagamento. | Cenários completos de compra. |
| AbacatePay | Integração e webhook implementados. | Processamento dos eventos e resultados dos testes. |
| Frete e envio | Serviços e operações atualizados. | Cotação, preparação e pagamento de etiquetas. |
| Administração | Área administrativa e proteção de acesso existentes. | Autorização no frontend e backend. |
| Upload de imagem | Implementação existente, com autorização administrativa. | Validação de arquivos e permissões. |
| Estoque | Funcionalidades existentes com melhorias de consistência. | Concorrência, baixa, cancelamento, expiração e devolução. |

**Nota:** a tabela registra o estado identificado nas alterações do projeto. A aprovação dos testes deve ser confirmada pelos resultados de execução e pelas evidências disponíveis.

---

## 12. Próximas validações prioritárias

1. Confirmar o funcionamento do login convencional e do login com Google.
2. Validar confirmação de e-mail e recuperação de senha.
3. Verificar o comportamento após a expiração ou revogação de tokens.
4. Confirmar a autorização administrativa nas operações protegidas.
5. Validar a integração do catálogo com a API.
6. Testar os cenários completos de checkout e pagamento com AbacatePay.
7. Verificar o processamento de webhooks e a prevenção de operações duplicadas.
8. Validar as operações de frete e envio.
9. Confirmar a consistência das movimentações de estoque em operações concorrentes.
10. Validar cancelamentos, expirações e devoluções conforme as regras implementadas.
11. Consultar os resultados dos testes automatizados e workflows de CI.