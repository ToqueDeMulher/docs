# Status Atual da Implementação

Este documento registra o estado do código versionado até **24 de maio de 2026**, com revisão documental em **5 de junho de 2026**. A atualização foi feita a partir dos logs Git dos repositórios `toquedemulher-frontend`, `toquedemulher-backend` e `docs`, além da leitura dos arquivos principais de rotas e serviços.

## Resumo executivo

O projeto evoluiu para um MVP navegável no frontend e uma base backend mais ampla, com autenticação, produtos, usuários, endereços, pagamentos, fornecedores, estoque e associação fornecedor-produto. A integração de **registro, login e consulta de usuário autenticado** já está funcionando entre frontend e backend. O estado geral do MVP ainda é **parcial/em validação**, porque os demais fluxos de catálogo, endereço, produto, estoque, pedido e pagamento ainda precisam de validação de ponta a ponta documentada.

## Arquitetura efetiva do snapshot

- **Frontend:** `React 18`, `TypeScript`, `Vite`, `React Router`, Radix UI, serviços HTTP centralizados e `axios` adicionado em maio.
- **Backend:** `FastAPI`, modelos SQLAlchemy/SQLModel, CORS, arquivos estáticos, autenticação JWT, pagamento, fornecedores e estoque.
- **Documentação:** docs atualizados com acompanhamento de sprints, mockup de alta fidelidade, prints de evidência em `docs/assets` e vídeo não listado de demonstração do site.

> Observação importante: os documentos de planejamento citam `React + Node.js` como direção tecnológica, mas o código versionado usa `React + FastAPI/Python`.

## O que já está implementado

### Frontend

- home, catálogo por categoria, busca e página de produto;
- carrinho e checkout em etapas;
- login, cadastro, perfil e tela de cadastro de endereço com autocompletar por CEP;
- páginas institucionais, ajuda, sobre e página de erro;
- área administrativa protegida por `RequireAdmin`;
- dashboard administrativo e cadastro de produto com upload de imagem;
- páginas de gamificação (`missões` e `ranking`);
- tema claro/escuro, refinamentos de estilo e melhorias de UI/UX registradas até 24/05/2026;
- centralização de serviços em `apiClient`, `authService`, `productService` e `addressService`.

### Backend

- inicialização da API com CORS, arquivos estáticos e criação de tabelas no startup;
- rotas montadas no `app/main.py` para produto, pagamento, usuário, login, endereço, fornecedor, estoque e associação fornecedor-produto;
- criação de produto, upload de imagem e lógica relacionada a fornecedor/produto;
- registro, login, consulta e alteração de usuário na estrutura legada `/api/v1/user`;
- checkout/pagamento e webhooks de pagamento presentes;
- CRUD de endereço;
- gestão de fornecedores;
- associação fornecedor-produto;
- criação, consulta, alteração, exclusão e movimentação de estoque;
- estrutura adicional em `app/api/v1/router.py` com routers para `/auth`, `/users`, `/products`, `/cart`, `/orders`, `/payments` e `/reviews`, ainda não montada no `main.py` atual.

## Evidência visual

O mockup de alta fidelidade, os prints de organização/integração e o vídeo não listado do site foram registrados em [Protótipo e Evidências Visuais](prototipo.md). Eles servem como referência para comparar a direção visual planejada com as telas implementadas e para comprovar avanços técnicos do frontend/backend.

## Integração validada

| Fluxo | Status | Observação |
|---|---|---|
| Registro de usuário | Integrado e funcionando | Frontend envia os dados de cadastro para o backend e recebe resposta esperada |
| Login | Integrado e funcionando | Frontend autentica no backend e mantém a sessão com token |
| Consulta de usuário autenticado (`get user`/`me`) | Integrado e funcionando | Frontend consegue recuperar os dados do usuário logado a partir do backend |

## O que está parcial ou desalinhado

- o backend possui uma estrutura versionada em `app/api/v1/router.py`, mas o `app/main.py` monta routers legados/importados individualmente;
- o frontend consome autenticação em `/user/login`, `/user/register` e `/user/me`, e essa integração está funcionando; ainda existe, porém, uma estrutura alternativa no backend novo com `/auth/*` e `/users/*`;
- o serviço de endereço do frontend envia para `/addresses`, enquanto o backend legado monta `/addresses/`;
- o catálogo público ainda depende de dados locais em `src/shared/data/catalog-products.ts`;
- catálogo, endereço, produto, pedidos, baixa automática de estoque e conciliação de pagamento ainda precisam ser validados como fluxo completo;
- a proteção administrativa existe no frontend e há dependência admin no backend, mas o bloqueio por perfil precisa de evidência funcional;
- não há relatório de teste automatizado anexado na documentação atual.

## Recursos previstos mas ainda não implementados

Os itens abaixo aparecem nos planos de projeto e permanecem como backlog:

- busca avançada com tolerância a erro e autocomplete completo integrado à API;
- rotina personalizada de produtos (`routine builder`);
- comparador inteligente de produtos;
- wishlist social e notificações de interesse;
- programa de fidelidade por níveis;
- avaliações com foto e vídeo em produção;
- PWA, modo offline e notificações push;
- painel de privacidade e consentimento LGPD granular;
- relatórios administrativos completos.

## Próximos passos recomendados

- escolher uma única estrutura de roteamento no backend e montar a API principal de forma consistente;
- manter documentado o contrato funcional de autenticação e alinhar os contratos restantes de endereço, produto, imagem, pedido e estoque;
- conectar catálogo público à API real;
- validar checkout, pedido, pagamento e baixa de estoque de ponta a ponta;
- registrar evidências de teste funcional nas sprints;
- substituir criação automática de tabelas por migrações Alembic quando o modelo estabilizar;
- priorizar consolidação do MVP antes de ampliar diferenciais de experiência.
