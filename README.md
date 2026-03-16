# Toque de Mulher - README

<p align="center">
  <img src="BannerTDM.gif" alt="Banner Toque de Mulher" width="100%">
</p>

<div align="center">
  <img src="https://img.shields.io/badge/Toque%20de%20Mulher-E--commerce%20de%20Beleza-pink?style=for-the-badge" alt="Toque de Mulher">
  <br>
  <img src="https://img.shields.io/github/last-commit/ToqueDeMulher/toquedemulher-frontend?style=flat-square&color=ff69b4&label=frontend" alt="Frontend last commit">
  <img src="https://img.shields.io/github/last-commit/ToqueDeMulher/toquedemulher-backend?style=flat-square&color=ff69b4&label=backend" alt="Backend last commit">
  <img src="https://img.shields.io/github/issues/ToqueDeMulher/toquedemulher-backend?style=flat-square&color=ff69b4" alt="Backend issues">
  <img src="https://img.shields.io/github/license/ToqueDeMulher/docs?style=flat-square&color=ff69b4" alt="License">
</div>

---

## 🎯 Sobre o Projeto

O **Toque de Mulher** é um ecossistema digital de beleza focado em transformar a experiência de compra de cosméticos. O projeto nasceu para modernizar uma operação de varejo tradicional, automatizando processos manuais e expandindo o alcance comercial da marca para o nível nacional.

O objetivo é posicionar a Toque de Mulher como uma referência confiável em cosméticos de curadoria, oferecendo uma experiência de compra organizada, um catálogo bem apresentado e uma base tecnológica pronta para evoluir com recursos avançados de personalização e fidelização.

## 📊 Status Atual (Março de 2026)

O projeto encontra-se em fase de **MVP (Produto Mínimo Viável) parcial**. Já possuímos um frontend navegável e um backend com funcionalidades comerciais essenciais, mas ainda há trabalho de integração a ser feito para conectar todas as pontas.

- ✅ **Frontend**: Telas de home, catálogo, produto, carrinho, checkout, perfil e dashboard administrativo estão visualmente implementadas.
- ✅ **Backend**: APIs para criação de produtos, usuários e geração de pagamentos (Mercado Pago) estão funcionais.
- ⚠️ **Pontos de Atenção**: Existem desalinhamentos entre os contratos do frontend e backend, especialmente na autenticação e no upload de imagens. O catálogo público ainda utiliza dados locais, e o fluxo de registro de pedidos não está completo.

Para uma análise técnica detalhada do que está implementado, parcial ou pendente, consulte o documento de [Status Atual do Projeto](https://github.com/ToqueDeMulher/docs/blob/main/docs/introducao/status_atual.md).

## 🗺️ Roadmap Estratégico

Nossa visão de futuro é clara e dividida em fases, com o objetivo de consolidar o básico antes de inovar.

1.  **Consolidação do MVP**: Alinhar frontend e backend, finalizar o fluxo de pedidos e estabilizar a plataforma.
2.  **Experiência e Conversão**: Refinar a interface, implementar dark mode e otimizar a performance.
3.  **Diferenciação em Beauty Tech**: Introduzir recursos como construtor de rotinas (`routine builder`) e comparador inteligente de produtos.
4.  **Retenção e Fidelização**: Lançar um programa de fidelidade com benefícios progressivos.
5.  **Escala e Confiança**: Evoluir para uma arquitetura PWA, headless e reforçar a segurança.

O [Roadmap completo](https://github.com/ToqueDeMulher/docs/blob/main/docs/roadmap.md) oferece uma visão detalhada de cada fase.

## ✨ Funcionalidades

-   **Navegação e Compra**: Explore o catálogo por categorias, adicione produtos ao carrinho e finalize a compra.
-   **Gestão de Produtos**: Painel administrativo para cadastro de produtos, controle de estoque e gestão de fornecedores.
-   **Contas de Usuário**: Crie sua conta, faça login e gerencie seu perfil.
-   **Integração de Pagamento**: Checkout seguro com integração com o Mercado Pago.
-   **Design Responsivo**: Experiência otimizada para desktop, tablets e smartphones.

## 🛠️ Stack Tecnológica

<div align="center">
  <img src="https://img.shields.io/badge/React-20232A?style=for-the-badge&logo=react&logoColor=61DAFB" alt="React">
  <img src="https://img.shields.io/badge/TypeScript-007ACC?style=for-the-badge&logo=typescript&logoColor=white" alt="TypeScript">
  <img src="https://img.shields.io/badge/FastAPI-009688?style=for-the-badge&logo=fastapi&logoColor=white" alt="FastAPI">
  <img src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white" alt="Python">
  <img src="https://img.shields.io/badge/Tailwind_CSS-38B2AC?style=for-the-badge&logo=tailwind-css&logoColor=white" alt="Tailwind CSS">
  <img src="https://img.shields.io/badge/GraphQL-E10098?style=for-the-badge&logo=graphql&logoColor=white" alt="GraphQL">
  <img src="https://img.shields.io/badge/Supabase-3FCF8E?style=for-the-badge&logo=supabase&logoColor=white" alt="Supabase">
</div>

> **Observação**: A documentação inicial mencionava `Node.js`, mas a implementação atual do backend utiliza `FastAPI (Python)`.

## 🚀 Começando

Para executar o projeto em seu ambiente local, siga os passos abaixo. Você precisará clonar os repositórios do frontend e do backend.

### Pré-requisitos

-   Node.js (v18 ou superior)
-   Python (v3.10 ou superior)
-   Git

### Instalação

1.  **Clone os repositórios:**

    ```bash
    # Frontend
    git clone https://github.com/ToqueDeMulher/toquedemulher-frontend.git

    # Backend
    git clone https://github.com/ToqueDeMulher/toquedemulher-backend.git
    ```

2.  **Instale as dependências do Frontend:**

    ```bash
    cd toquedemulher-frontend
    npm install
    ```

3.  **Instale as dependências do Backend:**

    ```bash
    cd ../toquedemulher-backend
    pip install -r requirements.txt
    ```

### Execução

1.  **Inicie o servidor de desenvolvimento do Backend:**

    ```bash
    cd toquedemulher-backend
    uvicorn app.main:app --reload
    ```

    O servidor estará disponível em `http://127.0.0.1:8000`.

2.  **Inicie o servidor de desenvolvimento do Frontend:**

    ```bash
    cd ../toquedemulher-frontend
    npm run dev
    ```

    A aplicação estará disponível em `http://localhost:5173`.

## 🤔 Troubleshooting

-   **Erro de CORS**: Certifique-se de que a URL do frontend (`http://localhost:5173`) está corretamente configurada nas permissões de CORS do backend.
-   **Falhas de API (404 Not Found)**: Como mencionado no status do projeto, algumas rotas chamadas pelo frontend podem não corresponder exatamente às rotas expostas pelo backend. Verifique o `app/main.py` no backend para ver as rotas corretas e ajuste as chamadas no frontend se necessário.
-   **Dados não aparecem no catálogo**: A versão atual do frontend pode estar usando dados mocados. Para conectar à API, será necessário alterar os serviços de dados do frontend para chamar o backend.

## 🤝 Como Contribuir

As contribuições são o que tornam a comunidade de código aberto um lugar incrível para aprender, inspirar e criar. Qualquer contribuição que você fizer será **muito apreciada**.

1.  Faça um *Fork* do Projeto
2.  Crie uma *Branch* para sua Feature (`git checkout -b feature/AmazingFeature`)
3.  Faça o *Commit* de suas alterações (`git commit -m 'Add some AmazingFeature'`)
4.  Faça o *Push* para a Branch (`git push origin feature/AmazingFeature`)
5.  Abra um *Pull Request*

Para mais detalhes sobre padrões de código e processos, consulte nosso [Guia de Contribuição](https://github.com/ToqueDeMulher/docs/blob/main/docs/contributing.md).

## 📄 Licença

Distribuído sob a licença MIT. Veja `LICENSE` para mais informações.

## 👥 Time

<table align="center">
  <tr>
    <td align="center">
      <a href="https://github.com/Marichoii">
        <img src="https://avatars.githubusercontent.com/u/126472433?v=4" width="100px;" alt="Maria Eduarda"/><br />
        <sub><b>Maria Eduarda</b></sub>
      </a><br />
      Product Owner / Design
    </td>
    <td align="center">
      <a href="https://github.com/MatheusMusashiTanaka">
        <img src="https://avatars.githubusercontent.com/u/126472450?v=4" width="100px;" alt="Matheus Musashi"/><br />
        <sub><b>Matheus Musashi</b></sub>
      </a><br />
      Tech Lead / Backend
    </td>
    <td align="center">
      <a href="https://github.com/joaodelabio">
        <img src="https://avatars.githubusercontent.com/u/126472751?v=4" width="100px;" alt="Joao Gabriel"/><br />
        <sub><b>João Gabriel</b></sub>
      </a><br />
      Fullstack Developer
    </td>
  </tr>
  <tr>
    <td align="center">
      <a href="https://github.com/Jpzin1">
        <img src="https://avatars.githubusercontent.com/u/161030050?v=4" width="100px;" alt="Joao Pedro"/><br />
        <sub><b>João Pedro</b></sub>
      </a><br />
      PWA / Frontend
    </td>
    <td align="center">
      <a href="https://github.com/GuHenriquee">
        <img src="https://avatars.githubusercontent.com/u/197537829?v=4" width="100px;" alt="Gustavo Henrique"/><br />
        <sub><b>Gustavo Henrique</b></sub>
      </a><br />
      Backend / Data
    </td>
    <td align="center">
      <a href="https://github.com/ccarolmdlima">
        <img src="https://avatars.githubusercontent.com/u/126472626?v=4" width="100px;" alt="Carolina"/><br />
        <sub><b>Carolina</b></sub>
      </a><br />
      Frontend / UI
    </td>
  </tr>
  <tr>
    <td align="center" colspan="3">
      <a href="https://github.com/Zouares">
        <img src="https://avatars.githubusercontent.com/u/115197009?v=4" width="100px;" alt="Gabriel Soares"/><br />
        <sub><b>Gabriel Soares</b></sub>
      </a><br />
      UI/UX Designer
    </td>
  </tr>
</table>

---

<div align="center">
  <sub>Desenvolvido com ❤️ pela equipe Toque de Mulher.</sub>
</div>
