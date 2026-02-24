# Push-UP

[![Version](https://img.shields.io/badge/version-1.0.0-blue?style=for-the-badge)](https://github.com/usuario/Push-UP/releases/tag/v1.0.0)
[![Issues](https://img.shields.io/github/issues/usuario/Push-UP?style=for-the-badge&color=orange)](https://github.com/usuario/Push-UP/issues)
[![License](https://img.shields.io/badge/license-MIT-green?style=for-the-badge)](LICENSE)
[![Language](https://img.shields.io/github/languages/top/usuario/Push-UP?style=for-the-badge&color=yellow)](https://github.com/usuario/Push-UP)
[![Status](https://img.shields.io/badge/status-em%20desenvolvimento-yellowgreen?style=for-the-badge)](#)

---

## 📖 Descrição do Projeto

O **Push-UP** é uma aplicação inovadora voltada para o monitoramento, registro e aprimoramento do desempenho em exercícios físicos, com foco principal em flexões (push-ups). Desenvolvido para atender tanto praticantes casuais quanto atletas e treinadores, o sistema propõe uma solução digital acessível que facilita a prática regular de atividades físicas através de funcionalidades inteligentes e uma interface intuitiva.

A aplicação resolve o problema comum da falta de acompanhamento personalizado e registro eficiente dos exercícios, incentivando o usuário com feedbacks progressivos que potencializam o desenvolvimento físico e a saúde. O Push-UP apresenta um diferencial técnico ao oferecer um sistema modular e escalável, com possibilidade de futura ampliação para outras modalidades de treino e integração com dispositivos de monitoramento.

---

## ⚙️ Funcionalidades

- **Cadastro e autenticação de usuários:** Controle seguro de acesso para múltiplos perfis.
- **Registro de sessões de flexões:** Inserção e edição detalhada de séries, repetições, tempo, e data.
- **Acompanhamento histórico:** Visualização gráfica do progresso pessoal ao longo do tempo.
- **Definição de metas personalizadas:** Configuração de objetivos semanais e mensais.
- **Feedback automático:** Alertas e recomendações baseadas no desempenho registrado.
- **Interface responsiva:** Otimizada para dispositivos móveis e desktops.
- **Exportação de dados:** Baixa de relatórios em formatos padrões para análise externa.
  
---

## 🛠 Tecnologias Utilizadas

| Tecnologia             | Tipo                          | Detalhes                                                    |
|-----------------------|------------------------------|-------------------------------------------------------------|
| React                 | Framework Front-end           | Construção da interface do usuário responsiva               |
| Node.js               | Plataforma Back-end           | Servidor e API RESTful                                       |
| Express.js            | Framework Node.js             | Roteamento e middleware para API                            |
| MongoDB               | Banco de Dados NoSQL          | Armazenamento dos dados do usuário e exercícios             |
| JWT                   | Autenticação                  | Gerenciamento seguro de tokens para autenticação             |
| Chart.js              | Biblioteca Front-end          | Gráficos para visualização do progresso                      |
| Docker                | Contêinerização               | Facilita o deploy e ambiente isolado                          |

---

## 📁 Estrutura de Diretórios

```
/Push-UP
├── README.md                 # Documentação detalhada do projeto
├── /client                   # Código fonte da interface React
│   ├── /components           # Componentes reutilizáveis da UI
│   ├── /pages                # Páginas da aplicação
│   ├── /services             # Serviços para consumo da API
│   └── /assets               # Imagens e estilos
├── /server                   # Aplicação backend Node.js/Express
│   ├── /controllers          # Lógica de negócios e controle de rotas
│   ├── /models               # Definições de schema do MongoDB
│   ├── /routes               # Definição das rotas da API REST
│   ├── /middlewares          # Middleware para autenticação, logs, etc.
│   ├── /config               # Configurações gerais e variáveis de ambiente
│   └── /utils                # Utilitários e helpers
├── Dockerfile                # Configuração para criação da imagem Docker
└── docker-compose.yml        # Orquestração de contêineres (app+db)
```

---

## 🖥 Instalação e Execução

### Pré-requisitos

- Node.js v16+
- npm ou yarn
- MongoDB (local ou remoto)
- Docker e Docker Compose (opcional para deploy simplificado)

### Passos

1. Clone o repositório:
   ```bash
   git clone https://github.com/usuario/Push-UP.git
   cd Push-UP
   ```

2. Instale as dependências backend:
   ```bash
   cd server
   npm install
   ```

3. Configure as variáveis de ambiente:
   - Renomeie `.env.example` para `.env` e ajuste as variáveis como `MONGO_URI`, `JWT_SECRET` e `PORT`.

4. Instale as dependências frontend:
   ```bash
   cd ../client
   npm install
   ```

5. Inicialize o servidor backend:
   ```bash
   npm run dev
   ```

6. Inicialize o cliente React:
   ```bash
   npm start
   ```

A aplicação estará acessível via `http://localhost:3000`.

---

## 🌐 Endpoints da API

| Método  | Endpoint              | Descrição                                      |
|---------|-----------------------|-----------------------------------------------|
| POST    | /api/auth/register    | Registrar novo usuário                         |
| POST    | /api/auth/login       | Autenticar usuário e obter token JWT          |
| GET     | /api/users/profile    | Obter dados do perfil autenticado              |
| POST    | /api/exercises        | Criar novo registro de exercício (flexões)    |
| GET     | /api/exercises        | Listar registros do usuário                     |
| PUT     | /api/exercises/:id    | Atualizar registro específico                   |
| DELETE  | /api/exercises/:id    | Remover registro                                |
| GET     | /api/progress         | Obter dados agregados para gráficos de progresso |

---

## 🔍 Testes

Atualmente o projeto inclui testes automatizados no backend com **Jest** e **Supertest**:

- Para executar os testes:
  ```bash
  cd server
  npm test
  ```

- Cobertura de testes inclui: validação de rotas, autenticação, CRUD de exercícios e middleware.

- Estratégia: testes unitários para controllers e integração para rotas REST.

---

## ☁️ Deploy

### Deploy com Docker

1. Construir imagem Docker:
   ```bash
   docker-compose build
   ```

2. Subir serviços:
   ```bash
   docker-compose up -d
   ```

3. Acesse a aplicação via `http://localhost:3000`.

### Deploy em Nuvem

A aplicação pode ser facilmente publicada em plataformas como Heroku, AWS Elastic Beanstalk, ou DigitalOcean, utilizando a imagem Docker ou implantação direta do Node.js com banco MongoDB conectado remotamente.

---

## 🔐 Segurança

- **Autenticação JWT:** Todas as rotas que manipulam dados do usuário são protegidas por token JWT.
- **Validação de dados:** Inputs validados no backend usando middleware para prevenir dados inválidos e ataques de injeção.
- **CORS configurado:** Controla acessos externos à API garantindo comunicação segura.
- **Protocolos HTTPS:** Recomendado para produção, garantindo a criptografia do tráfego.
  
---

## 🚀 Melhorias Futuras

- Implementar integração com dispositivos wearables para monitoramento em tempo real.
- Adicionar suporte para outras modalidades de exercícios físicos (abdominais, agachamentos, etc).
- Incluir recursos avançados de análise e inteligência artificial para planos de treino personalizados.
- Suporte multi-idiomas para alcance global.
- Implementar notificações push para lembretes e motivação diária.
- Criar versão mobile nativa para iOS e Android.

---

## 🤝 Contribuição

Contribuições são muito bem-vindas! Para colaborar, siga os passos abaixo:

1. Fork o projeto
2. Crie uma branch para sua feature (`git checkout -b feature/nova-funcionalidade`)
3. Commit suas alterações (`git commit -m 'Adiciona nova funcionalidade'`)
4. Push para sua branch (`git push origin feature/nova-funcionalidade`)
5. Abra um Pull Request explicando as alterações realizadas

Por favor, siga o padrão de código existente e escreva testes para novas funcionalidades quando aplicável.

---

## ⚖️ Licença

Este projeto está licenciado sob a licença **MIT** - veja o arquivo [LICENSE](LICENSE) para detalhes.

---

_Desenvolvido com 💪 para incentivar saúde e bem-estar através da tecnologia._