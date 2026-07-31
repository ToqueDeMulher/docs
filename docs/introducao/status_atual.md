# Status Atual da Implementação

Este documento registra o estado do código versionado até **31 de julho de 2026**. A atualização foi feita a partir dos logs Git dos repositórios `toquedemulher-frontend`, `toquedemulher-backend` e `docs`, além da leitura dos arquivos principais de rotas, serviços, modelos, contratos frontend e documentação.

## Resumo executivo

O projeto evoluiu para um MVP navegável no frontend e uma base backend ampla, com autenticação, produtos, usuários, endereços, pagamentos, fornecedores, estoque e associação fornecedor-produto. O estado geral do MVP ainda é **parcial/em validação**: existem rotas e telas para os fluxos principais, mas os contratos entre frontend e backend ainda apresentam divergências em autenticação, endereço, produto, checkout, pedido e pagamento.

## Arquitetura efetiva do snapshot

- **Frontend:** `React 18`, `TypeScript`, `Vite`, `React Router`, Radix UI, serviços HTTP centralizados e `axios` adicionado em maio.
- **Backend:** `FastAPI`, modelos SQLAlchemy/SQLModel, CORS, arquivos estáticos, autenticação JWT, pagamento, fornecedores e estoque.
- **Documentação:** docs atualizados com acompanhamento de sprints, mockup de alta fidelidade, prints de evidência em `docs/assets`, vídeo não listado de demonstração do site e consolidação técnica em 31/07/2026.

> Observação importante: os documentos de planejamento citam `React + Node.js` como direção tecnológica, mas o código versionado usa `React + FastAPI/Python`.

## O que já está implementado

### Frontend

- home, catálogo por categoria, busca e página de produto;
- carrinho e checkout em etapas;
- login, cadastro, perfil e tela de cadastro de endereço com autocompletar por CEP;
- páginas institucionais, ajuda, sobre e página de erro;
- área administrativa protegida por `RequireAdmin`;
- dashboard administrativo e cadastro de produto com upload de imagem;
- páginas de gamificação de produtos (`missões` e `ranking`);
- tema claro/escuro, refinamentos de estilo, footer revisado, confetti no checkout e melhorias de UI/UX registradas até 27/07/2026;
- identidade visual ajustada a pedido da cliente, com preto como cor predominante no lugar do rosa;
- fontes ajustadas de `Inter` para `All Round Gothic` e `Noto Sans`;
- centralização de serviços em `apiClient`, `authService`, `productService` e `addressService`;
- checagem TypeScript executada em 31/07/2026 com `npx tsc --noEmit` sem erros.

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
- estrutura adicional em `app/api/v1/router.py` com routers para `/auth`, `/users`, `/products`, `/cart`, `/orders`, `/payments` e `/reviews`, ainda não montada no `main.py` atual;
- branch remota `origin/backend-review` com commit de 27/07/2026 para autenticação e produtos, ainda separada da `main` local.

## Evidência visual

O mockup de alta fidelidade, os prints de organização/integração e o vídeo não listado do site foram registrados em [Protótipo e Evidências Visuais](prototipo.md). Eles servem como referência para comparar a direção visual planejada com as telas implementadas e para comprovar avanços técnicos do frontend/backend.

As mudanças visuais principais em relação ao mockup foram a troca da predominância do rosa para o preto, a pedido da cliente, a troca de `Inter` por `All Round Gothic` e `Noto Sans`, e a inclusão da gamificação de produtos. O restante da estrutura visual foi mantido.

## Validação e integração observada

| Fluxo | Status | Observação |
|---|---|---|
| Registro de usuário | Parcialmente alinhado | Frontend envia `name`, `email` e `password` para `/api/v1/user/register`, rota existente no backend legado |
| Login | Parcialmente alinhado | Frontend chama `/api/v1/user/login`, mas espera `refresh_token`; backend legado retorna `access_token` e `token_type` |
| Consulta de usuário autenticado (`/user/me`) | Parcialmente alinhada | Frontend espera `id`, `name`, `email` e `role`; backend legado retorna dados de perfil sem `id` e `role` |
| Frontend | Validado estaticamente | `npx tsc --noEmit` executado sem erros em 31/07/2026 |
| Backend | Não validado em runtime local | Dependências Python não estão instaladas no ambiente local; análise estática apontou erro de sintaxe em `app/api/v1/endpoints/products.py` |

## O que está parcial ou desalinhado

- o backend possui uma estrutura versionada em `app/api/v1/router.py`, mas o `app/main.py` monta routers legados/importados individualmente;
- o frontend consome autenticação em `/user/login`, `/user/register` e `/user/me` com prefixo `/api/v1`, mas os formatos de resposta ainda não batem totalmente com os tipos usados no frontend;
- o serviço de endereço do frontend envia para `/api/v1/addresses`, enquanto o backend legado monta `/addresses/` sem o prefixo `/api/v1`;
- o serviço de produto administrativo do frontend envia para `/api/v1/products`, enquanto o backend ativo monta `/products` e espera outro payload;
- o catálogo público ainda depende de dados locais em `src/shared/data/catalog-products.ts`;
- o checkout frontend é um fluxo visual/local e não chama a API de pedido ou pagamento ao confirmar a compra;
- catálogo, endereço, produto, pedidos, baixa automática de estoque e conciliação de pagamento ainda precisam ser validados como fluxo completo;
- o checkout backend reduz estoque antes da confirmação efetiva do pagamento, enquanto a documentação descreve baixa após confirmação/webhook;
- a proteção administrativa existe no frontend e há dependência admin no backend, mas o bloqueio por perfil precisa de evidência funcional;
- o teste `tests/test_auth.py` está desalinhado com o `main.py` atual porque espera `/api/v1/auth`, `/api/v1/users/me` e `/health`;
- não há relatório de teste automatizado executado e anexado na documentação atual.

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
- corrigir a sintaxe de `app/api/v1/endpoints/products.py` antes de considerar a API nova pronta;
- alinhar o contrato funcional de autenticação, especialmente `refresh_token`, `id` e `role`;
- alinhar os contratos restantes de endereço, produto, imagem, pedido e estoque;
- conectar catálogo público à API real;
- validar checkout, pedido, pagamento e baixa de estoque de ponta a ponta;
- atualizar ou remover testes automatizados que apontam para rotas não montadas;
- registrar evidências de teste funcional nas sprints;
- substituir criação automática de tabelas por migrações Alembic quando o modelo estabilizar;
- priorizar consolidação do MVP antes de ampliar diferenciais de experiência.
