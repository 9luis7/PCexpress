# PC-Express - Sistema de Gerenciamento de Inventário

Um sistema completo de gerenciamento de inventário desenvolvido com FastAPI (backend) e React (frontend), oferecendo uma interface moderna e intuitiva para controle de estoque, fornecedores, alertas e insights de negócio.

## 🚀 Características

- **Dashboard Interativo**: Visualização em tempo real de métricas importantes
- **Gerenciamento de Produtos**: CRUD completo com categorização e controle de estoque
- **Fornecedores**: Cadastro e gerenciamento de parceiros comerciais
- **Alertas de Estoque**: Notificações automáticas para itens com estoque baixo
- **Pedidos de Compra**: Sistema completo de pedidos de reabastecimento
- **Insights de Negócio**: Análises e recomendações baseadas em dados
- **Reabastecimento Automático**: Sistema inteligente de sugestões de reabastecimento
- **Tema Escuro/Claro**: Interface adaptável com suporte a múltiplos temas
- **Internacionalização**: Suporte completo a português e inglês
- **Autenticação Segura**: Sistema de login com JWT

## 📋 Pré-requisitos

- **Python 3.8+**
- **Node.js 16+**
- **npm** (incluído com Node.js)

## 🛠️ Instalação

### 1. Clone o repositório
```bash
git clone <url-do-repositorio>
cd PCexpress
```

### 2. Configuração do Backend

#### Crie um ambiente virtual Python
```bash
python -m venv .venv
```

#### Ative o ambiente virtual
**Windows:**
```bash
.venv\Scripts\activate
```

**Linux/Mac:**
```bash
source .venv/bin/activate
```

#### Instale as dependências Python
```bash
pip install -r requirement.txt
```

#### Inicialize o banco de dados
```bash
python scripts/setup_db.py
```

### 3. Configuração do Frontend

#### Navegue para a pasta frontend
```bash
cd frontend
```

#### Instale as dependências Node.js
```bash
npm install
```

#### Volte para a pasta raiz
```bash
cd ..
```

## 🚀 Executando o Projeto

### Opção 1: Script de Inicialização Automática
```bash
python start.py
```

### Opção 2: Execução Manual

#### Terminal 1 - Backend
```bash
# Ative o ambiente virtual primeiro
.venv\Scripts\activate  # Windows
# source .venv/bin/activate  # Linux/Mac

# Execute o servidor FastAPI
uvicorn app.main:app --reload --host 0.0.0.0 --port 8000
```

#### Terminal 2 - Frontend
```bash
cd frontend
npm run dev
```

## 🌐 Acessando a Aplicação

Após a inicialização, acesse:

- **Frontend**: http://localhost:5173
- **Backend API**: http://localhost:8000
- **Documentação da API**: http://localhost:8000/docs

## 🔐 Credenciais Padrão

- **Email**: admin@pc-express.com
- **Senha**: admin123

## 🏗️ Arquitetura

### Backend
- **Framework**: FastAPI
- **ORM**: SQLAlchemy
- **Banco de Dados**: SQLite
- **Autenticação**: JWT com passlib[bcrypt]
- **Validação**: Pydantic

### Frontend
- **Framework**: React 18
- **UI Library**: Material-UI (MUI)
- **Build Tool**: Vite
- **Roteamento**: React Router DOM
- **Gráficos**: Recharts
- **Ícones**: Lucide React
- **Internacionalização**: React-i18next

## 📁 Estrutura do Projeto

```
PCexpress/
├── app/                    # Backend FastAPI
│   ├── routers/           # Rotas da API
│   ├── models.py          # Modelos do banco de dados
│   ├── schemas.py         # Schemas Pydantic
│   ├── auth.py            # Autenticação
│   ├── database.py        # Configuração do banco
│   └── main.py            # Aplicação principal
├── frontend/              # Frontend React
│   ├── src/
│   │   ├── components/    # Componentes React
│   │   ├── services/      # Serviços de API
│   │   ├── contexts/      # Contextos React
│   │   ├── locales/       # Arquivos de tradução
│   │   └── utils/         # Utilitários
│   ├── package.json
│   └── vite.config.js
├── scripts/               # Scripts de configuração
│   ├── setup_db.py        # Configuração inicial do banco
│   └── seed.py            # Dados de exemplo
├── requirement.txt        # Dependências Python
├── start.py              # Script de inicialização
└── README.md
```

## 🔧 Funcionalidades Principais

### Dashboard
- Métricas em tempo real
- Gráficos interativos
- Alertas de estoque
- Produtos em destaque

### Produtos
- Cadastro completo de produtos
- Controle de estoque
- Categorização
- Preços e códigos

### Fornecedores
- Cadastro de fornecedores
- Informações de contato
- Histórico de pedidos

### Alertas
- Monitoramento de estoque baixo
- Notificações automáticas
- Priorização de itens críticos

### Pedidos de Compra
- Criação de pedidos
- Acompanhamento de status
- Integração com fornecedores

### Insights
- Análises de vendas
- Recomendações de negócio
- Relatórios personalizados

### Reabastecimento Automático
- Sugestões inteligentes
- Cálculo de demanda
- Otimização de estoque

## 🎨 Temas e Personalização

O sistema suporta temas claro e escuro, com transições suaves e interface responsiva. Todos os componentes são adaptáveis e mantêm a consistência visual.

## 🌍 Internacionalização

O sistema oferece suporte completo a múltiplos idiomas:
- **Português**: Idioma nativo brasileiro
- **Inglês**: Idioma padrão do sistema
- **Seletor de Idioma**: Disponível na barra de navegação
- **Persistência**: Preferência salva automaticamente
- **Configurações**: Opção adicional no menu de configurações

Para mais detalhes sobre a implementação, consulte o arquivo `frontend/INTERNATIONALIZATION.md`.

## 🔒 Segurança

- Autenticação JWT
- Senhas criptografadas com bcrypt
- Isolamento de dados por usuário
- Validação de entrada com Pydantic
- CORS configurado adequadamente

## 📊 Banco de Dados

O sistema utiliza SQLite como banco de dados principal, com as seguintes tabelas:

- **users**: Usuários do sistema
- **suppliers**: Fornecedores
- **products**: Produtos
- **stock_movements**: Movimentações de estoque
- **sales**: Vendas
- **sale_items**: Itens de venda
- **purchase_orders**: Pedidos de compra
- **purchase_order_items**: Itens dos pedidos

## 🚀 Deploy

### Desenvolvimento
O projeto está configurado para desenvolvimento local com hot-reload tanto no backend quanto no frontend.

### Produção
Para deploy em produção, considere:
- Usar um banco de dados mais robusto (PostgreSQL, MySQL)
- Configurar um servidor web (Nginx, Apache)
- Implementar HTTPS
- Configurar variáveis de ambiente
- Usar um servidor WSGI para o FastAPI

## 🤝 Contribuição

1. Faça um fork do projeto
2. Crie uma branch para sua feature (`git checkout -b feature/AmazingFeature`)
3. Commit suas mudanças (`git commit -m 'Add some AmazingFeature'`)
4. Push para a branch (`git push origin feature/AmazingFeature`)
5. Abra um Pull Request

## 📝 Licença

Este projeto está sob a licença MIT. Veja o arquivo `LICENSE` para mais detalhes.

## 📞 Suporte

Para suporte ou dúvidas, entre em contato através dos canais disponibilizados no projeto.

---

**PC-Express** - Transformando o gerenciamento de inventário em uma experiência simples e eficiente! 🚀
