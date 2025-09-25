# Banco API - Testes de Performance com K6

Repositório destinado a testes de performance da aplicação **Banco API**, utilizando a ferramenta [K6](https://k6.io/).

🔗 Repositório: [eddysantoss/banco-api-performance](https://github.com/eddysantoss/banco-api-performance)

---

## 📖 Introdução

Este projeto tem como objetivo validar o desempenho, estabilidade e capacidade de resposta da **Banco API**.  
Os testes foram implementados em **JavaScript** usando o **K6**, permitindo simular diferentes cenários de carga e stress.

---

## 🛠 Tecnologias Utilizadas

- **[K6](https://k6.io/)** → Ferramenta open-source para testes de performance.  
- **JavaScript (ES6+)** → Linguagem utilizada para criação dos scripts de teste.  
- **Node.js (opcional)** → Auxilia em automações e gerenciamento de dependências.  

---

## 📂 Estrutura do Repositório

```bash
banco-api-performance/
│
├── fixtures/            # Dados de entrada para os testes (ex: usuários, payloads)
├── helpers/              # Funções utilitárias reutilizáveis para interação com a API
├── tests/              # Casos de teste organizados por módulo de API
││
├── utils/              # Funções utilitárias reutilizáveis
├── config/              # Arquivo de configuração de variáveis de ambiente
└── README.md             # Documentação do projeto
```

---

## 🎯 Objetivo de cada grupo de arquivos

- **fixtures/** → Dados de entrada para os testes (ex: usuários, payloads)
  - **helpers/** → Funções utilitárias reutilizáveis para interação com a API  
  - **tests/** → Casos de teste organizados por módulo de API  
  - **utils/** → Funções utilitárias reutilizáveis   
- **config/** → Arquivo de configuração de variáveis de ambiente.  

---

## ⚙️ Instalação

1. **Clone o repositório**
   ```bash
   git clone https://github.com/eddysantoss/banco-api-performance.git
   cd banco-api-performance
   ```
2. **Configure as Variáveis de Ambiente**

   Altere o arquivo `config.local.json` e defina a URL base da API a ser testada:

   ```json
   BASE_URL="http://localhost:3000"
   ```

---

## 🚀 Execução dos Testes

### 1. Execução de um teste
```bash
k6 run tests/login.test.js
```

Certifique-se de passar a variável de ambiente `BASE_URL`, caso não esteja usando um `config.local.json`ou uma abordagem de carregamento automático:

```bash
k6 run tests/lautenticacao.test.js 
-e BASE_URL=http://localhost:3000
```

### 2. Relatório em tempo real com dashboard do K6
Para visualizar os resultados em tempo real no navegador e exportar o relatório em HTML:

```bash
K6_WEB_DASHBOARD=true\
K6_WEB_DASHBOARD_EXPORT=reports/html-report.html \
k6 run tests/autenticacao/login.test.js \
-e BASE_URL= http://localhost:3000
```

Após a execução, o relatório estará disponível em `reports/html-report.html`.
