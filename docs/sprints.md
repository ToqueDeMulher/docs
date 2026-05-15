# Acompanhamento das Sprints

Documento consolidado em **15 de maio de 2026** com base nos commits, branches e artefatos versionados nos repositórios do projeto Toque de Mulher.

## Fontes consultadas

| Repositório | Branches relevantes | Uso como evidência |
|---|---|---|
| `toquedemulher-frontend` | `main`, `feat/frontend-pages`, `feat/dark-mode-themes`, `feat/accessibility-audit`, `feat/navegacao` | Interface web, catálogo, carrinho, checkout, autenticação, área administrativa, busca, tema e acessibilidade |
| `toquedemulher-backend` | `main`, `feature/backend-base`, `fix/updating-dependency-versions`, `dependabot/pip/python-jose-3.4.0` | API FastAPI, autenticação, pagamentos, usuários, endereços, fornecedores, estoque e coleções Bruno |
| `docs` | `main`, `backup/main-before-rewrite`, `backup/main-before-remove-0c7ceec` | Documentação executiva, escopo, roadmap, status técnico, riscos e glossário |
| `.github` | `main` | Perfil institucional, badges e apresentação pública da organização |

> Observação: não foram localizados arquivos de ata de Daily Scrum nem registros formais de ALM além do próprio Git/GitHub e da coleção Bruno. Por isso, os itens de reunião diária abaixo ficam documentados como evidência por commit quando possível e como pendência quando exigem registro manual.

Links dos repositórios usados como ALM/evidência:

- Frontend: <https://github.com/ToqueDeMulher/toquedemulher-frontend>
- Backend: <https://github.com/ToqueDeMulher/toquedemulher-backend>
- Documentação: <https://github.com/ToqueDeMulher/docs>

## Visão geral por sprint

| Sprint | Período inferido pelos commits | Foco principal | Status |
|---|---|---|---|
| Sprint #01 | 05/02/2026 a 23/02/2026 | Estrutura inicial do produto, documentação e base do frontend/backend | Concluída com pendência de atas |
| Sprint #02 | 08/03/2026 a 16/03/2026 | Fluxos essenciais: usuário, login, pagamento, checkout, dashboard e documentação consolidada | Concluída com pendência de atas |
| Sprint #03 | 23/03/2026 a 23/04/2026 | Busca, endereço, refinamento de checkout, estoque inicial, temas, acessibilidade e correções de segurança | Concluída com pendência de atas |
| Sprint #04 | 25/04/2026 a 09/05/2026 | Fornecedores, associação fornecedor-produto, estoque, movimentação de estoque e controle administrativo | Em validação |

## Sprint #01

### Objetivo da sprint

Criar a base do projeto, organizar a documentação inicial e iniciar as estruturas técnicas de frontend e backend.

### Branches e commits de evidência

| Repositório | Branch | Evidências |
|---|---|---|
| `docs` | `main` | `4cb344d` roadmap com KPIs e fases; `54ce3c5` roadmap e guia de contribuição |
| `toquedemulher-frontend` | `main` | `643c0ae` frontend inicial; `4b39695` ignore de build e VSCode; `5c19ac2` refatoração de estrutura |
| `toquedemulher-backend` | `main` | `76215cd` estrutura feature-based do backend |
| `.github` | `main` | `4de5bad`, `9f80c6e`, `bb17108` ajustes de README, banner e badges |

### Desenvolvimento da sprint

- Tarefas do Sprint Backlog em execução: documentação base, organização de repositórios e início da aplicação web.
- Funcionalidades implementadas e testadas: estrutura inicial de frontend e backend; ainda sem evidência de teste automatizado.
- Atualizações registradas no ALM: commits versionados no GitHub.
- Backlog ajustado: roadmap e guia de contribuição atualizados no repositório `docs`.

### Artefatos produzidos

- Histórias de usuários documentadas: não localizadas em arquivo específico.
- Critérios de aceitação definidos: não localizados em arquivo específico.
- Protótipos atualizados: sem arquivo de wireframe/mockup localizado no repositório.
- Regras de negócio revisadas: escopo, roadmap e documentação inicial.

### Testes e validação

- Testes funcionais realizados: sem evidência versionada de execução.
- Correções aplicadas conforme feedback: ajustes de estrutura e README.
- Evidências dos testes registradas: não localizada.

### Reunião diária

| Item | Status | Evidência |
|---|---|---|
| Progresso individual e coletivo compartilhado | Pendente de ata | Sem arquivo de Daily Scrum localizado |
| Impedimentos identificados e discutidos | Pendente de ata | Sem registro específico |
| Plano de contingência definido | Não aplicável/localizado | Sem impedimento formal versionado |
| Registro da reunião no ALM | Parcial | Commits registram progresso, mas não substituem ata |

## Sprint #02

### Objetivo da sprint

Avançar o MVP com autenticação, cadastro de usuário, pagamento, checkout, painel administrativo e documentação consolidada do projeto.

### Branches e commits de evidência

| Repositório | Branch | Evidências |
|---|---|---|
| `toquedemulher-backend` | `main` | `59d3598` backend completo do e-commerce; `60b802a` criação de usuário; `39eb0fe` login e webhook; `edcb9e4` integração Stripe; `513a925` reestruturação de criação de produto |
| `toquedemulher-frontend` | `main`, `feat/frontend-pages` | `85e6ca2` checkout em etapas; `fb9e450` dashboard administrativo; `6871239` autenticação e gerenciamento de produto; `6fc3ecd` README técnico |
| `docs` | `main`, `backup/main-before-rewrite`, `backup/main-before-remove-0c7ceec` | `be67842` status da implementação; `0eed50d` documento de requisitos; `0c7ceec` plano consolidado com visão de futuro |
| `.github` | `main` | `b2cea0e`, `96fd653`, `513dee5` banners, badges e README institucional |

### Desenvolvimento da sprint

- Tarefas do Sprint Backlog em execução: autenticação, checkout, pagamento, dashboard e documentação do MVP.
- Funcionalidades implementadas e testadas: cadastro de usuário, login, preferência/webhook de pagamento, checkout frontend e dashboard administrativo.
- Atualizações registradas no ALM: commits em frontend, backend, docs e `.github`.
- Backlog ajustado: documentação de status atual registra desalinhamentos entre frontend e backend.

### Artefatos produzidos

- Histórias de usuários documentadas: parcialmente refletidas no escopo do MVP e no status atual, sem arquivo formal de user stories.
- Critérios de aceitação definidos: parcialmente inferidos por rotas e fluxos implementados, sem checklist formal.
- Protótipos atualizados: telas implementadas diretamente no frontend.
- Regras de negócio revisadas: fluxo de checkout, pagamento, usuário e administração.

### Testes e validação

- Testes funcionais realizados: evidência parcial por implementação e ajustes; sem relatório de execução.
- Correções aplicadas conforme feedback: correções de texto, estrutura e configuração.
- Evidências dos testes registradas: não localizada em arquivo de teste.

### Reunião diária

| Item | Status | Evidência |
|---|---|---|
| Progresso individual e coletivo compartilhado | Pendente de ata | Sem arquivo de Daily Scrum localizado |
| Impedimentos identificados e discutidos | Parcial | Desalinhamentos registrados em `docs/docs/introducao/status_atual.md` |
| Plano de contingência definido | Parcial | Próximos passos recomendados no status atual |
| Registro da reunião no ALM | Parcial | Commits e documentação técnica |

## Sprint #03

### Objetivo da sprint

Melhorar a experiência de compra, busca, endereços, acessibilidade, tema visual, segurança e início da gestão operacional de estoque e fornecedores.

### Branches e commits de evidência

| Repositório | Branch | Evidências |
|---|---|---|
| `toquedemulher-frontend` | `main`, `feat/dark-mode-themes`, `feat/accessibility-audit`, `feat/navegacao` | `9256c47` e `2275927` página de resultados; `4733ea6` função de busca; `58fd444` input de busca; `0b23da6` tema dinâmico; `76451c0` acessibilidade; `ca8a5c2` navegação inteligente na busca |
| `toquedemulher-backend` | `main`, `fix/updating-dependency-versions`, `dependabot/pip/python-jose-3.4.0` | `19e5bca` Stripe checkout/webhook; `b6baebf` endereço; `6e4aa07` CRUD de endereço; `4731b65` processo de teste com Bruno; `a45301b` coleção Bruno; `87c3c12` estoque; `0cd6f7c` atualização de dependências; `0018e23` correção de alerta de segurança |

### Desenvolvimento da sprint

- Tarefas do Sprint Backlog em execução: busca, navegação, endereços, checkout, estoque inicial, tema escuro e acessibilidade.
- Funcionalidades implementadas e testadas: rotas de endereço, checkout/webhook, coleção Bruno, busca no frontend e temas.
- Atualizações registradas no ALM: commits, merges e branches de feature/fix.
- Backlog ajustado: correções de segurança e dependência priorizadas.

### Artefatos produzidos

- Histórias de usuários documentadas: não localizadas em formato formal.
- Critérios de aceitação definidos: parcialmente representados por rotas, componentes e coleção Bruno.
- Protótipos atualizados: páginas reais implementadas no frontend.
- Regras de negócio revisadas: endereço no checkout, estoque, fornecedor/produto inicial e segurança.

### Testes e validação

- Testes funcionais realizados: coleção Bruno adicionada e documentada para APIs.
- Correções aplicadas conforme feedback: regressões de merge no frontend e alertas de segurança no backend.
- Evidências dos testes registradas: arquivos Bruno versionados em `toquedemulher-backend/bruno/`.

### Reunião diária

| Item | Status | Evidência |
|---|---|---|
| Progresso individual e coletivo compartilhado | Pendente de ata | Sem arquivo de Daily Scrum localizado |
| Impedimentos identificados e discutidos | Parcial | Correções de merge, segurança e dependências aparecem nos commits |
| Plano de contingência definido | Parcial | Branches de fix e merges no backend |
| Registro da reunião no ALM | Parcial | Commits e coleção Bruno |

## Sprint #04

### Objetivo da sprint

Consolidar a execução operacional do MVP com fornecedores, associação fornecedor-produto, entradas de estoque, movimentações de estoque e controle de acesso administrativo.

### Branches e commits de evidência

| Repositório | Branch | Evidências |
|---|---|---|
| `toquedemulher-backend` | `feature/backend-base` | `d9d9f79` fornecedores em produto; `17a6ef9` associação fornecedor-produto; `f8ed02c` lógica de associação fornecedor-produto; `d12e999` dependência de admin; `19f8cfa` busca/exclusão de estoque; `efeffe5` serviço de estoque; `35e5d6d` movimentação de estoque; `680f584` endpoints de fornecedor |
| `toquedemulher-backend` | `main` | Base anterior de segurança e dependências até `0018e23` |
| `toquedemulher-frontend` | `main` | Sem commits novos após 23/04/2026 localizados para esta sprint |
| `docs` | `main` | Sem commits novos após 16/03/2026 localizados para esta sprint |

### Reunião diária

| Item solicitado | Status | Evidência/observação |
|---|---|---|
| Progresso individual e coletivo compartilhado | Parcial | Progresso técnico registrado em commits de 25/04 a 09/05 no backend |
| Impedimentos identificados e discutidos | Parcial | Riscos técnicos: dependência de alinhamento frontend-backend, validação de rotas protegidas e testes completos do fluxo de estoque |
| Plano de contingência definido | Parcial | Usar Bruno para validar rotas; priorizar fluxo administrativo mínimo antes de novas features; manter branch `feature/backend-base` até validação |
| Registro da reunião no ALM | Pendente | Não há ata de Daily Scrum versionada; registrar no GitHub/ALM com link para commits |

### Desenvolvimento da Sprint #04

| Item solicitado | Status | Evidência |
|---|---|---|
| Tarefas do Sprint Backlog em execução | Concluído/parcial | Commits em `feature/backend-base` para fornecedores, estoque e controle administrativo |
| Funcionalidades implementadas e testadas | Parcial | Código implementado; testes funcionais devem ser executados via Bruno |
| Atualizações registradas no ALM | Parcial | Git/GitHub registram branches e commits; falta registro textual da sprint no ALM |
| Backlog ajustado conforme necessário | Parcial | Próximas pendências: integração frontend-backend, testes de estoque, atualização da documentação |

### Artefatos produzidos

| Item solicitado | Status | Evidência |
|---|---|---|
| Histórias de Usuários documentadas | Parcial | Histórias abaixo consolidadas a partir dos commits da sprint |
| Critérios de Aceitação definidos | Parcial | Critérios abaixo definidos para validação da Sprint #04 |
| Protótipos atualizados | Pendente | Não houve commit frontend/protótipo localizado para esta sprint |
| Regras de Negócio revisadas | Concluído/parcial | README do backend documenta fornecedor, supplier-product, estoque, lotes e fluxo Bruno |

### Histórias de usuário da Sprint #04

| ID | História | Critérios de aceitação |
|---|---|---|
| HU-S04-01 | Como administrador, quero cadastrar fornecedores para controlar quem abastece a loja. | Deve permitir criar, listar, atualizar e excluir fornecedores; deve impedir duplicidade por e-mail quando aplicável; deve retornar erro de validação para payload inválido. |
| HU-S04-02 | Como administrador, quero associar fornecedores a produtos para registrar custo e prazo de reposição. | Deve associar fornecedor existente a produtos existentes; deve retornar erro quando fornecedor ou produto não existir; deve registrar preço de custo e prazo médio. |
| HU-S04-03 | Como administrador, quero registrar entradas de estoque para manter quantidade disponível atualizada. | Deve receber fornecedor e lista de itens; deve criar lote/entrada de estoque; deve atualizar saldo disponível; deve validar quantidade e custo unitário. |
| HU-S04-04 | Como administrador, quero consultar e remover registros de estoque quando necessário. | Deve permitir recuperar estoque por produto; deve permitir exclusão conforme regra da API; deve retornar erro para produto inexistente. |
| HU-S04-05 | Como administrador, quero que rotas administrativas sejam protegidas. | Deve exigir usuário autenticado com permissão administrativa; deve negar acesso quando a permissão for insuficiente. |

### Regras de negócio revisadas

- `Supplier` representa quem fornece produtos.
- `SupplierProduct` representa o catálogo do fornecedor, com preço de custo e prazo.
- `StockBatch` representa uma entrada real de mercadoria/lote.
- `Stock` guarda o total disponível por produto.
- O fluxo recomendado é: cadastrar fornecedor, cadastrar produto, associar fornecedor-produto e registrar entrada no estoque.
- Rotas administrativas devem usar dependência de usuário administrador.

### Testes e validação

| Item solicitado | Status | Evidência/ação |
|---|---|---|
| Testes funcionais realizados | Parcial | Coleção Bruno existe para `supplier`, `suppliersProducts`, `stock`, `Auth`, `User`, `Addresses` e `Payment` |
| Correções aplicadas conforme feedback | Parcial | Commits de 07/05 a 09/05 ajustam estoque, movimentação e fornecedor |
| Evidências dos testes registradas | Parcial | Arquivos Bruno versionados; faltam prints ou relatório de execução |

### Evidências da Sprint #04

- Branch principal de trabalho: `toquedemulher-backend/feature/backend-base`.
- Commits principais:
  - [`d9d9f79`](https://github.com/ToqueDeMulher/toquedemulher-backend/commit/d9d9f79) - adiciona lógica de fornecedores ao endpoint de produto.
  - [`17a6ef9`](https://github.com/ToqueDeMulher/toquedemulher-backend/commit/17a6ef9) - implementa endpoint de associação fornecedor-produto.
  - [`f8ed02c`](https://github.com/ToqueDeMulher/toquedemulher-backend/commit/f8ed02c) - melhora lógica e schemas de associação fornecedor-produto.
  - [`d12e999`](https://github.com/ToqueDeMulher/toquedemulher-backend/commit/d12e999) - implementa dependência de usuário administrador.
  - [`19f8cfa`](https://github.com/ToqueDeMulher/toquedemulher-backend/commit/19f8cfa) - adiciona busca e exclusão de estoque.
  - [`efeffe5`](https://github.com/ToqueDeMulher/toquedemulher-backend/commit/efeffe5) - cria serviço de estoque com funções auxiliares.
  - [`35e5d6d`](https://github.com/ToqueDeMulher/toquedemulher-backend/commit/35e5d6d) - implementa movimentação de estoque.
  - [`680f584`](https://github.com/ToqueDeMulher/toquedemulher-backend/commit/680f584) - implementa endpoints de gestão de fornecedores.
- Artefatos de teste:
  - `toquedemulher-backend/bruno/Toque de mulher/supplier/`
  - `toquedemulher-backend/bruno/Toque de mulher/suppliersProducts/`
  - `toquedemulher-backend/bruno/Toque de mulher/stock/`
  - `toquedemulher-backend/bruno/Toque de mulher/environments/baseUrl.yml`

## Pendências para fechamento formal

| Pendência | Motivo | Ação recomendada |
|---|---|---|
| Atas de Daily Scrum | Não há arquivos versionados com registros diários | Criar registro no ALM com data, participantes, progresso, impedimentos e plano |
| Evidências visuais | Não foram localizados prints de tela/teste | Anexar prints do frontend e capturas do Bruno executando os fluxos |
| Testes automatizados | Não há relatório de testes automatizados identificado | Executar testes existentes ou documentar teste manual funcional |
| Atualização de documentação da Sprint #04 | Backend avançou após a última atualização do `docs` | Atualizar status atual do projeto com commits até 09/05/2026 |
| Integração frontend-backend | Sprint #04 concentrou backend | Planejar tarefa de integração das rotas administrativas no frontend |

## Checklist final da Aula 13

- [x] Progresso técnico individual e coletivo consolidado por commits e branches.
- [x] Impedimentos técnicos mapeados a partir da documentação e dos commits.
- [x] Plano de contingência proposto para validação e fechamento.
- [ ] Registro formal da reunião diária no ALM.
- [x] Tarefas do Sprint Backlog da Sprint #04 identificadas.
- [x] Funcionalidades da Sprint #04 documentadas.
- [ ] Evidência completa de testes funcionais executados.
- [x] Histórias de usuário e critérios de aceitação consolidados.
- [ ] Protótipos/wireframes atualizados para Sprint #04.
- [x] Regras de negócio revisadas.
- [ ] Prints de tela anexados.
- [x] Links/identificadores de commits registrados.
- [ ] Lista formal de impedimentos registrada no ALM.
