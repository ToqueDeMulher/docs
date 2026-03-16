# Status Atual da Implementação

Este documento registra o estado do código versionado em **16 de março de 2026** e cruza o planejamento do projeto com o que realmente existe no repositório hoje.

## Resumo executivo

O projeto já possui frontend navegável e backend funcional para partes do fluxo comercial, mas o MVP ainda está **parcial**. Há recursos importantes implementados visualmente no frontend e serviços relevantes no backend, porém ainda existem desalinhamentos entre contratos, rotas e responsabilidades dos dois lados.

## Arquitetura efetiva do snapshot

- **Frontend:** `React 18`, `TypeScript`, `Vite`, `React Router` e componentes próprios.
- **Backend:** `FastAPI` com `SQLModel`, CORS configurado, upload de imagens e integração com Mercado Pago.
- **Persistência:** criação de tabelas no startup da aplicação; imagens enviadas para Supabase.

> Observação importante: os documentos de planejamento citam `React + Node.js` como direção tecnológica, mas o código versionado hoje usa `React + FastAPI/Python`.

## O que já está implementado

### Frontend

- home, catálogo por categoria e página de produto;
- carrinho e checkout em etapas (`endereço`, `pagamento`, `confirmação`);
- login, perfil e páginas institucionais;
- dashboard administrativo e tela de cadastro de produto;
- páginas de gamificação (`missões` e `ranking`);
- persistência local de carrinho com `localStorage`.

### Backend

- inicialização da API com CORS e arquivos estáticos;
- criação de produto com supplier, brand, description, categories, stock e imagens;
- upload de imagem de produto com validação de tipo;
- geração de preferência de pagamento com Mercado Pago;
- criação de usuário;
- webhook de pagamento presente em arquivo, mas ainda não acoplado ao `app.main`.

## O que está parcial ou desalinhado

- o frontend de autenticação consome rotas como `/auth/login`, `/auth/register` e `/users/me`, mas o backend montado hoje expõe apenas `/user/createUser`;
- existe um arquivo de login no backend, porém ele não está registrado em `app/main.py`;
- o frontend envia upload para `/products/{id}/images`, enquanto o backend publica `/products/{product_id}/images/upload`;
- o payload de criação de produto no frontend não segue o schema de `CreateProductRequest` do backend;
- o catálogo público do frontend ainda usa dados locais em `src/shared/data/catalog-products.ts`, e não leitura dinâmica da API;
- checkout, pedido e baixa automática de estoque ainda não aparecem como fluxo persistido de ponta a ponta;
- relatórios, gestão de pedidos e painel administrativo completo continuam pendentes no backend.

## Recursos previstos mas ainda não implementados

Os itens abaixo aparecem nos planos de projeto e permanecem como backlog:

- busca avançada e fuzzy search;
- rotina personalizada de produtos (`routine builder`);
- comparador inteligente de produtos;
- wishlist social e notificações de interesse;
- programa de fidelidade por níveis;
- avaliações com foto e vídeo;
- PWA, modo offline e notificações push;
- painel de privacidade e consentimento LGPD granular.

## Próximos passos recomendados

- alinhar contratos entre frontend e backend antes de ampliar o escopo;
- conectar catálogo, autenticação e checkout à API real;
- registrar e finalizar o fluxo de pedidos, webhook e baixa de estoque;
- substituir `create_all` por migrações formais de banco;
- usar o roadmap para priorizar primeiro a consolidação do MVP e só depois os diferenciais de experiência.
