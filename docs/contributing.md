# Guia de Contribuição para o Projeto ToqueDeMulher

Bem-vindo(a) ao guia de contribuição do projeto ToqueDeMulher! Agradecemos o seu interesse em colaborar. Este documento visa fornecer as diretrizes necessárias para que suas contribuições sejam eficazes e se integrem harmoniosamente ao nosso fluxo de trabalho.

## Como Contribuir

Existem diversas formas de contribuir para o projeto, seja reportando bugs, sugerindo novas funcionalidades, melhorando a documentação ou escrevendo código.

### 1. Reportando Bugs

Se você encontrar um bug, por favor, siga os passos abaixo:

1.  **Verifique as Issues Existentes:** Antes de abrir uma nova issue, verifique se o bug já foi reportado. Utilize a funcionalidade de busca do GitHub para isso.
2.  **Abra uma Nova Issue:** Se o bug não foi reportado, abra uma nova issue utilizando o template `Bug Report` disponível. Forneça o máximo de detalhes possível, incluindo:
    *   **Título Descritivo:** Um título claro e conciso que resuma o problema.
    *   **Passos para Reproduzir:** Instruções claras e numeradas sobre como reproduzir o bug.
    *   **Comportamento Esperado:** O que você esperava que acontecesse.
    *   **Comportamento Atual:** O que realmente aconteceu.
    *   **Capturas de Tela/Vídeos:** Se possível, inclua capturas de tela ou vídeos que demonstrem o bug.
    *   **Ambiente:** Informações sobre o seu ambiente (navegador, sistema operacional, etc.).

### 2. Sugerindo Novas Funcionalidades

Novas ideias são sempre bem-vindas! Para sugerir uma funcionalidade:

1.  **Verifique as Issues Existentes:** Verifique se a funcionalidade já foi sugerida.
2.  **Abra uma Nova Issue:** Utilize o template `Feature Request` e descreva a funcionalidade em detalhes, incluindo:
    *   **Problema:** Qual problema essa funcionalidade resolveria?
    *   **Solução Proposta:** Como você imagina que a funcionalidade funcionaria?
    *   **Benefícios:** Quais seriam os benefícios para o projeto ou para os usuários?

### 3. Contribuindo com Código

Para contribuir com código, siga o fluxo de trabalho de Pull Request:

1.  **Faça um Fork do Repositório:** Crie um fork do repositório principal para a sua conta do GitHub.
2.  **Clone o Repositório:** Clone o seu fork para a sua máquina local.
    ```bash
    git clone https://github.com/SEU_USUARIO/ToqueDeMulher.git
    ```
3.  **Crie uma Nova Branch:** Crie uma branch com um nome descritivo para a sua funcionalidade ou correção de bug.
    ```bash
    git checkout -b feature/nome-da-funcionalidade
    ```
    ou
    ```bash
    git checkout -b bugfix/correcao-do-bug
    ```
4.  **Faça Suas Alterações:** Implemente suas alterações, seguindo as convenções de código do projeto.
5.  **Teste Suas Alterações:** Certifique-se de que suas alterações não introduzem novos bugs e que as funcionalidades existentes continuam funcionando corretamente.
6.  **Commit Suas Alterações:** Escreva mensagens de commit claras e concisas.
    ```bash
    git commit -m "feat: Adiciona nova funcionalidade X"
    ```
    ou
    ```bash
    git commit -m "fix: Corrige bug Y"
    ```
7.  **Envie Suas Alterações (Push):** Envie suas alterações para o seu fork no GitHub.
    ```bash
    git push origin feature/nome-da-funcionalidade
    ```
8.  **Abra um Pull Request (PR):** Abra um Pull Request do seu fork para a branch `main` do repositório original. Utilize o template `Pull Request` e forneça uma descrição detalhada das suas alterações.

### 4. Melhorando a Documentação

A documentação é crucial para o sucesso do projeto. Se você encontrar erros, inconsistências ou oportunidades de melhoria, sinta-se à vontade para:

*   Abrir uma issue descrevendo a melhoria.
*   Abrir um Pull Request com as suas alterações diretamente na documentação.

## Convenções de Código e Boas Práticas

*   **Estilo de Código:** Siga o estilo de código existente no projeto. Se houver um linter configurado, certifique-se de que suas alterações passem por ele.
*   **Testes:** Sempre que possível, adicione testes para suas novas funcionalidades ou correções de bugs.
*   **Mensagens de Commit:** Utilize mensagens de commit claras e descritivas, seguindo a convenção de Conventional Commits (ex: `feat:`, `fix:`, ``docs:`, `chore:`).
*   **Revisão de Código:** Esteja aberto(a) a feedback e sugestões durante o processo de revisão do seu Pull Request.

Agradecemos a sua colaboração para tornar o projeto ToqueDeMulher ainda melhor!
