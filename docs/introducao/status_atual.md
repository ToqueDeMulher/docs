# Status Atual da Implementação

Este documento registra o estado do projeto até **31 de julho de 2026**, considerando código, documentação e histórico de commits dos repositórios de frontend, backend e docs.

## Resumo executivo

O projeto já possui uma boa base de MVP: a loja é navegável, a identidade visual está mais madura e o backend cobre as principais áreas do negócio. Ainda assim, o MVP segue **parcial/em validação**, porque alguns fluxos existem na tela e no backend, mas ainda não estão totalmente conectados e comprovados de ponta a ponta.

## Arquitetura efetiva do snapshot

- **Frontend:** loja web em React, com navegação, catálogo, carrinho, checkout visual, autenticação, área administrativa e gamificação.
- **Backend:** API em FastAPI/Python, com base para usuários, produtos, pagamentos, fornecedores, endereços e estoque.
- **Documentação:** materiais atualizados com sprints, status, requisitos, arquitetura, testes, desafios, protótipo e evidências visuais.

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

## Validação atual

| Fluxo | Status | Observação |
|---|---|---|
| Frontend | Consistente para demonstração | A checagem TypeScript passou sem erros |
| Cadastro e login | Parcial | Existem no frontend e no backend, mas o contrato de resposta ainda precisa ser ajustado |
| Perfil e acesso admin | Parcial | A tela existe, mas os dados de perfil/permissão precisam estar alinhados com o backend |
| Endereço e produto admin | Parcial | Existem telas e rotas, mas falta validação integrada |
| Checkout, pedido e pagamento | Parcial | O fluxo visual existe, mas ainda não fecha compra real de ponta a ponta |
| Backend | Em revisão | Ainda precisa de ambiente validado, correção técnica e consolidação de rotas |

## Pontos de atenção

- a loja está boa para demonstração, mas ainda não está pronta para operação comercial real;
- parte do frontend ainda usa dados locais no catálogo;
- cadastro, login, perfil e admin precisam de contrato final entre frontend e backend;
- endereço e cadastro de produto precisam ser validados em uso real;
- checkout, pedido, pagamento e baixa de estoque ainda não estão comprovados como fluxo completo;
- o backend tem duas estruturas de rota e precisa escolher uma versão oficial;
- os testes automatizados precisam ser atualizados para refletir o estado atual da aplicação.

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

- definir a API oficial do backend;
- alinhar os contratos entre frontend e backend;
- conectar catálogo público à API real;
- validar cadastro, login, perfil, endereço e produto administrativo em ambiente integrado;
- validar checkout, pedido, pagamento e estoque de ponta a ponta;
- atualizar os testes e registrar evidências funcionais;
- priorizar a consolidação do MVP antes de adicionar novas funcionalidades.
