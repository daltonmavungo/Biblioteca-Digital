# DVLTCH — Repositório Digital do Laboratório de Desenvolvimento Humano por Tecnologia

> Repositório institucional digital baseado no DSpace 8.0, desenvolvido no âmbito do estágio curricular do curso de Engenharia Informática e Comunicações da Universidade Óscar Ribas (UÓR).

---

## Índice

- [Descrição](#descrição)
- [Tecnologias](#tecnologias)
- [Arquitectura](#arquitectura)
- [Pré-requisitos](#pré-requisitos)
- [Instalação](#instalação)
- [Como Correr](#como-correr)
- [Estrutura do Projecto](#estrutura-do-projecto)
- [Utilizadores e Permissões](#utilizadores-e-permissões)
- [Comunidades e Colecções](#comunidades-e-colecções)
- [Personalização](#personalização)
- [Autor](#autor)

---

## Descrição

O **DVLTCH** é um repositório digital institucional desenvolvido para o **Laboratório de Desenvolvimento Humano por Tecnologia** da Universidade Óscar Ribas (UÓR), em Luanda, Angola.

O sistema permite:
- Armazenar e organizar documentos académicos e científicos
- Submeter relatórios de estágio, artigos, imagens, áudios e vídeos
- Gerir utilizadores com diferentes níveis de permissão
- Pesquisar e navegar pelo conteúdo do repositório

---

## Tecnologias

| Camada | Tecnologia | Versão |
|---|---|---|
| Frontend | Angular (DSpace Angular) | 8.0 |
| Backend | Java + Spring Boot | 3.2.6 |
| Base de dados | PostgreSQL | 14+ |
| Motor de pesquisa | Apache Solr | 9.10.1 |
| Gestor de dependências (backend) | Apache Maven | 3.9.16 |
| Gestor de dependências (frontend) | Yarn / Node.js | 18+ |

---

## Arquitectura

\`\`\`
┌─────────────────────────────────────────────────────┐
│                  Utilizador (Browser)                │
└───────────────────────┬─────────────────────────────┘
                        │
                        ▼
┌─────────────────────────────────────────────────────┐
│         Frontend Angular — localhost:4000            │
│              (DSpace Angular / DVLTCH)               │
└───────────────────────┬─────────────────────────────┘
                        │ API REST
                        ▼
┌─────────────────────────────────────────────────────┐
│       Backend Spring Boot — localhost:8080/server    │
│              (DSpace Server)                         │
└──────────────┬────────────────────┬─────────────────┘
               │                    │
               ▼                    ▼
┌──────────────────────┐  ┌─────────────────────────┐
│  PostgreSQL :5432    │  │  Apache Solr :8983       │
│  (Base de dados)     │  │  (Motor de pesquisa)     │
└──────────────────────┘  └─────────────────────────┘
\`\`\`

---

## Pré-requisitos

- **Java 17** ou superior
- **PostgreSQL 14+**
- **Apache Maven 3.8+**
- **Node.js 18+**
- **Yarn**
- **Git**

---

## Como Correr

**1. Iniciar o Solr:**
\`\`\`bash
cd C:\dspace\solr-9.10.1
bin\solr.cmd start
\`\`\`

**2. Iniciar o Backend:**
\`\`\`bash
java -DDSPACE_HOME=C:\dspace -jar C:\dspace\webapps\server-boot.jar
\`\`\`

**3. Iniciar o Frontend:**
\`\`\`bash
cd C:\Users\User\dspace-angular
yarn start
\`\`\`

**4. Aceder no browser:**
\`\`\`
http://localhost:4000
\`\`\`

---

## Estrutura do Projecto

\`\`\`
Biblioteca-Digital/
├── frontend/                    ← DSpace Angular (interface web)
│   ├── src/themes/dspace/       ← Tema personalizado DVLTCH
│   └── config/config.yml        ← Configuração do frontend
└── backend/                     ← DSpace Server
    └── config/                  ← Configurações do backend
\`\`\`

---

## Utilizadores e Permissões

| Utilizador | Email | Perfil | Permissões |
|---|---|---|---|
|  Dalton Mavungo | josedalton258@gmail.com | Administrador | Acesso total |
| Adelino Miala | adelinomiala@gmail.com | Submissor | Submeter itens |
| Ester Alexandre | esteralexandre@gmail.com | Editor | Editar e gerir itens |
| Telma Simão | telmasimao@gmail.com | Leitor | Ler e ver documentos |

---

## Comunidades e Colecções

\`\`\`
Tecnologia e Inovação (Comunidade)
└── Relatórios de Estágio (Colecção)
    ├── PDFs (livros, relatórios, artigos)
    ├── Imagens (JPEG)
    ├── Áudios (MPEG, AAC)
    └── Vídeos (MP4)
\`\`\`

---

## Personalização

O tema personalizado DVLTCH inclui:
- **Logótipo** da UÓR no cabeçalho
- **Fundo cinza claro** nas páginas internas
- **Tipografia Roboto** (Google Fonts)
- **Acentos em laranja** nos títulos e links
- Interface traduzida para **Português (PT)**

---

## Autor

**Dalton Mavungo**
