# 🧩 TEAcolhe

O **TEAcolhe** é um ecossistema tecnológico desenvolvido para auxiliar profissionais de enfermagem (auxiliares, técnicos e enfermeiros) no atendimento humanizado a pacientes com **Transtorno do Espectro Autista (TEA)** — considerando os níveis de suporte 1, 2 e 3 — no ambiente hospitalar.

A solução integra um aplicativo móvel voltado para o profissional da saúde e um robusto serviço de backend alimentado por um agente de Inteligência Artificial.

---

## 🏗️ Estrutura da Organização

O projeto principal está dividido em dois repositórios fundamentais:

### 📱 1. [TEAcolhe Mobile](https://github.com/teacolhe-enfermagem/teacolhe-mobile)
Interface do usuário onde os profissionais de enfermagem interagem com o sistema.
- **Tecnologias:** Node.js 20+, npm 10+, Expo / React Native.
- **Arquitetura:** O projeto é estruturado na pasta `src/`, dividido em `app/` (para o roteamento) e `features/` (para as funcionalidades como telas, componentes próprios e schemas).
- **Execução:** Ambiente de desenvolvimento executado localmente através do comando `npx expo start` com teste via Expo Go.

### ⚙️ 2. [TEAcolhe Backend & Agente IA](https://github.com/teacolhe-enfermagem/teacolhe-backend)
Serviço central que provê suporte às decisões e gerencia os dados da plataforma.
- **Tecnologias:** Arquitetura RAG (Retrieval-Augmented Generation), modelos Llama via Groq, armazenamento vetorial FAISS e banco de dados PostgreSQL.
- **Serviços Ativos:** - Backend API (Porta `8001`)
  - Agent API (Porta `8002`)
  - PostgreSQL (Porta `5432`)
- **Execução:** Infraestrutura totalmente conteinerizada utilizando Docker e Docker Compose (`docker compose up --build`).

---

## 🚀 Como iniciar o ecossistema localmente

Para rodar a plataforma completa, siga o fluxo de iniciar a infraestrutura de dados/IA antes de subir o aplicativo móvel:

1. **Configuração do Backend e Agente:**
   - Obtenha os arquivos do dataset via [Google Drive](https://drive.google.com/drive/folders/1-K3W47mu_WRCx63xddHUGzT2rrfpUJ7C?usp=sharing) e coloque-os em `agent/app/datasets`.
   - Crie os arquivos `.env` nas raízes dos diretórios `/agent` e `/backend` configurando a API Key do Groq, URL do banco, e a chave interna (`INTERNAL_API_KEY`).
   - Suba os containers com `docker compose up --build`.

2. **Configuração do Mobile:**
   - Clone o repositório mobile e certifique-se de ter o Node.js e npm instalados.
   - Instale as dependências com `npm install` e inicie o ambiente com `npx expo start`.

---

*Para instruções mais detalhadas de contribuição e configuração de cada escopo, consulte o arquivo `README.md` presente na raiz de cada repositório específico.*
