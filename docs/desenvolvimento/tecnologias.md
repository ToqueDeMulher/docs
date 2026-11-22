# Tecnologias Utilizadas

**Última atualização:** 22 de novembro de 2026

As tecnologias do projeto Toque de Mulher estão organizadas conforme suas funções na arquitetura da plataforma.

A seleção tecnológica contempla o desenvolvimento da interface, a implementação da API, a persistência de dados, as integrações externas, os testes automatizados e as ferramentas de colaboração.

Este documento considera as tecnologias identificadas na implementação e as alterações registradas nos repositórios até novembro de 2026.

---

## 1. Frontend

O frontend é responsável pela interface da loja virtual e pela interação entre os usuários e as funcionalidades da plataforma.

| Tecnologia | Finalidade |
|---|---|
| React | Construção da interface baseada em componentes reutilizáveis. |
| TypeScript | Tipagem estática e identificação de inconsistências durante o desenvolvimento. |
| Vite | Ambiente de desenvolvimento e processo de build. |
| Tailwind CSS | Estilização responsiva da interface. |
| CSS Modules | Organização de estilos associados aos componentes e páginas. |
| Axios | Comunicação HTTP entre frontend e backend. |
| React Router | Gerenciamento de rotas e navegação. |

### Organização da aplicação

O frontend utiliza componentes reutilizáveis, páginas organizadas por funcionalidades, serviços HTTP e mecanismos de gerenciamento de estado.

Entre os módulos implementados estão:

- autenticação e perfil;
- catálogo e produtos;
- carrinho e checkout;
- área administrativa;
- páginas institucionais;
- gamificação.

As atualizações de outubro e novembro incluíram melhorias na integração com a API de catálogo, na navegação, na responsividade e na experiência de compra.

---

## 2. Backend

O backend é responsável pela API, pelas regras de negócio e pela comunicação com o banco de dados e serviços externos.

| Tecnologia | Finalidade |
|---|---|
| Python | Linguagem principal do backend. |
| FastAPI | Desenvolvimento da API REST. |
| Pydantic | Validação e serialização dos dados. |
| JWT | Autenticação baseada em tokens. |
| Bcrypt | Proteção de senhas por hash. |
| SQLAlchemy | Mapeamento objeto-relacional e operações de persistência. |
| SQLModel | Organização de modelos e persistência, conforme os módulos que o utilizam. |

### Principais responsabilidades

O backend contempla funcionalidades relacionadas a:

- autenticação e gerenciamento de usuários;
- produtos e catálogo;
- carrinho e checkout;
- pagamentos;
- estoque;
- fornecedores;
- endereços;
- frete e envio;
- upload de arquivos;
- comunicação por e-mail.

Durante a revisão técnica de setembro de 2026, foram removidas estruturas experimentais, rotas legadas e dependências sem utilização identificada.

Em outubro e novembro, a API recebeu melhorias nas integrações, nas validações e na segurança.

---

## 3. Banco de dados e armazenamento

| Tecnologia ou serviço | Finalidade |
|---|---|
| PostgreSQL | Persistência dos dados relacionais da plataforma. |
| Supabase | Infraestrutura utilizada na conexão e administração dos dados, conforme a configuração do backend. |
| Supabase Storage | Armazenamento persistente de avatares de usuários. |
| Migrações SQL | Aplicação de alterações e correções na estrutura e nos dados do banco. |

### Integridade e manutenção

O backend recebeu melhorias relacionadas a:

- configuração de conexões;
- pooling e tempos limite;
- diagnósticos de banco de dados;
- verificações de integridade;
- correção de registros de estoque ausentes;
- validação de valores monetários;
- consistência de operações concorrentes.

Os commits recentes também registram arquivos de migração no diretório `supabase/migrations`.

### Observação sobre o Alembic

A configuração antiga do Alembic foi removida durante a revisão técnica de setembro de 2026.

Por esse motivo, o Alembic não é apresentado como a ferramenta atual de migrações sem uma nova confirmação de sua utilização no repositório.

---

## 4. Integrações externas

A plataforma utiliza serviços externos para complementar as funcionalidades de pagamento, envio, armazenamento e comunicação.

| Tecnologia ou serviço | Finalidade |
|---|---|
| AbacatePay | Integração de checkout, operações de pagamento e processamento de eventos por webhook. |
| Melhor Envio | Integração relacionada às operações de frete e envio. |
| Supabase Storage | Persistência de arquivos associados aos usuários. |
| Serviço de e-mail | Envio de comunicações relacionadas a autenticação e recuperação de acesso. |

### AbacatePay

A integração com AbacatePay foi incorporada em novembro de 2026.

O backend recebeu componentes específicos para comunicação com o serviço, processamento de eventos por webhook e acompanhamento das operações de pagamento.

O frontend também recebeu alterações para utilizar o fluxo de pagamento integrado.

### Integrações anteriores de pagamento

A documentação anterior mencionava Mercado Pago e Stripe.

O Mercado Pago foi removido das dependências identificadas na revisão técnica de setembro.

Posteriormente, o projeto passou a utilizar Stripe Hosted Checkout, conforme a documentação daquele período.

Em novembro, foi incorporada a integração com AbacatePay.

A situação da Stripe deve ser confirmada na implementação atual antes de ser classificada como removida, substituída integralmente ou mantida como alternativa.

---

## 5. Testes automatizados

A infraestrutura de testes foi ampliada nos repositórios de frontend e backend.

### Frontend

| Tecnologia | Finalidade |
|---|---|
| Vitest | Execução de testes unitários. |
| Testing Library | Testes de componentes e interações da interface. |
| jsdom | Simulação de ambiente de navegador durante testes. |
| Playwright | Automação de testes ponta a ponta (E2E). |

Os testes adicionados contemplam áreas como carrinho, API, componentes, formulários e fluxos de compra.

Também foi incluído um teste de compra integrado à API FastAPI.

### Backend

| Tecnologia | Finalidade |
|---|---|
| pytest | Organização e execução de testes automatizados. |
| PostgreSQL | Banco utilizado em cenários de integração e concorrência. |
| Ruff | Análise estática e verificação de qualidade do código Python. |
| pip-audit | Auditoria de vulnerabilidades em dependências Python. |
| Ferramentas de cobertura | Medição da cobertura dos testes automatizados. |

As alterações registradas incluem testes relacionados a autenticação, catálogo, pagamentos, estoque, concorrência, banco de dados e serviços internos.

**Observação:** a presença das ferramentas e dos testes nos repositórios não comprova que todas as execuções foram aprovadas. Os resultados devem ser consultados nos registros de integração contínua.

---

## 6. Integração contínua e qualidade

| Tecnologia ou ferramenta | Finalidade |
|---|---|
| GitHub Actions | Execução automatizada de verificações e testes nos repositórios. |
| TypeScript | Verificação estática dos tipos utilizados no frontend. |
| Vite Build | Verificação do processo de compilação da aplicação. |
| Playwright | Execução de testes E2E nos workflows configurados. |
| pytest | Execução dos testes automatizados do backend. |
| Ruff | Verificação estática do código Python. |
| pip-audit | Auditoria de segurança das dependências Python. |

Os workflows de integração contínua foram ampliados em novembro de 2026.

No frontend, foram adicionadas verificações relacionadas a TypeScript, build e testes.

No backend, foram incorporadas verificações com PostgreSQL, cobertura, Ruff e pip-audit.

Essas ferramentas contribuem para a identificação antecipada de falhas e regressões.

---

## 7. Desenvolvimento e colaboração

| Ferramenta | Finalidade |
|---|---|
| Git | Controle de versão do código e da documentação. |
| GitHub | Hospedagem dos repositórios, colaboração e revisão de alterações. |
| GitHub Projects | Organização das atividades e acompanhamento do desenvolvimento. |
| GitHub Actions | Automação de testes e verificações de integração contínua. |
| Figma | Prototipação visual e referência para a interface. |
| Visual Studio Code | Ambiente de desenvolvimento. |
| GitHub Pages | Publicação da documentação. |
| Markdown | Escrita e manutenção da documentação técnica. |
| Docsify | Organização e apresentação da documentação em Markdown. |

### Organização dos repositórios

O projeto possui repositórios separados para:

- frontend;
- backend;
- documentação.

Essa divisão facilita a manutenção das diferentes partes da plataforma e permite acompanhar as alterações por meio do histórico de commits e Pull Requests.

---

## 8. Evolução tecnológica

| Período | Principais alterações |
|---|---|
| Planejamento inicial | Previsão de React e Node.js. |
| Implementação | Adoção de React e TypeScript no frontend e FastAPI/Python no backend. |
| Setembro de 2026 | Remoção de dependências legadas, simplificação da autenticação e revisão de segurança. |
| Outubro de 2026 | Integração do catálogo com a API e inclusão de testes E2E no frontend. |
| Novembro de 2026 | Integração com AbacatePay, melhorias em Supabase, ampliação dos testes automatizados e workflows de CI. |

---

## 9. Observações

A presença de uma tecnologia no planejamento não garante que ela esteja completamente configurada ou em produção.

Da mesma forma, a existência de bibliotecas, testes ou workflows nos repositórios não comprova que todas as funcionalidades foram validadas.

O estado efetivo deve ser comparado com a implementação atual, os resultados dos testes e as evidências disponíveis.

Para mais informações, consulte:

- [Status Atual da Implementação](../introducao/status_atual.md)
- [Arquitetura do Sistema](arquitetura.md)
- [Testes e Validações](testes.md)

### Repositórios

- [Frontend](https://github.com/ToqueDeMulher/toquedemulher-frontend)
- [Backend](https://github.com/ToqueDeMulher/toquedemulher-backend)
- [Documentação](https://github.com/ToqueDeMulher/docs)