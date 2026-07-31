# Testes e Validações

Os testes da plataforma Toque de Mulher têm como objetivo verificar funcionalidades, integrações e fluxos principais do sistema.

## Testes internos

Os testes internos são executados pela equipe durante o desenvolvimento.

As validações descritas no relatório incluem:

- cadastro de usuários;
- autenticação;
- navegação entre páginas;
- carrinho;
- checkout;
- processamento de pedidos;
- controle de estoque;
- validação de endpoints da API.

Esses testes auxiliam na identificação de:

- erros de integração;
- inconsistências de dados;
- falhas nas regras de negócio;
- problemas de navegação;
- ajustes necessários na interface.

## Testes alfa

Os testes alfa correspondem a avaliações controladas com participantes convidados e pessoas externas à equipe.

Os aspectos observados incluem:

- clareza da interface;
- facilidade de navegação;
- compreensão do fluxo de compra;
- experiência geral do usuário.

Os feedbacks obtidos podem ser utilizados para refinamentos de usabilidade e interface.

## Testes beta

O relatório informa que testes beta formais com stakeholders reais ainda não foram executados em ambiente de produção.

Essa etapa permanece prevista para o futuro.

## Validação atual

| Fluxo | Situação |
|---|---|
| Frontend | Verificado estaticamente e sem erros de TypeScript |
| Cadastro e login | Implementados, mas ainda precisam de contrato final validado |
| Perfil do usuário | Implementado, mas precisa confirmar dados e permissões vindos do backend |
| Endereço, produto, checkout, pagamento e estoque | Ainda precisam de teste integrado |
| Backend | Precisa ser executado em ambiente com dependências instaladas |

## Fluxos que ainda precisam de evidência completa

- catálogo conectado à API;
- cadastro e consulta de endereço;
- gerenciamento de produtos;
- criação de pedidos;
- checkout completo;
- pagamento;
- webhook;
- baixa automática de estoque;
- controle de acesso administrativo.

## Testes automatizados

A documentação atual ainda não possui um relatório consolidado de testes automatizados executados com sucesso.

O backend possui testes versionados, mas eles precisam ser atualizados para refletir as rotas realmente usadas pela aplicação. Até essa revisão, os testes não devem ser usados como prova formal de fechamento do MVP.

Permanecem recomendados:

- testes unitários;
- testes de integração;
- testes de API;
- testes de sistema;
- testes ponta a ponta;
- testes de regressão.

## Registro de evidências

As evidências de testes devem incluir, quando possível:

- data;
- funcionalidade;
- ambiente;
- responsável;
- resultado esperado;
- resultado obtido;
- situação;
- imagem, vídeo ou log;
- referência ao commit ou Pull Request.
