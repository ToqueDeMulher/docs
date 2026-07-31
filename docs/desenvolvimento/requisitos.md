# Requisitos do Sistema

Este documento apresenta os requisitos funcionais e não funcionais da plataforma Toque de Mulher.

A existência de um requisito nesta documentação não significa que ele esteja totalmente implementado ou validado. O estado real das funcionalidades deve ser consultado em [Status Atual da Implementação](../introducao/status_atual.md).

## Requisitos funcionais

| Código | Descrição |
|---|---|
| RF001 | Permitir cadastro e autenticação de usuários |
| RF002 | Permitir visualização e edição de perfil |
| RF003 | Disponibilizar catálogo de produtos com categorias e filtros |
| RF004 | Permitir adicionar, remover e atualizar itens no carrinho |
| RF005 | Permitir finalização de compras por meio do checkout |
| RF006 | Integrar meios de pagamento online |
| RF007 | Gerenciar pedidos e seus respectivos status |
| RF008 | Controlar estoque automaticamente |
| RF009 | Permitir avaliações de produtos |
| RF010 | Disponibilizar painel administrativo para gestão da plataforma |

## Detalhamento dos requisitos funcionais

### RF001 — Cadastro e autenticação de usuários

O sistema deve permitir que novos usuários realizem cadastro e que usuários cadastrados façam login utilizando suas credenciais.

### RF002 — Perfil do usuário

O usuário autenticado deve poder visualizar e editar seus dados de perfil.

### RF003 — Catálogo de produtos

A plataforma deve exibir os produtos disponíveis, organizados por categorias, com recursos de busca e filtragem.

### RF004 — Carrinho de compras

O usuário deve poder adicionar produtos ao carrinho, remover itens e atualizar quantidades.

### RF005 — Checkout

O sistema deve disponibilizar um processo de finalização da compra com validação dos produtos, endereço e pagamento.

### RF006 — Pagamento online

A aplicação deve integrar um serviço externo de pagamento para processar as transações.

### RF007 — Gerenciamento de pedidos

O sistema deve registrar pedidos e permitir o acompanhamento de seus respectivos status.

### RF008 — Controle de estoque

A plataforma deve controlar a disponibilidade dos produtos e registrar movimentações de estoque.

### RF009 — Avaliações de produtos

Os usuários devem poder registrar avaliações e comentários relacionados aos produtos.

### RF010 — Painel administrativo

Administradores devem possuir acesso a funcionalidades de gestão de produtos, pedidos, estoque e fornecedores.

## Requisitos não funcionais

| Código | Tipo | Descrição |
|---|---|---|
| RNF001 | Performance | Manter baixo tempo de resposta nas operações principais |
| RNF002 | Usabilidade | Garantir interface intuitiva e responsiva |
| RNF003 | Segurança | Proteger autenticação e dados sensíveis |
| RNF004 | Manutenibilidade | Facilitar manutenção e evolução do sistema |
| RNF005 | Escalabilidade | Suportar crescimento de usuários e transações |
| RNF006 | Confiabilidade | Garantir integridade dos dados e das operações |

## Detalhamento dos requisitos não funcionais

### Performance

As operações principais devem apresentar tempo de resposta adequado, especialmente login, consulta ao catálogo, checkout e pedidos.

### Usabilidade

A interface deve ser intuitiva, responsiva e adequada a computadores, tablets e celulares.

### Segurança

A aplicação deve proteger credenciais, tokens de autenticação, dados pessoais e informações relacionadas a pagamentos.

### Manutenibilidade

A organização do sistema deve facilitar correções, inclusão de funcionalidades e evolução dos módulos.

### Escalabilidade

A arquitetura deve permitir o crescimento da quantidade de usuários, produtos, pedidos e transações.

### Confiabilidade

O sistema deve preservar a consistência dos dados, especialmente em operações de pagamento, pedidos e movimentações de estoque.

## Rastreabilidade

O acompanhamento dos requisitos deve considerar:

- a documentação de escopo;
- o estado atual da implementação;
- as entregas registradas nas sprints;
- as evidências de testes;
- as divergências entre planejamento e código.