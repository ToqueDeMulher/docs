# Acompanhamento das Sprints

Relatório consolidado originalmente em **5 de junho de 2026** e atualizado em **31 de julho de 2026**, elaborado a partir dos commits, branches, entregas registradas, leitura do backend/frontend e alinhamentos feitos pela equipe durante as sprints do projeto Toque de Mulher.

> A atualização de 31/07/2026 considera os históricos separados dos repositórios `docs`, `toquedemulher-backend` e `toquedemulher-frontend`. O diretório raiz local não é um repositório Git único.

## Fontes consultadas

| Repositório               | Branches relevantes                                                                                                                | Registro consultado                                                                                                                               |
| -------------------------- | ---------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------- |
| `toquedemulher-frontend` | `main`, `frontend-pages`, `feat/frontend-pages`, `feat/dark-mode-themes`, `feat/accessibility-audit`, `feat/navegacao` | Interface web, catálogo, carrinho, checkout, autenticação, endereço, área administrativa, busca, tema, acessibilidade e refinamentos visuais |
| `toquedemulher-backend`  | `main`, `feature/backend-base`, `fix/updating-dependency-versions`, `dependabot/pip/python-jose-3.4.0`                     | API FastAPI, autenticação, pagamentos, usuários, endereços, fornecedores, estoque, associação fornecedor-produto e validações internas    |
| `docs`                   | `main`, `backup/main-before-rewrite`, `backup/main-before-remove-0c7ceec`                                                    | Documentação executiva, escopo, roadmap, status técnico, sprints, riscos, glossário e mockup de alta fidelidade                               |
| `.github`                | `main`                                                                                                                           | Perfil institucional, badges e apresentação pública da organização                                                                           |

As dailies/alinhamentos da equipe acontecem **semanalmente**, normalmente das **21h às 22h30**, com possibilidade de extensão até aproximadamente **23h** quando há pendências técnicas ou fechamento de entrega. O progresso discutido nas reuniões é rastreado pelos logs, branches e commits do GitHub.

As prints de evidência ficam reunidas no **Google Docs compartilhado da equipe**, usado como material de apoio do relatório da sprint. A documentação também possui assets locais em `docs/assets` e o vídeo não listado [Demonstração do site no YouTube](https://youtu.be/bMFOPJKa_tY).

Links dos repositórios usados como registro técnico:

- Frontend: [https://github.com/ToqueDeMulher/toquedemulher-frontend](https://github.com/ToqueDeMulher/toquedemulher-frontend)
- Backend: [https://github.com/ToqueDeMulher/toquedemulher-backend](https://github.com/ToqueDeMulher/toquedemulher-backend)
- Documentação: [https://github.com/ToqueDeMulher/docs](https://github.com/ToqueDeMulher/docs)

## Visão geral por sprint

| Sprint     | Período inferido pelos commits | Foco principal                                                                                                | Status                |
| ---------- | ------------------------------- | ------------------------------------------------------------------------------------------------------------- | --------------------- |
| Sprint #01 | 05/02/2026 a 23/02/2026         | Estrutura inicial do produto, documentação e base do frontend/backend                                       | Concluída            |
| Sprint #02 | 08/03/2026 a 16/03/2026         | Fluxos essenciais: usuário, login, pagamento, checkout, dashboard e documentação consolidada               | Concluída            |
| Sprint #03 | 23/03/2026 a 23/04/2026         | Busca, endereço, refinamento de checkout, estoque inicial, temas, acessibilidade e correções de segurança | Concluída            |
| Sprint #04 | 25/04/2026 a 09/05/2026         | Fornecedores, associação fornecedor-produto, estoque, movimentação de estoque e controle administrativo   | Concluída            |
| Sprint #05 | 15/05/2026 a 24/05/2026         | Alinhamento frontend-backend, autenticação, prefixo de API, merge da base operacional e refinamento visual  | Em finalização     |
| Sprint #06 | A partir de 05/06/2026          | Fechamento documental, validação ponta a ponta, consolidação de rotas oficiais e registro de evidências  | Planejada/em abertura |
| Sprint #07 | 27/07/2026 a 31/07/2026         | Revisão final de julho: refinamentos frontend, branch de revisão backend, consolidação documental e auditoria código-documentação | Em validação |

## Sprint #01

### Objetivo da sprint

Criar a base do projeto, organizar a documentação inicial e iniciar as estruturas técnicas de frontend e backend.

### Branches e commits de evidência

| Repositório               | Branch   | Evidências                                                                                                |
| -------------------------- | -------- | ---------------------------------------------------------------------------------------------------------- |
| `docs`                   | `main` | `4cb344d` roadmap com KPIs e fases; `54ce3c5` roadmap e guia de contribuição                         |
| `toquedemulher-frontend` | `main` | `643c0ae` frontend inicial; `4b39695` ignore de build e VSCode; `5c19ac2` refatoração de estrutura |
| `toquedemulher-backend`  | `main` | `76215cd` estrutura feature-based do backend                                                             |
| `.github`                | `main` | `4de5bad`, `9f80c6e`, `bb17108` ajustes de README, banner e badges                                   |

### Desenvolvimento da sprint

- Tarefas do Sprint Backlog em execução: documentação base, organização de repositórios e início da aplicação web.
- Funcionalidades implementadas e testadas: estrutura inicial de frontend e backend; ainda sem evidência de teste automatizado.
- Atualizações registradas: commits versionados no GitHub.
- Backlog ajustado: roadmap e guia de contribuição atualizados no repositório `docs`.

### Artefatos produzidos

- Histórias de usuários documentadas: registradas de forma indireta no escopo e nas entregas técnicas.
- Critérios de aceitação definidos: acompanhados pela entrega das funcionalidades iniciais.
- Protótipos atualizados: a evolução visual ocorreu diretamente no frontend.
- Regras de negócio revisadas: escopo, roadmap e documentação inicial.

### Testes e validação

- Testes funcionais realizados: validação inicial feita pela equipe durante a construção da base.
- Correções aplicadas conforme feedback: ajustes de estrutura e README.
- Evidências dos testes registradas: commits e ajustes de estrutura.

### Reunião diária

| Item                                          | Status           | Evidência                                               |
| --------------------------------------------- | ---------------- | -------------------------------------------------------- |
| Progresso individual e coletivo compartilhado | Realizado        | Alinhamentos por WhatsApp e conversas presenciais        |
| Impedimentos identificados e discutidos       | Realizado        | Tratados diretamente pela equipe durante os alinhamentos |
| Plano de contingência definido               | Conforme demanda | Não houve impedimento crítico registrado nesta sprint  |
| Registro da reunião                          | Parcial          | Progresso técnico registrado por commits                |

## Sprint #02

### Objetivo da sprint

Avançar o MVP com autenticação, cadastro de usuário, pagamento, checkout, painel administrativo e documentação consolidada do projeto.

### Branches e commits de evidência

| Repositório               | Branch                                                                          | Evidências                                                                                                                                                                                       |
| -------------------------- | ------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `toquedemulher-backend`  | `main`                                                                        | `59d3598` backend completo do e-commerce; `60b802a` criação de usuário; `39eb0fe` login e webhook; `edcb9e4` integração Stripe; `513a925` reestruturação de criação de produto |
| `toquedemulher-frontend` | `main`, `feat/frontend-pages`                                               | `85e6ca2` checkout em etapas; `fb9e450` dashboard administrativo; `6871239` autenticação e gerenciamento de produto; `6fc3ecd` README técnico                                          |
| `docs`                   | `main`, `backup/main-before-rewrite`, `backup/main-before-remove-0c7ceec` | `be67842` status da implementação; `0eed50d` documento de requisitos; `0c7ceec` plano consolidado com visão de futuro                                                                    |
| `.github`                | `main`                                                                        | `b2cea0e`, `96fd653`, `513dee5` banners, badges e README institucional                                                                                                                      |

### Desenvolvimento da sprint

- Tarefas do Sprint Backlog em execução: autenticação, checkout, pagamento, dashboard e documentação do MVP.
- Funcionalidades implementadas e testadas: cadastro de usuário, login, preferência/webhook de pagamento, checkout frontend e dashboard administrativo.
- Atualizações registradas: commits em frontend, backend, docs e `.github`.
- Backlog ajustado: documentação de status atual registra desalinhamentos entre frontend e backend.

### Artefatos produzidos

- Histórias de usuários documentadas: refletidas no escopo do MVP e no status atual.
- Critérios de aceitação definidos: acompanhados pelas rotas e fluxos implementados.
- Protótipos atualizados: telas implementadas diretamente no frontend.
- Regras de negócio revisadas: fluxo de checkout, pagamento, usuário e administração.

### Testes e validação

- Testes funcionais realizados: evidência parcial por implementação e ajustes; sem relatório de execução.
- Correções aplicadas conforme feedback: correções de texto, estrutura e configuração.
- Evidências dos testes registradas: commits e documentação técnica.

### Reunião diária

| Item                                          | Status    | Evidência                                                              |
| --------------------------------------------- | --------- | ----------------------------------------------------------------------- |
| Progresso individual e coletivo compartilhado | Realizado | Alinhamentos por WhatsApp e conversas presenciais                       |
| Impedimentos identificados e discutidos       | Realizado | Desalinhamentos registrados em `docs/docs/introducao/status_atual.md` |
| Plano de contingência definido               | Parcial   | Próximos passos recomendados no status atual                           |
| Registro da reunião                          | Parcial   | Commits e documentação técnica                                       |

## Sprint #03

### Objetivo da sprint

Melhorar a experiência de compra, busca, endereços, acessibilidade, tema visual, segurança e início da gestão operacional de estoque e fornecedores.

### Branches e commits de evidência

| Repositório               | Branch                                                                                | Evidências                                                                                                                                                                                                                                                                                |
| -------------------------- | ------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `toquedemulher-frontend` | `main`, `feat/dark-mode-themes`, `feat/accessibility-audit`, `feat/navegacao` | `9256c47` e `2275927` página de resultados; `4733ea6` função de busca; `58fd444` input de busca; `0b23da6` tema dinâmico; `76451c0` acessibilidade; `ca8a5c2` navegação inteligente na busca                                                                           |
| `toquedemulher-backend`  | `main`, `fix/updating-dependency-versions`, `dependabot/pip/python-jose-3.4.0`  | `19e5bca` Stripe checkout/webhook; `b6baebf` endereço; `6e4aa07` CRUD de endereço; `4731b65` processo de teste de API; `a45301b` coleção de requests da API; `87c3c12` estoque; `0cd6f7c` atualização de dependências; `0018e23` correção de alerta de segurança |

### Desenvolvimento da sprint

- Tarefas do Sprint Backlog em execução: busca, navegação, endereços, checkout, estoque inicial, tema escuro e acessibilidade.
- Funcionalidades implementadas e testadas: rotas de endereço, checkout/webhook, validação interna da API, busca no frontend e temas.
- Atualizações registradas: commits, merges e branches de feature/fix.
- Backlog ajustado: correções de segurança e dependência priorizadas.

### Artefatos produzidos

- Histórias de usuários documentadas: refletidas nas entregas de busca, endereço, tema, acessibilidade e estoque.
- Critérios de aceitação definidos: parcialmente representados por rotas, componentes e validações internas.
- Protótipos atualizados: páginas reais implementadas no frontend.
- Regras de negócio revisadas: endereço no checkout, estoque, fornecedor/produto inicial e segurança.

### Testes e validação

- Testes funcionais realizados: validações internas previstas e documentação de requests da API.
- Correções aplicadas conforme feedback: regressões de merge no frontend e alertas de segurança no backend.
- Evidências dos testes registradas: documentação técnica, commits e prints reunidas no Google Docs da equipe.

### Reunião diária

| Item                                          | Status    | Evidência                                                            |
| --------------------------------------------- | --------- | --------------------------------------------------------------------- |
| Progresso individual e coletivo compartilhado | Realizado | Alinhamentos por WhatsApp e conversas presenciais                     |
| Impedimentos identificados e discutidos       | Realizado | Correções de merge, segurança e dependências aparecem nos commits |
| Plano de contingência definido               | Parcial   | Branches de fix e merges no backend                                   |
| Registro da reunião                          | Parcial   | Commits e documentação técnica                                     |

## Sprint #04

### Objetivo da sprint

Consolidar a execução operacional do MVP com fornecedores, associação fornecedor-produto, entradas de estoque, movimentações de estoque e controle de acesso administrativo.

### Status da sprint

Sprint **concluída**. As entregas técnicas previstas para fornecedores, associação fornecedor-produto, estoque, movimentação de estoque e controle administrativo foram implementadas no backend e registradas por commits.

### Branches e commits de evidência

| Repositório               | Branch                   | Evidências                                                                                                                                                                                                                                                                                                                      |
| -------------------------- | ------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `toquedemulher-backend`  | `feature/backend-base` | `d9d9f79` fornecedores em produto; `17a6ef9` associação fornecedor-produto; `f8ed02c` lógica de associação fornecedor-produto; `d12e999` dependência de admin; `19f8cfa` busca/exclusão de estoque; `efeffe5` serviço de estoque; `35e5d6d` movimentação de estoque; `680f584` endpoints de fornecedor |
| `toquedemulher-backend`  | `main`                 | Base anterior de segurança e dependências até `0018e23`                                                                                                                                                                                                                                                                     |
| `toquedemulher-frontend` | `main`                 | Não houve novos commits de frontend após 23/04/2026 para esta sprint                                                                                                                                                                                                                                                           |
| `docs`                   | `main`                 | Não houve novos commits de documentação após 16/03/2026 para esta sprint                                                                                                                                                                                                                                                     |

### Reunião diária

| Item solicitado                               | Status  | Evidência/observação                                                                                                                                |
| --------------------------------------------- | ------- | ------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Progresso individual e coletivo compartilhado | Realizado | Progresso técnico registrado em commits de 25/04 a 09/05 no backend                                                                                 |
| Impedimentos identificados e discutidos       | Realizado | Riscos técnicos tratados durante a sprint: alinhamento frontend-backend, rotas protegidas e fluxo de estoque                                      |
| Plano de contingência definido               | Realizado | Priorização do fluxo administrativo mínimo e manutenção da `feature/backend-base` até o fechamento técnico                                      |
| Registro da reunião                          | Parcial   | Alinhamentos feitos por WhatsApp/presencial e evolução técnica registrada em commits                                                              |

### Desenvolvimento da Sprint #04

| Item solicitado                          | Status             | Evidência                                                                                               |
| ---------------------------------------- | ------------------ | -------------------------------------------------------------------------------------------------------- |
| Tarefas do Sprint Backlog em execução  | Concluído | Commits em `feature/backend-base` para fornecedores, estoque e controle administrativo                 |
| Funcionalidades implementadas e testadas | Concluído/parcial | Código implementado e validações internas consideradas suficientes para fechamento da sprint          |
| Atualizações registradas               | Concluído | Git/GitHub registram branches e commits; relatório de sprint consolida o acompanhamento               |
| Backlog ajustado conforme necessário    | Concluído | Pendências remanescentes movidas para Sprint #05/#06: integração frontend-backend e evidências finais |

### Artefatos produzidos

| Item solicitado                      | Status             | Evidência                                                                                   |
| ------------------------------------ | ------------------ | -------------------------------------------------------------------------------------------- |
| Histórias de Usuários documentadas | Concluído          | Histórias abaixo consolidadas a partir dos commits da sprint                                |
| Critérios de Aceitação definidos  | Concluído          | Critérios abaixo definidos e usados para fechamento da Sprint #04                         |
| Protótipos atualizados              | Pendente           | Não houve commit frontend/protótipo localizado para esta sprint                            |
| Regras de Negócio revisadas         | Concluído          | README do backend documenta fornecedor, supplier-product, estoque, lotes e fluxo operacional |

### Histórias de usuário da Sprint #04

| ID        | História                                                                                               | Critérios de aceitação                                                                                                                                                       |
| --------- | ------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| HU-S04-01 | Como administrador, quero cadastrar fornecedores para controlar quem abastece a loja.                   | Deve permitir criar, listar, atualizar e excluir fornecedores; deve impedir duplicidade por e-mail quando aplicável; deve retornar erro de validação para payload inválido. |
| HU-S04-02 | Como administrador, quero associar fornecedores a produtos para registrar custo e prazo de reposição. | Deve associar fornecedor existente a produtos existentes; deve retornar erro quando fornecedor ou produto não existir; deve registrar preço de custo e prazo médio.          |
| HU-S04-03 | Como administrador, quero registrar entradas de estoque para manter quantidade disponível atualizada.  | Deve receber fornecedor e lista de itens; deve criar lote/entrada de estoque; deve atualizar saldo disponível; deve validar quantidade e custo unitário.                      |
| HU-S04-04 | Como administrador, quero consultar e remover registros de estoque quando necessário.                  | Deve permitir recuperar estoque por produto; deve permitir exclusão conforme regra da API; deve retornar erro para produto inexistente.                                        |
| HU-S04-05 | Como administrador, quero que rotas administrativas sejam protegidas.                                   | Deve exigir usuário autenticado com permissão administrativa; deve negar acesso quando a permissão for insuficiente.                                                         |

### Regras de negócio revisadas

- `Supplier` representa quem fornece produtos.
- `SupplierProduct` representa o catálogo do fornecedor, com preço de custo e prazo.
- `StockBatch` representa uma entrada real de mercadoria/lote.
- `Stock` guarda o total disponível por produto.
- O fluxo recomendado é: cadastrar fornecedor, cadastrar produto, associar fornecedor-produto e registrar entrada no estoque.
- Rotas administrativas devem usar dependência de usuário administrador.

### Testes e validação

| Item solicitado                         | Status  | Evidência/ação                                                                                                                          |
| --------------------------------------- | ------- | ------------------------------------------------------------------------------------------------------------------------------------------ |
| Testes funcionais realizados            | Concluído/parcial | Fluxos de `supplier`, `suppliersProducts` e `stock` considerados validados internamente para fechamento da sprint |
| Correções aplicadas conforme feedback | Concluído | Commits de 07/05 a 09/05 ajustam estoque, movimentação e fornecedor                                                        |
| Evidências dos testes registradas      | Parcial   | Prints e registros de validação reunidos no Google Docs da equipe; formalização final permanece na Sprint #06              |

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
  - validação interna dos fluxos de fornecedor;
  - validação interna dos fluxos de associação fornecedor-produto;
  - validação interna dos fluxos de estoque;
  - registro dos resultados em relatório ou ata da sprint.

## Sprint #05

### Objetivo da sprint

Fechar as pendências da Sprint #04 e avançar para uma entrega validável do MVP operacional, com foco em alinhamento frontend-backend, autenticação, prefixo versionado de API, merge da base operacional do backend, refinamentos de interface e registro de evidências.

### Branches e commits de evidência

| Repositório               | Branch                             | Evidências                                                                                                                                                                                                                                                 |
| -------------------------- | ---------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `docs`                   | `main`                           | `178ac3a`, `425a26d`, `fe6be31` documentação de acompanhamento das sprints, clareza estrutural e rastreabilidade de evidências                                                                                                                     |
| `toquedemulher-backend`  | `main`, `feature/backend-base` | `4eb2b44` atualização de sintaxe e segurança; `47decbe` correção de `python-multipart`; `8df0fea` ajuste de registro/login com `name` e prefixo versionado; `d9e942b` merge da `feature/backend-base` para `main`                      |
| `toquedemulher-frontend` | `main`, `frontend-pages`       | `d2b56f0` refinamento de UX; `93a1055` merge da branch `frontend-pages`; `50ba285` adição de `axios` e atualização dos serviços de autenticação; `87d134c` limpeza de componentes promocionais; `7dcd10d` melhorias de estilo, layout, cores e tipografia |

Os logs mostram que a Sprint #05 deixou de ser apenas planejada: houve atualização de documentação em 15/05, ajustes backend entre 15/05 e 24/05, e refinamentos frontend entre 20/05 e 24/05. Na época, a autenticação foi tratada como fluxo integrado; a revisão de 31/07/2026, porém, identificou que o contrato de resposta ainda precisa ser ajustado para fechar `refresh_token`, `id` e `role`.

### Reunião diária

| Item solicitado                               | Status            | Evidência/observação                                                                            |
| --------------------------------------------- | ----------------- | -------------------------------------------------------------------------------------------------- |
| Progresso individual e coletivo compartilhado | Realizado/parcial | Dailies semanais das 21h às 22h30, eventualmente até 23h; progresso técnico registrado nos logs do GitHub |
| Impedimentos identificados e discutidos       | Realizado/parcial | Desalinhamento de contratos e duplicidade de estruturas de rota permanecem como risco técnico     |
| Plano de contingência definido               | Parcial           | Priorizar validação dos fluxos críticos e documentar endpoints oficiais antes de novas features |
| Registro da reunião                          | Parcial           | Commits/logs do GitHub e documentação atualizada; ata detalhada ainda deve ser consolidada pela equipe |

### Desenvolvimento da Sprint #05

| Item solicitado                          | Status             | Evidência/ação                                                                               |
| ---------------------------------------- | ------------------ | ----------------------------------------------------------------------------------------------- |
| Tarefas do Sprint Backlog em execução  | Em finalização | Autenticação e prefixo de API ajustados; base backend operacional mergeada; frontend refinado |
| Funcionalidades implementadas e testadas | Parcial/concluído | Registro, login e get de usuário integrados e funcionando; demais fluxos aguardam evidência final |
| Atualizações registradas               | Concluído         | Commits registrados em frontend, backend e docs                                                 |
| Backlog ajustado conforme necessário    | Concluído/parcial | Sprint #06 deve focar evidências finais, rotas oficiais e validação dos fluxos restantes     |

### Backlog executado/atualizado da Sprint #05

| ID      | Tarefa                                        | Resultado                                                     | Evidência                            |
| ------- | --------------------------------------------- | ------------------------------------------------------------- | ------------------------------------- |
| S05-T01 | Atualizar documentação de sprints           | Relatório de sprints criado e estruturado                    | `178ac3a`, `425a26d`, `fe6be31` |
| S05-T02 | Corrigir dependência backend                 | Versão de `python-multipart` corrigida                     | `47decbe`                           |
| S05-T03 | Atualizar sintaxe e segurança backend        | Ajustes de segurança e modernização aplicados              | `4eb2b44`                           |
| S05-T04 | Alinhar autenticação com frontend           | Registro/login passam a incluir `name` e prefixo versionado | `8df0fea`                           |
| S05-T05 | Integrar branch operacional backend           | `feature/backend-base` mergeada em `main`                 | `d9e942b`                           |
| S05-T06 | Refinar UX e layout frontend                  | Páginas e componentes ajustados visualmente; predominância visual mudou de rosa para preto a pedido da cliente; fontes passaram de `Inter` para `All Round Gothic` e `Noto Sans` | `d2b56f0`, `87d134c`, `7dcd10d` |
| S05-T07 | Atualizar serviço de autenticação frontend | `axios` adicionado e fluxo de login/cadastro revisado       | `50ba285`                           |

### Artefatos produzidos

| Item solicitado                      | Status             | Evidência                                                                                           |
| ------------------------------------ | ------------------ | ---------------------------------------------------------------------------------------------------- |
| Histórias de Usuários documentadas | Concluído/parcial | Histórias abaixo revisadas conforme entregas da sprint                                              |
| Critérios de Aceitação definidos  | Concluído/parcial | Critérios abaixo definidos para validação                                                         |
| Protótipos atualizados              | Parcial            | Mockup de alta fidelidade registrado em `docs/assets/figma_altafidelidade.png`                    |
| Regras de Negócio revisadas         | Parcial            | Autenticação, usuário, fornecedor, estoque e associação fornecedor-produto revisados no código |

### Histórias de usuário da Sprint #05

| ID        | História                                                                                                        | Critérios de aceitação                                                                                                                              |
| --------- | ---------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------ |
| HU-S05-01 | Como cliente, quero cadastrar e acessar minha conta usando o frontend conectado ao backend.                      | Login e cadastro devem enviar `email`, `password` e `name` conforme contrato atual; sessão deve persistir token e usuário no navegador.        |
| HU-S05-02 | Como administrador, quero que a base operacional de fornecedor e estoque esteja disponível na branch principal. | Commits da `feature/backend-base` devem estar mergeados na `main` e os endpoints devem permanecer acessíveis no app backend.                      |
| HU-S05-03 | Como usuária da loja, quero navegar por páginas visualmente mais consistentes.                                 | Layout, cores e componentes devem refletir os refinamentos de UX feitos no frontend, incluindo a predominância do preto, as fontes `All Round Gothic`/`Noto Sans` e a manutenção da estrutura geral do mockup. |
| HU-S05-04 | Como equipe técnica, queremos evidências de teste para comprovar a entrega da sprint.                          | Cada fluxo crítico deve ter print no Google Docs, registro interno de teste ou link de commit; falhas devem ser registradas com correção planejada. |
| HU-S05-05 | Como equipe do projeto, queremos registrar os alinhamentos da sprint para manter rastreabilidade.                | O relatório deve conter progresso, impedimentos, plano e links para commits ou tarefas.                                                               |

### Regras de negócio revisadas

- Registro de usuário deve incluir `name`, `email` e `password`.
- Login deve retornar token para autenticação das rotas protegidas.
- A identidade visual final deve usar preto como cor predominante, conforme solicitação da cliente.
- A tipografia final deve usar `All Round Gothic` e `Noto Sans` no lugar de `Inter`.
- A gamificação de produtos deve complementar a experiência de catálogo sem alterar a estrutura principal aprovada no mockup.
- Produto só pode ser associado a fornecedor existente.
- Entrada de estoque deve atualizar saldo disponível e manter rastreabilidade por lote/movimentação.
- Apenas usuários administradores devem executar operações administrativas de fornecedor, estoque e associação fornecedor-produto.
- Dados inválidos devem retornar erro claro e não alterar o estado do banco.

### Testes e validação

| Item solicitado                         | Status  | Evidência/ação                                                                                                |
| --------------------------------------- | ------- | ---------------------------------------------------------------------------------------------------------------- |
| Testes funcionais realizados            | Parcial | Validações manuais devem ser anexadas; código e commits indicam implementação, mas não relatório completo |
| Correções aplicadas conforme feedback | Parcial | Correções de dependência, autenticação, prefixo e layout registradas nos commits                            |
| Evidências dos testes registradas      | Parcial | Prints centralizadas no Google Docs; mockup local registrado na documentação                                   |

### Evidências da Sprint #05

- [`fe6be31`](https://github.com/ToqueDeMulher/docs/commit/fe6be31) - atualização de documentação de sprints.
- [`8df0fea`](https://github.com/ToqueDeMulher/toquedemulher-backend/commit/8df0fea) - ajuste de registro/login com `name` e prefixo versionado.
- [`d9e942b`](https://github.com/ToqueDeMulher/toquedemulher-backend/commit/d9e942b) - merge da `feature/backend-base`.
- [`50ba285`](https://github.com/ToqueDeMulher/toquedemulher-frontend/commit/50ba285) - atualização do serviço de autenticação frontend.
- [`7dcd10d`](https://github.com/ToqueDeMulher/toquedemulher-frontend/commit/7dcd10d) - melhorias de estilo e layout.
- Mockup de alta fidelidade: `docs/assets/figma_altafidelidade.png`.

### Checklist final da Sprint #05

- [X] Alinhamentos da sprint registrados de forma consolidada.
- [X] Impedimentos e plano de contingência documentados.
- [X] Branch backend operacional mergeada na `main`.
- [X] Serviço de autenticação frontend atualizado.
- [X] Cores predominantes ajustadas de rosa para preto a pedido da cliente.
- [X] Fontes ajustadas de `Inter` para `All Round Gothic` e `Noto Sans`.
- [X] Gamificação de produtos adicionada.
- [X] Histórias de usuário e critérios de aceitação revisados.
- [X] Mockup de alta fidelidade registrado nos assets da documentação.
- [ ] Endpoints de fornecedor validados com evidência anexada.
- [ ] Associação fornecedor-produto validada com evidência anexada.
- [ ] Entrada e consulta de estoque validadas com evidência anexada.
- [ ] Controle de acesso admin validado com evidência anexada.
- [ ] Frontend administrativo integrado e testado contra rotas reais.
- [ ] Prints funcionais registradas no Google Docs e vinculadas ao relatório.

## Sprint #06

### Objetivo da sprint

Consolidar o fechamento documental e técnico do MVP, validar os fluxos ponta a ponta, definir endpoints oficiais, reduzir divergências entre frontend e backend e registrar evidências funcionais.

### Branches e commits de evidência

| Repositório               | Branch   | Evidências                                                                                                    |
| -------------------------- | -------- | -------------------------------------------------------------------------------------------------------------- |
| `docs`                   | `main` | Atualização de 05/06/2026 com status atual, roadmap, sprints, riscos, premissas, contribuição, protótipo, prints e vídeo de demonstração |
| `toquedemulher-backend`  | `main` | Base até `d9e942b`, com rotas operacionais e estrutura adicional em `app/api/v1/router.py`                |
| `toquedemulher-frontend` | `main` | Base até `7dcd10d`, com serviços de autenticação/produto/endereço e refinamentos visuais                |

### Sprint Backlog da Sprint #06

| ID      | Tarefa                                                        | Resultado esperado                                               | Evidência esperada                      |
| ------- | ------------------------------------------------------------- | ---------------------------------------------------------------- | ---------------------------------------- |
| S06-T01 | Consolidar endpoints oficiais do backend                      | Uma árvore de rotas principal definida e documentada            | README/status atualizado e teste de rota |
| S06-T02 | Validar autenticação frontend-backend                       | Login, cadastro e `/me` funcionando com token                  | Integração confirmada pela equipe; anexar print/request-response |
| S06-T03 | Validar cadastro de endereço                                 | CEP, payload e persistência funcionando                         | Print da tela e resposta da API          |
| S06-T04 | Validar criação de produto e upload de imagem               | Produto criado e imagem associada                                | Print da tela admin e response da API    |
| S06-T05 | Validar fornecedor, associação fornecedor-produto e estoque | Fluxo operacional completo sem erro inesperado                   | Evidência com saldo antes/depois        |
| S06-T06 | Validar checkout/pagamento/pedido                             | Pedido criado e pagamento/webhook testado em ambiente controlado | Registro do fluxo e status final         |
| S06-T07 | Comparar frontend com mockup de alta fidelidade               | Lista de ajustes visuais priorizados                             | Print comparativo, vídeo ou checklist de UI |
| S06-T08 | Registrar evidências visuais e técnicas da sprint             | Prints e vídeo centralizados na documentação                      | Assets em `docs/assets` e link do YouTube |
| S06-T09 | Atualizar documentação final da sprint                        | Docs refletem entregas, pendências e evidências                  | Commit no repositório `docs`          |

### Histórias de usuário da Sprint #06

| ID        | História                                                                          | Critérios de aceitação                                                                                                                     |
| --------- | ---------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------- |
| HU-S06-01 | Como equipe técnica, queremos uma API principal sem rotas conflitantes.           | Deve existir uma estrutura de rotas oficial; endpoints duplicados ou legados devem ser removidos, migrados ou documentados como temporários. |
| HU-S06-02 | Como cliente, quero criar conta, entrar e manter minha sessão.                    | Cadastro, login e carregamento de perfil funcionam com o contrato atual entre frontend e backend; evidência visual/técnica deve ser anexada. |
| HU-S06-03 | Como cliente, quero cadastrar endereço e seguir para compra.                      | Endereço deve ser validado, salvo e usado no checkout.                                                                                       |
| HU-S06-04 | Como administrador, quero criar produto com imagem e controlar fornecedor/estoque. | Produto, imagem, fornecedor, associação e saldo devem ser criados ou alterados com evidência funcional.                                    |
| HU-S06-05 | Como equipe do projeto, queremos comprovar o avanço do MVP.                       | Evidências devem conter commits, prints, resultados de teste e pendências remanescentes.                                                    |

### Rotina de dailies da Sprint #06

| Item | Registro |
|---|---|
| Frequência | Semanal |
| Horário previsto | 21h às 22h30 |
| Extensão eventual | Até aproximadamente 23h |
| Registro de progresso | Logs, branches e commits do GitHub |
| Canais de alinhamento | WhatsApp e encontros presenciais quando necessário |

### Testes e validação

| Item solicitado                         | Status    | Evidência/ação                                                                                |
| --------------------------------------- | --------- | ------------------------------------------------------------------------------------------------ |
| Testes funcionais realizados            | Parcial   | Registro, login e consulta de usuário estão integrados e funcionando; executar endereço, produto, estoque, fornecedor, checkout e pagamento |
| Correções aplicadas conforme feedback | Pendente  | Registrar commits de correção durante a sprint                                                 |
| Evidências dos testes registradas      | Parcial   | Assets locais registrados em `docs/assets` e vídeo não listado anexado; faltam resultados formais de teste |

### Checklist final da Sprint #06

- [X] Endpoints oficiais definidos.
- [X] Autenticação implementada, mas com revalidação de contrato pendente em 31/07/2026.
- [ ] Cadastro de endereço validado.
- [ ] Produto e upload de imagem validados.
- [ ] Fornecedor e associação fornecedor-produto validados.
- [X] Estoque e movimentação validados.
- [ ] Checkout, pedido e pagamento validados.
- [X] Mockup de alta fidelidade usado como referência visual.
- [X] Prints de organização frontend/backend anexados em `docs/assets`.
- [X] Prints de integração backend anexados em `docs/assets`.
- [X] Vídeo não listado do site registrado.
- [X] Evidências funcionais com resultado esperado/obtido documentadas.
- [ ] Documentação final da sprint atualizada após validação funcional.

## Sprint #07

### Objetivo da sprint

Atualizar a visão real do projeto depois da retomada de julho, registrando os commits mais recentes, a participação por área, o que foi entregue e os pontos em que o código ainda não confirma totalmente o que está previsto na documentação.

### Branches e commits de evidência

| Repositório | Branch | Evidências |
|---|---|---|
| `toquedemulher-frontend` | `main`, `feat/dark-mode-themes` | `f4fc4dc` refatora carrinho/gamificação, rotas e API client; `85d4543` ajusta tipos de autenticação e normalização; `fcaca5b` melhora footer, branding e confetti no checkout; `33e97e0` implementa theme switcher no perfil e melhora categoria |
| `toquedemulher-backend` | `origin/backend-review` | `ebc69ac` melhora autenticação de usuário e endpoints de produto; a branch ainda não aparece como `main` local |
| `docs` | `main`, `docs/consolidacao-plano-projeto` | `0bd74f1` reorganiza README/sidebar; `9ca79c3` a `c3e9bd4` consolidam escopo, requisitos, arquitetura, modelo de dados, fluxos, tecnologias, testes, desafios e sidebar |

### Desenvolvimento da Sprint #07

| Item | Resultado |
|---|---|
| Refinamento do frontend | Houve reorganização de providers, rotas, `api-client`, contexto de carrinho, contexto de gamificação, autenticação, footer, checkout visual e tema |
| Revisão backend | Há evolução em branch de revisão, mas a `main` local ainda monta os routers legados diretamente em `app/main.py` |
| Consolidação documental | A documentação foi ampliada em 31/07 com requisitos, arquitetura, fluxos, modelo de dados, tecnologias, testes e desafios |
| Auditoria de consistência | A leitura do código confirma parte relevante do escopo, mas também mostra pendências de integração e contratos |

### O que faz sentido entre código e documentação

- A stack documentada está coerente com o código atual: React, TypeScript, Vite e Axios no frontend; FastAPI, Python, Pydantic, JWT, SQLAlchemy/SQLModel e PostgreSQL no backend.
- O frontend possui telas e rotas compatíveis com o MVP: home, catálogo, categoria, produto, busca, carrinho, checkout visual, login/cadastro, perfil, endereço, painel admin, cadastro de produto, missões e ranking.
- O backend possui modelos e routers para usuários, endereços, produtos, pagamentos, fornecedores, associação fornecedor-produto e estoque.
- A documentação registra corretamente a divergência histórica entre o planejamento inicial com Node.js e a implementação real em FastAPI/Python.
- O relatório de desafios está coerente ao apontar integração frontend-backend, autenticação, pagamentos, estoque e documentação como pontos críticos.

### Pontos que ainda não fecham com o código

| Tema | Situação encontrada em 31/07/2026 | Impacto |
|---|---|---|
| Rotas oficiais backend | `app/main.py` monta routers legados diretamente; `app/api/v1/router.py` existe, mas não é incluído no `main.py` | A API oficial ainda precisa ser consolidada |
| API nova | `app/api/v1/endpoints/products.py` possui erro de sintaxe por mistura de tabs e espaços; alguns endpoints novos importam nomes de modelos que não existem no código atual | A árvore nova `/auth`, `/users`, `/products`, `/orders`, `/payments` e `/reviews` não deve ser tratada como pronta |
| Autenticação frontend-backend | O frontend chama `/api/v1/user/login`, `/api/v1/user/register` e `/api/v1/user/me`; as rotas existem, mas o login backend não retorna `refresh_token` e o `/me` legado não retorna `id` nem `role` | Login pode funcionar parcialmente, mas perfil/admin e normalização de usuário precisam de contrato ajustado |
| Produtos admin | O frontend envia payload no formato da API nova em `/api/v1/products`, enquanto o backend ativo expõe `/products` e espera outro payload, incluindo `slug` | Cadastro de produto admin não está comprovado ponta a ponta |
| Endereço | O frontend usa `/api/v1/addresses`; o backend ativo monta `/addresses` sem o prefixo `/api/v1` | Cadastro de endereço precisa ajuste de rota ou prefixo |
| Checkout e pedido | O checkout frontend valida dados localmente, confirma pedido, limpa carrinho e aplica gamificação sem chamar API de pedido/pagamento | Fluxo comercial completo continua parcial |
| Estoque e pagamento | O checkout backend reduz estoque antes da confirmação efetiva do pagamento; a documentação descreve baixa após confirmação/webhook | Regra de negócio precisa revisão para evitar baixa indevida |
| Testes automatizados | Existe `tests/test_auth.py`, mas ele espera `/api/v1/auth`, `/api/v1/users/me` e `/health`, que não são montados no `main.py` atual; `pytest` não está instalado no ambiente local | Testes estão desatualizados ou não executáveis no snapshot atual |

### Participação por área

As contagens abaixo vêm dos metadados do Git. Elas indicam volume registrado, não medem complexidade individual nem trabalho fora do commit.

| Área | Maior participação registrada | Outros participantes relevantes | Leitura |
|---|---|---|---|
| Frontend | Maria, com 36 commits somando os aliases `eguchi@ibm.com` e `maryeguchi6@gmail.com` | João Gabriel, Zouares, Jpzin1, GuHenriquee e Maria Eduarda | Maria concentrou a maior parte da construção e refinamento visual/UX; João Gabriel atuou em busca; Zouares em navegação e endereço; Jpzin1 em tema/acessibilidade |
| Backend | GuHenriquee/Gustavo Henrique, com 43 commits no mesmo e-mail `gguu.henri@gmail.com` | Matheus Musashi, Maria, Manus AI e Maria Eduarda | GuHenriquee liderou a evolução funcional do backend: pagamentos, usuários, endereços, fornecedores e estoque; Matheus concentrou correções de segurança/dependências |
| Documentação | Maria, com 33 commits nos aliases `eguchi@ibm.com` e `maryeguchi6@gmail.com` | ccarolmdlima/Carolina, Marichoii/Maria Eduarda e Manus AI | Maria manteve a documentação histórica; ccarolmdlima liderou a consolidação técnica de 31/07 |
| Visão geral | Maria aparece como maior participação transversal em frontend e documentação; GuHenriquee aparece como maior participação técnica de backend | Equipe distribuída por especialidade | A evolução do projeto ficou concentrada em Maria no frontend/docs e GuHenriquee no backend |

### Status da Sprint #07

Sprint **em validação**. O frontend compila em TypeScript (`npx tsc --noEmit`) e a documentação foi atualizada. O backend foi analisado estaticamente, mas não foi executado porque as dependências Python não estão instaladas no ambiente local. A checagem de sintaxe apontou erro em `app/api/v1/endpoints/products.py`, e os contratos frontend-backend ainda precisam ser fechados antes de declarar o MVP como integrado.

## Pendências para fechamento formal

| Pendência                     | Motivo                                                                                            | Ação recomendada                                                                                           |
| ------------------------------ | ------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------ |
| Registro detalhado das dailies | Os alinhamentos são semanais, normalmente das 21h às 22h30, com extensão eventual até 23h; o progresso é acompanhado pelos logs do GitHub | Consolidar data, progresso, impedimentos e plano quando houver ata formal |
| Evidências visuais            | Prints centralizadas no Google Docs, assets locais em `docs/assets` e vídeo não listado no YouTube | Manter Google Docs, assets locais e link do vídeo como evidências complementares |
| Testes automatizados           | Relatório de testes automatizados ainda não foi anexado                                         | Executar testes existentes ou documentar teste manual funcional                                              |
| Rotas oficiais do backend      | Existem routers legados montados no `main.py` e estrutura adicional em `app/api/v1/router.py`, mas a estrutura nova não está montada e possui erro de sintaxe em `products.py` | Consolidar ou documentar oficialmente a rota principal antes de novas integrações |
| Integração frontend-backend  | Autenticação possui rotas compatíveis, mas o contrato de resposta ainda diverge; produto, endereço, pedido e pagamento seguem sem validação completa | Ajustar contratos, payloads e prefixos; depois executar teste ponta a ponta dos fluxos restantes |
| Fluxo comercial completo       | Pedido, pagamento e baixa de estoque precisam de validação integrada                            | Priorizar Sprint #06 antes de novas features                                                                 |
