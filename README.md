# Documentação do Projeto Toque de Mulher

Este repositório concentra a documentação executiva e funcional do projeto Toque de Mulher. O conteúdo foi consolidado a partir dos arquivos `Plano de Projeto - 2025`, `Plano de Projeto Cliente` e `Plano de Futuro e Otimização - 2026`, com complemento do estado real do código versionado até **24 de maio de 2026**.

## Página para GitHub Pages

A documentação pode ser acessada também pela versão publicada no **GitHub Pages**, utilizando como página inicial:

- [index.html](index.html)

Esse arquivo é a entrada recomendada para publicação no GitHub Pages.

## Visão Geral

A documentação principal fica em `docs/` e está organizada por tema:

| Local | Conteúdo |
|--------|----------|
| `introducao/` | Contexto, objetivos, escopo, protótipo e status técnico atual |
| `introducao/prototipo.md` | Registro do mockup, prints de evidência e vídeo não listado do site. |
| `roadmap.md` | Evolução planejada do MVP até as otimizações futuras. |
| `sprints.md` | Histórico das sprints, entregas e evidências |
| `equipe/` | Stakeholders, papéis e responsabilidades |
| `financeiro/` | Visão de orçamento do MVP e custos previstos |
| `riscos_e_dependencias/` | Restrições, premissas, riscos e dependências |
| `aprovacao/` | Registro consolidado de aprovação |
| `glossario.md` | Termos técnicos e de negócio |
| `contributing.md` | Guia de contribuição da documentação |

## Como Consultar

Os documentos principais podem ser acessados pelos links abaixo:

### Introdução

- [Contexto e Justificativa](docs/introducao/contexto.md)
- [Objetivos Estratégicos e KPIs](docs/introducao/objetivos.md)
- [Escopo do MVP](docs/introducao/escopo.md)
- [Status Atual da Implementação](docs/introducao/status_atual.md)
- [Protótipo e Evidências Visuais](docs/introducao/prototipo.md)

### Planejamento

- [Roadmap Estratégico](docs/roadmap.md)
- [Acompanhamento das Sprints](docs/sprints.md)

### Equipe

- [Stakeholders](docs/equipe/stakeholders.md)
- [Funções da Equipe](docs/equipe/funcao_equipe.md)

### Gestão

- [Orçamento do Projeto](docs/financeiro/orcamento.md)
- [Premissas](docs/riscos_e_dependencias/premissas.md)
- [Restrições](docs/riscos_e_dependencias/restricoes.md)
- [Riscos e Dependências](docs/riscos_e_dependencias/riscos_e_dependencias.md)

### Documentos

- [Assinaturas de Aprovação](docs/aprovacao/assinaturas_aprovacao.md)
- [Glossário](docs/glossario.md)
- [Guia de Contribuição](docs/contributing.md)

## Tecnologias Utilizadas

O projeto é desenvolvido utilizando tecnologias modernas para frontend, backend e banco de dados.

### Frontend

- React
- TypeScript
- Vite
- Tailwind CSS
- Axios

### Backend

- Python
- FastAPI
- Pydantic
- JWT
- Bcrypt

### Banco de Dados

- PostgreSQL
- SQLAlchemy
- Alembic

### Integrações Externas

- Mercado Pago
- SMTP

### Ferramentas de Desenvolvimento

- Git & GitHub
- GitHub Pages

> A documentação descreve a evolução do projeto, independentemente da tecnologia utilizada em cada módulo.

## Estrutura do Repositório

```text
.
|-- LICENSE
|-- README.md
`-- docs
    |-- _sidebar.md
    |-- assets
    |-- aprovacao
    |-- contributing.md
    |-- equipe
    |-- financeiro
    |-- glossario.md
    |-- introducao
    |-- riscos_e_dependencias
    |-- roadmap.md
    `-- sprints.md
```

## Nota de Consolidação

Esta documentação substitui materiais redundantes mantidos fora da estrutura principal. O objetivo é manter uma única fonte de verdade para estratégia, escopo e acompanhamento do projeto.

## Contribuição

As diretrizes de contribuição estão em [Guia de Contribuição](docs/contributing.md).

---

*Última atualização: 31 de julho de 2026*
