# Toque de Mulher - Documentação do Projeto

Este repositório reúne a documentação do projeto **Toque de Mulher**, uma plataforma de e-commerce para cosméticos e cuidados pessoais.

A documentação mostra o que foi planejado, o que já foi desenvolvido, o que ainda está em validação e quais são os próximos passos para transformar o MVP em uma operação comercial completa.

## Status do projeto

O projeto já possui uma base sólida de MVP:

- loja navegável;
- catálogo, busca, carrinho e checkout visual;
- login, cadastro, perfil e endereço;
- área administrativa e cadastro de produto;
- gamificação;
- backend com base para usuários, produtos, pagamentos, fornecedores e estoque;
- documentação consolidada por escopo, requisitos, arquitetura, testes, riscos e sprints.

O MVP, porém, ainda está **em validação**. A loja está boa para demonstração, mas os fluxos de compra, pedido, pagamento, estoque, endereço e produto administrativo ainda precisam ser comprovados de ponta a ponta antes de uso comercial real.

## Leitura rápida das sprints

| Sprint    | Principal entrega                                                                      |
| --------- | -------------------------------------------------------------------------------------- |
| Sprint#01 | Organização inicial do projeto, documentação base e estrutura técnica             |
| Sprint#02 | Avanço do MVP com autenticação, checkout, pagamento e dashboard                     |
| Sprint#03 | Busca, endereço, tema, acessibilidade, segurança e início de estoque                |
| Sprint#04 | Fornecedores, estoque, associação fornecedor-produto e controle admin                |
| Sprint#05 | Ajustes de integração, identidade visual, autenticação e layout                    |
| Sprint#06 | Planejamento de fechamento, validação ponta a ponta e evidências                    |
| Sprint#07 | Revisão final de julho, frontend mais maduro, docs atualizados e pendências mapeadas |

## Participação geral

A leitura dos commits mostra a seguinte distribuição histórica:

- **Maria Eduarda:** maior participação em frontend e documentação;
- **Carolina:** liderança na consolidação técnica mais recente da documentação;
- **Gabriel Soares:** contribuições em navegação e endereço;
- **João Pedro:** contribuições em tema e acessibilidade;
- **Matheus Musashi:** correções de segurança e dependências no backend.

Também há contribuições anteriores relevantes de **Gustavo Henrique** no backend e de **João Gabriel** na busca. Ambos não fazem mais parte do grupo atual.

Essas informações vêm dos metadados do Git e indicam participação registrada em commits, não todo o trabalho feito fora do repositório.

## Principais documentos

- [Status atual da implementação](docs/introducao/status_atual.md)
- [Acompanhamento das sprints](docs/sprints.md)
- [Escopo do MVP](docs/introducao/escopo.md)
- [Objetivos e KPIs](docs/introducao/objetivos.md)
- [Requisitos do sistema](docs/desenvolvimento/requisitos.md)
- [Arquitetura do sistema](docs/desenvolvimento/arquitetura.md)
- [Fluxos principais](docs/desenvolvimento/fluxos.md)
- [Testes e validações](docs/desenvolvimento/testes.md)
- [Desafios encontrados](docs/desenvolvimento/desafios.md)
- [Roadmap estratégico](docs/roadmap.md)

## Tecnologias utilizadas

| Frente         | Tecnologias principais          |
| -------------- | ------------------------------- |
| Frontend       | React, TypeScript, Vite, Axios  |
| Backend        | Python, FastAPI, Pydantic, JWT  |
| Banco de dados | PostgreSQL, SQLAlchemy, Alembic |
| Documentação | Markdown, GitHub Pages          |

## Como consultar

Para entender o projeto rapidamente, comece por:

1. [Status atual da implementação](docs/introducao/status_atual.md)
2. [Acompanhamento das sprints](docs/sprints.md)
3. [Escopo do MVP](docs/introducao/escopo.md)
4. [Roadmap estratégico](docs/roadmap.md)

## Publicação

A documentação pode ser publicada pelo GitHub Pages usando o arquivo [index.html](index.html) como entrada.

---

**Última atualização:** 31 de julho de 2026.
