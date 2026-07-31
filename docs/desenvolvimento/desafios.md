# Desafios Encontrados

Durante o desenvolvimento da plataforma Toque de Mulher, foram identificados desafios técnicos e organizacionais.

Esses desafios exigiram adaptações arquiteturais, alinhamento entre os integrantes e refinamento das atividades planejadas.

## Integração entre frontend e backend

A comunicação entre o frontend em React e a API em FastAPI exige alinhamento entre:

- URLs;
- métodos HTTP;
- formatos de requisição;
- formatos de resposta;
- nomes dos campos;
- tratamento de erros;
- autenticação.

Diferenças entre contratos podem impedir que funcionalidades aparentemente concluídas funcionem de ponta a ponta.

## Autenticação e controle de acesso

A autenticação com JWT exige atenção em:

- armazenamento do token;
- validade da sessão;
- proteção de rotas;
- recuperação do usuário autenticado;
- diferenciação entre usuário comum e administrador.

## Modelagem de dados

A modelagem precisa manter consistência entre:

- usuários;
- produtos;
- categorias;
- carrinho;
- pedidos;
- pagamentos;
- estoque;
- fornecedores;
- avaliações.

Alterações nas entidades podem exigir atualização dos modelos, rotas, serviços e banco de dados.

## Integração com pagamentos

A integração com o Mercado Pago envolve processamento assíncrono.

Os principais desafios incluem:

- criação da transação;
- retorno do pagamento;
- tratamento de falhas;
- webhooks;
- atualização do pedido;
- prevenção de inconsistências.

## Controle de estoque

O estoque deve permanecer consistente durante:

- cadastro de produtos;
- entradas;
- saídas;
- cancelamentos;
- pedidos;
- pagamentos;
- alterações administrativas.

## Mudanças de requisitos

Durante o desenvolvimento ocorreram ajustes de escopo, identidade visual e direção técnica.

Entre as mudanças registradas estão:

- substituição da predominância do rosa pelo preto;
- alteração das fontes;
- inclusão de gamificação;
- adoção de FastAPI em vez de Node.js;
- evolução dos módulos de estoque e fornecedores.

## Gestão e comunicação

A organização das entregas em sprints exige comunicação contínua entre:

- planejamento;
- frontend;
- backend;
- testes;
- documentação;
- stakeholders.

## Documentação

Um desafio importante é manter uma única fonte de verdade.

Sempre que houver divergência entre o plano e a implementação, ela deve ser registrada explicitamente, sem apagar o histórico da decisão.