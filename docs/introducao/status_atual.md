# Status Atual da Implementação

Este documento registra o estado do projeto até **20 de setembro de 2026**, considerando código, documentação e histórico de commits dos repositórios de frontend, backend e docs.

## Resumo executivo

O projeto possui uma base funcional de e-commerce, incluindo catálogo, carrinho, checkout, autenticação, perfil do usuário, área administrativa e gamificação.

O backend contempla funcionalidades relacionadas a usuários, produtos, pagamentos, endereços, fornecedores e estoque.

Em setembro de 2026, os repositórios passaram por uma revisão técnica para remover estruturas sem utilização identificada, reduzir dependências, simplificar a autenticação e reforçar regras de segurança e integridade dos dados.

**Situação geral:** MVP em consolidação e validação integrada.

A existência de uma funcionalidade no código não significa, por si só, que todos os seus cenários de uso tenham sido testados de ponta a ponta.

## Arquitetura atual

| Camada | Tecnologias e responsabilidades |
|---|---|---|
| Frontend | React, TypeScript e Vite; interface da loja, autenticação, carrinho, checkout e área administrativa |
| Backend | Python e FastAPI; API, regras de negócio, autenticação e integrações |
| Banco de dados | Persistência de usuários, produtos, endereços, pedidos, pagamentos, fornecedores e estoque |
| Documentação | Markdown e repositório central de documentação do projeto |

Divergência em relação ao planejamento: documentos iniciais mencionavam React e Node.js, mas a implementação efetiva utiliza React no frontend e FastAPI/Python no backend.

### Configuração de desenvolvimento

A porta documentada para execução do frontend foi corrigida de `5173` para `3000`, conforme a configuração atual do Vite.

## O que já está implementado

### Frontend

- home, catálogo por categoria, busca e página de produto;
- carrinho e checkout em etapas;
- login, cadastro, perfil e tela de cadastro de endereço com autocompletar por CEP;
- páginas institucionais, ajuda, sobre e página de erro;
- área administrativa protegida por `RequireAdmin`;
- dashboard administrativo integrado a dados de pedidos e pagamentos;
- cadastro de produto com upload de imagem;
- funcionalidades de gamificação de produtos (`missões` e `ranking`);
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

## Atualizações técnicas de setembro de 2026

### Limpeza e simplificação do frontend

Foi realizada uma revisão da base de código para remover recursos sem utilização identificada na aplicação atual.

As alterações incluíram:

- remoção de componentes antigos de skeleton/loading;
- remoção de estilos CSS legados do storefront;
- remoção do Navigation Menu do Radix e da dependência correspondente;
- remoção de imagens sem referências identificadas;
- remoção de outros componentes e dependências sem uso;
- correção da documentação da porta de desenvolvimento para `3000`.

A revisão teve como objetivo reduzir código desnecessário e facilitar a manutenção da aplicação, preservando os fluxos ativos.

### Simplificação da autenticação no frontend

O frontend passou a trabalhar apenas com access token.

O refresh token foi removido porque não existia um fluxo ativo de renovação que o utilizasse. A aplicação também passou a limpar refresh tokens antigos que eventualmente permanecessem armazenados localmente.

O comportamento após a expiração do access token deve seguir o fluxo de autenticação implementado na aplicação.

### Limpeza e simplificação do backend

Foram removidas estruturas experimentais e legadas que não integravam a API ativa, incluindo implementações antigas ou duplicadas relacionadas a autenticação, carrinho e pedidos.

Também foram removidos:

- configuração antiga do Alembic;
- modelos e tabelas legadas vazias;
- templates de e-mail sem utilização identificada;
- dependências que não eram utilizadas pelo backend atual.

Entre as dependências removidas foram citadas Flask, Selenium, bibliotecas de scraping, Pygame e Mercado Pago.

**Importante:** a remoção de rotas legadas não deve ser interpretada como remoção das funcionalidades equivalentes que permanecem disponíveis na API ativa.

### Atualização da autenticação no backend

O fluxo de refresh token foi removido do backend.

O login convencional e o login com Google passaram a retornar apenas access token.

Os access tokens passaram a ser identificados com `type=access`, e tokens de outros tipos não devem autenticar usuários em rotas protegidas.

### Melhorias de segurança

A revisão incluiu:

- exigência de permissão administrativa para upload de imagens de produtos;
- validação do tipo de token utilizado nas rotas protegidas;
- redução da exposição de detalhes internos do Supabase nas respostas de erro.

Essas alterações reforçam os controles de acesso e reduzem a exposição desnecessária de informações internas.

### Integridade dos dados

Foram adicionadas ou reforçadas validações no banco de dados para evitar situações como:

- quantidades negativas;
- preços negativos;
- mais de um endereço padrão quando a regra exigir unicidade;
- mais de um método de pagamento padrão quando a regra exigir unicidade.

As restrições devem ser consideradas nos testes de integração e regressão do sistema.

## Validação atual

| Fluxo | Status | Observação |
|---|---|---|
| Estrutura do Frontend | Implementada e revisada | Remoção de componentes e dependências sem utilização identificada |
| Autenticação | Atualizada | Fluxo simplificado para access token; verificar evidências dos cenários de login e expiração |
| Proteção administrativa | Reforçada | Upload de imagem passou a exigir permissão administrativa |
| Estrutura do Backend | Revisada | Rotas experimentais e estruturas legadas removidas |
| Integridade dos dados | Reforçada | Restrições para valores negativos e registros padrão |
| Checkout, pedido e pagamento | Implementação existente | Manter validação integrada com pedidos e estoque |
| Estoque | Parcialmente consolidado | Confirmar movimentações automáticas de saída, cancelamento e devolução |

## Pontos de atenção

Após a reorganização do backlog, as principais pendências a acompanhar são:

- alinhar o contrato de produto entre frontend e backend;
- consolidar o CRUD oficial de catálogo/produtos no backend, conforme o estado das rotas ativas;
- integrar a gestão de estoque ao frontend administrativo;
- integrar a gestão de fornecedores ao frontend administrativo;
- integrar o vínculo entre fornecedores e produtos no frontend;
- finalizar e validar as movimentações automáticas de estoque no checkout, incluindo saída e devolução quando aplicável;
- implementar o fluxo de frete;
- registrar testes de regressão após a limpeza técnica;
- confirmar a decisão de escopo sobre o Routine Builder.

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

- registrar os PRs e commits das atualizações técnicas;
- revisar os contratos de integração entre frontend e backend;
- validar os fluxos de autenticação após a remoção do refresh token;
- executar testes de regressão nas funcionalidades afetadas pela limpeza;
- validar as regras de segurança e integridade dos dados;
- concluir a integração administrativa de estoque e fornecedores;
- validar checkout, pagamento e movimentações de estoque de ponta a ponta;
- manter os Projects alinhados ao estado real da implementação.
