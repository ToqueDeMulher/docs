# Testes e Validações

**Última atualização:** 22 de novembro de 2026  
**Período de revisão:** setembro a novembro de 2026

Os testes da plataforma Toque de Mulher têm como objetivo verificar o funcionamento das funcionalidades, a integração entre os componentes e a confiabilidade dos principais fluxos do sistema.

Durante o desenvolvimento, as atividades de validação evoluíram de verificações manuais e análises estáticas para uma infraestrutura que também contempla testes automatizados, testes de integração, testes ponta a ponta e verificações de integração contínua.

Este documento apresenta os tipos de testes utilizados, as ferramentas incorporadas ao projeto, os cenários acompanhados e as evidências necessárias para comprovar os resultados.

---

## 1. Estratégia de testes

A estratégia de testes considera diferentes níveis de verificação.

| Tipo de teste | Objetivo |
|---|---|
| Testes unitários | Verificar componentes, funções e regras isoladas. |
| Testes de integração | Verificar a comunicação entre módulos, API, banco de dados e serviços. |
| Testes de API | Validar endpoints, respostas, permissões e regras de negócio. |
| Testes ponta a ponta (E2E) | Simular jornadas do usuário envolvendo diferentes componentes. |
| Testes de regressão | Identificar falhas introduzidas por alterações no código. |
| Testes estáticos | Verificar aspectos do código sem executar os fluxos completos. |
| Testes de segurança | Verificar controles de acesso, autenticação e dependências. |
| Testes de usabilidade | Avaliar clareza, navegação e experiência do usuário. |

A utilização desses níveis busca identificar problemas antes que afetem os principais fluxos da plataforma.

---

## 2. Testes internos

Os testes internos são realizados pela equipe durante o desenvolvimento e a revisão das funcionalidades.

As validações contemplam áreas como:

- cadastro e autenticação;
- confirmação de e-mail;
- recuperação de senha;
- navegação entre páginas;
- catálogo e consulta de produtos;
- carrinho;
- checkout;
- processamento de pagamentos;
- integração com AbacatePay;
- processamento de webhooks;
- gerenciamento de pedidos;
- controle de estoque;
- frete e envio;
- validação de endpoints;
- autorização administrativa;
- persistência e integridade dos dados.

Essas verificações auxiliam na identificação de erros de integração, inconsistências de dados, falhas nas regras de negócio e problemas de navegação.

A execução e os resultados de cada cenário devem ser registrados separadamente.

---

## 3. Testes automatizados do frontend

Entre outubro e novembro de 2026, o frontend recebeu uma ampliação da infraestrutura de testes automatizados.

### 3.1. Ferramentas

As ferramentas incorporadas incluem:

- **Vitest:** execução de testes unitários;
- **Testing Library:** testes de componentes e interações;
- **jsdom:** simulação de ambiente de navegador para testes;
- **Playwright:** automação de testes ponta a ponta.

### 3.2. Testes unitários e de componentes

Foram adicionados testes relacionados a:

- gerenciamento do carrinho;
- serviços e comunicação com a API;
- componentes da interface;
- formulários;
- comportamento de funcionalidades específicas da loja.

Esses testes permitem verificar regras e comportamentos de forma isolada, contribuindo para a identificação de regressões.

### 3.3. Testes ponta a ponta

A infraestrutura E2E utiliza Playwright para executar jornadas que envolvem a interface da aplicação.

Entre os cenários contemplados pelas alterações registradas estão:

- navegação pela loja;
- operações do carrinho;
- preenchimento e utilização de CEP;
- fluxo de compra integrado à API FastAPI.

A execução completa desses cenários depende da configuração correta dos serviços e do ambiente de testes.

### 3.4. Validação estática

O frontend também possui verificações relacionadas a:

- TypeScript;
- build da aplicação;
- consistência das alterações submetidas.

A checagem TypeScript executada em julho de 2026 permanece como evidência histórica. Para comprovar o estado atual, devem ser considerados os resultados das verificações realizadas após as alterações de novembro.

---

## 4. Testes automatizados do backend

O backend recebeu ampliações na cobertura de testes e na validação das regras de negócio.

### 4.1. Testes de autenticação

Foram registradas alterações em testes relacionados a:

- autenticação de usuários;
- validação de tokens;
- recuperação e redefinição de senha;
- regressões de segurança;
- gerenciamento de sessões.

Esses testes são importantes para verificar o comportamento dos mecanismos de autenticação após as revisões realizadas no sistema.

### 4.2. Testes de catálogo e produtos

A suíte contempla verificações relacionadas a:

- operações de catálogo;
- endpoints de produtos;
- validações dos dados recebidos;
- regras de negócio associadas aos produtos.

### 4.3. Testes de checkout e pagamentos

Foram adicionadas ou atualizadas verificações relacionadas a:

- validação dos dados de checkout;
- integração com AbacatePay;
- processamento de operações de pagamento;
- tratamento de eventos;
- solicitações simultâneas de checkout.

Esses cenários são relevantes para verificar a consistência das operações e evitar comportamentos duplicados ou inesperados.

### 4.4. Testes de estoque

As alterações registradas incluem testes relacionados a:

- movimentações de estoque;
- consistência dos saldos;
- operações concorrentes;
- regressões após correções na lógica de atualização;
- integridade dos registros utilizados pelo sistema.

### 4.5. Testes de banco de dados

O backend também recebeu testes e verificações envolvendo:

- integração com PostgreSQL;
- configuração de conexões;
- diagnósticos de banco;
- integridade das estruturas utilizadas;
- comportamento de operações que dependem de persistência.

### 4.6. Outros testes

Foram registradas verificações relacionadas a:

- upload de avatar;
- serviços internos;
- validações de produtos;
- endpoint `/ready`, utilizado para verificar a disponibilidade do banco de dados.

A existência desses testes no repositório não significa, por si só, que todas as execuções foram aprovadas.

---

## 5. Integração contínua (CI)

A integração contínua permite executar verificações automatizadas durante o desenvolvimento e a revisão das alterações.

### 5.1. Frontend

O frontend recebeu configurações de CI relacionadas a:

- verificação de TypeScript;
- build da aplicação;
- execução de testes;
- preparação do ambiente de testes E2E.

### 5.2. Backend

O backend recebeu configurações de CI relacionadas a:

- execução de testes automatizados;
- utilização de PostgreSQL nos testes de integração;
- verificações de cobertura;
- análise estática com Ruff;
- auditoria de dependências com pip-audit.

### 5.3. Evidências de execução

Os resultados devem ser consultados nos workflows disponíveis no GitHub Actions.

- [GitHub Actions — Frontend](https://github.com/ToqueDeMulher/toquedemulher-frontend/actions)
- [GitHub Actions — Backend](https://github.com/ToqueDeMulher/toquedemulher-backend/actions)

Para comprovar uma execução, recomenda-se registrar o link do workflow, a data, o commit analisado e o resultado apresentado.

---

## 6. Testes de segurança

As alterações técnicas realizadas no projeto também exigem verificações de segurança.

Os principais cenários incluem:

- rejeição de tokens inválidos ou de tipos não permitidos;
- proteção das rotas autenticadas;
- autorização administrativa;
- restrição do upload de imagens de produtos;
- recuperação de senha;
- invalidação ou revogação de sessões quando aplicável;
- prevenção da exposição de informações internas em respostas de erro;
- validação de dados recebidos pela API;
- auditoria de dependências.

A inclusão de ferramentas como pip-audit complementa as verificações de segurança, mas não substitui testes funcionais de autenticação e autorização.

---

## 7. Testes de integridade e concorrência

As operações de pagamento e estoque exigem atenção especial à consistência dos dados.

### Estoque

As verificações devem considerar:

- atualização correta dos saldos;
- prevenção de quantidades negativas;
- movimentações simultâneas;
- prevenção de baixas duplicadas;
- consistência entre estoque e pedidos.

### Checkout e pagamento

As verificações devem considerar:

- validação dos dados da compra;
- processamento de pagamentos;
- tratamento de eventos por webhook;
- solicitações simultâneas;
- prevenção de operações duplicadas;
- comportamento em pagamentos não concluídos.

### Frete e envio

As verificações devem considerar:

- consistência dos dados de entrega;
- integração com o serviço de envio;
- validação do estado do pagamento;
- prevenção de preparação ou pagamento indevido de etiquetas.

Esses cenários devem ser comprovados por testes e evidências de execução.

---

## 8. Testes alfa

Os testes alfa correspondem a avaliações controladas realizadas durante o desenvolvimento, incluindo participantes convidados e pessoas externas à equipe.

Os aspectos observados incluem:

- clareza da interface;
- facilidade de navegação;
- compreensão do catálogo;
- experiência com o carrinho;
- compreensão do fluxo de compra;
- acessibilidade e responsividade;
- experiência geral do usuário.

Os feedbacks obtidos podem ser utilizados para orientar melhorias de usabilidade e interface.

Os resultados específicos dessas avaliações devem permanecer associados aos registros ou relatórios correspondentes.

---

## 9. Testes beta

Até a documentação anterior, não havia registro de testes beta formais com stakeholders reais em ambiente de produção.

A execução dessa etapa deve ser confirmada por evidências posteriores antes de ser classificada como concluída.

Caso ainda não tenha ocorrido, permanece como atividade prevista para a validação do sistema em condições próximas ao uso real.

---

## 10. Situação atual das validações

| Área | Evidência identificada | Situação |
|---|---|---|
| Frontend | Testes unitários, de componentes e E2E adicionados. | Resultados de execução a confirmar. |
| TypeScript e build | Verificações incorporadas à CI. | Resultado dos workflows a confirmar. |
| Autenticação | Testes de regressão adicionados ou atualizados. | Resultados a confirmar. |
| Catálogo | Testes e integração com API registrados. | Validação integrada a confirmar. |
| Carrinho | Testes unitários e de regressão registrados. | Resultados a confirmar. |
| Checkout | Testes e melhorias registrados. | Fluxo completo a confirmar. |
| AbacatePay | Testes de integração registrados. | Resultados e cenários de webhook a confirmar. |
| Estoque | Testes de regressão e concorrência registrados. | Resultados a confirmar. |
| Banco de dados | Testes com PostgreSQL e verificações de integridade registrados. | Resultados a confirmar. |
| Frete e envio | Alterações de integração e validação de pagamento registradas. | Evidência completa a confirmar. |
| Segurança | Testes e verificações automatizadas incorporados. | Resultados a confirmar. |

**Observação:** esta tabela diferencia a existência de testes e ferramentas da comprovação de seus resultados.

---

## 11. Fluxos que ainda precisam de evidência consolidada

As seguintes áreas devem ter suas evidências revisadas para confirmar o estado de validação:

- catálogo integrado à API;
- cadastro e consulta de endereços;
- gerenciamento administrativo de produtos;
- autorização administrativa;
- criação e atualização de pedidos;
- checkout completo;
- pagamento com AbacatePay;
- processamento de webhooks;
- movimentações automáticas de estoque;
- cancelamentos e expirações;
- operações de frete e envio;
- recuperação de senha;
- integridade das migrações de banco de dados.

A ausência de evidência consolidada neste documento não significa necessariamente que os testes não tenham sido executados.

---

## 12. Registro de evidências

As evidências devem incluir, sempre que possível:

- data;
- funcionalidade;
- tipo de teste;
- ambiente;
- responsável;
- resultado esperado;
- resultado obtido;
- situação;
- imagem, vídeo ou log;
- referência ao commit ou Pull Request;
- link da execução no GitHub Actions.

### Modelo de registro

| Campo | Informação |
|---|---|
| Identificação | [ID do teste] |
| Funcionalidade | [Funcionalidade testada] |
| Tipo | [Unitário, integração, E2E, regressão etc.] |
| Ambiente | [Ambiente utilizado] |
| Data | [Data da execução] |
| Resultado esperado | [Comportamento esperado] |
| Resultado obtido | [Comportamento observado] |
| Situação | [Aprovado, reprovado, bloqueado ou não executado] |
| Evidência | [Link do log, imagem ou workflow] |
| Commit/PR | [Referência] |

### Referências

- [Repositório Frontend](https://github.com/ToqueDeMulher/toquedemulher-frontend)
- [Repositório Backend](https://github.com/ToqueDeMulher/toquedemulher-backend)
- [GitHub Actions — Frontend](https://github.com/ToqueDeMulher/toquedemulher-frontend/actions)
- [GitHub Actions — Backend](https://github.com/ToqueDeMulher/toquedemulher-backend/actions)
- [Status Atual da Implementação](../introducao/status_atual.md)