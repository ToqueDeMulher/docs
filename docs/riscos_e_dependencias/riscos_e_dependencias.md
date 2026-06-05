# Riscos e Dependências do Projeto

## Riscos prioritários

| Risco | Impacto esperado | Mitigação sugerida |
| :--- | :--- | :--- |
| Deriva de escopo | Atraso do MVP e perda de foco | Formalizar prioridades e validar mudanças antes de executar |
| Indisponibilidade de recursos | Atrasos por agenda da equipe | Trabalhar com backlog enxuto e entrega incremental |
| Dívida técnica | Baixa manutenibilidade e retrabalho | Revisar contratos, padrões e integrações antes de ampliar o sistema |
| Rotas backend duplicadas ou divergentes | Integração instável e testes inconclusivos | Consolidar a API principal e documentar endpoints oficiais |
| Integração com terceiros | Problemas em pagamento, webhook ou hospedagem | Testar cedo em sandbox e documentar dependências |
| Baixa adoção do usuário | Conversão aquém do esperado | Priorizar UX, SEO, catálogo claro e jornada simples de compra |

## Dependências críticas

O sucesso do MVP depende diretamente de:

- validação contínua da cliente;
- catálogo, regras de negócio e prioridades comerciais fornecidos com clareza;
- integração estável com gateway de pagamento;
- alinhamento entre frontend e backend para autenticação, catálogo, endereço, checkout, estoque e administração;
- manutenção de documentação centralizada e atualizada.

## Dependências já visíveis no código

No snapshot atual, a documentação também precisa considerar algumas dependências técnicas específicas:

- o frontend depende de contratos de API ainda não totalmente compatíveis com todas as estruturas existentes no backend;
- o backend depende de variáveis de ambiente e serviços externos como Supabase e Mercado Pago;
- parte da experiência atual do frontend ainda depende de dados locais estáticos;
- as evidências visuais agora dependem também da manutenção do asset de alta fidelidade em `docs/assets/figma_altafidelidade.png`.
