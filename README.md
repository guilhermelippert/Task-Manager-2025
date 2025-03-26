# Task Manager 2025

Um sistema de gerenciamento de tarefas pessoal com interface Kanban, focado em simplicidade e eficiência, utilizando design minimalista.

## 🌟 Funcionalidades

- **Quadro Kanban Completo**: Colunas personalizáveis e gerenciamento visual de tarefas
- **Gerenciamento de Tarefas**: Crie, edite e organize tarefas com diferentes prioridades
- **Sistema de Delegação**: Marque tarefas como delegadas para acompanhamento
- **Arrastar e Soltar**: Mova tarefas entre colunas com interface intuitiva
- **Modo Escuro**: Interface adaptável que respeita a preferência do usuário
- **Interface Responsiva**: Funciona bem em dispositivos desktop e móveis
- **Autenticação**: Login com Google via Supabase (em implementação)

## 🛠️ Tecnologias

- **Frontend**: Next.js 14, React, TypeScript, Tailwind CSS
- **Banco de Dados e Autenticação**: Supabase
- **UI Components**: Interface minimalista com ícones Lucide
- **Drag and Drop**: API nativa de HTML5

## 🚀 Estado Atual do Desenvolvimento

O projeto está em desenvolvimento ativo, tendo sido implementado:

- Interface completa do quadro Kanban com design moderno
- Sistema de gerenciamento de tarefas com prioridades e datas
- Funcionalidade de arrastar e soltar para movimentação de tarefas
- Interface adaptativa com suporte a modo claro/escuro
- Layout responsivo para diferentes dispositivos

## 📋 Próximos Passos

- Finalizar a integração com Supabase para persistência de dados
- Implementar autenticação completa com Google
- Adicionar sistema de filtros e busca
- Implementar estatísticas de produtividade
- Adicionar notificações para tarefas com prazo próximo

## 📝 Estrutura do Banco de Dados (Planejado)

### Tabela: users
- id: uuid (primary key)
- email: string
- name: string
- created_at: timestamp
- last_login: timestamp
- settings: json (preferências do usuário)

### Tabela: kanban_columns
- id: uuid (primary key)
- user_id: uuid (foreign key)
- title: string
- order: integer
- color: string (opcional)
- created_at: timestamp

### Tabela: tasks
- id: uuid (primary key)
- user_id: uuid (foreign key)
- column_id: uuid (foreign key)
- title: string
- description: text
- is_delegated: boolean
- delegated_to: string (opcional)
- priority: integer (1-5)
- due_date: timestamp (opcional)
- completed: boolean
- completed_at: timestamp (opcional)
- created_at: timestamp
- updated_at: timestamp
- color: string (opcional)
- position: integer (para ordenar dentro da coluna)
- tags: array (opcional)

## 📂 Estrutura do Projeto

### Componentes Principais
- `KanbanBoard.tsx`: Componente principal que gerencia o quadro Kanban
- `KanbanColumn.tsx`: Componente para exibir cada coluna do Kanban
- `TaskCard.tsx`: Componente para exibir os cards de tarefas
- `TaskFormModal.tsx`: Modal para criação e edição de tarefas
- `ColumnFormModal.tsx`: Modal para criação e edição de colunas
- `EmptyColumnState.tsx`: Componente para exibir quando uma coluna está vazia
- `SignInWithGoogle.tsx`: Componente para autenticação com Google

### Diretórios
- `/src/app`: Páginas e layout principal da aplicação
- `/src/components`: Componentes React compartilhados
- `/src/lib`: Utilitários, hooks e contextos

## 📷 Screenshots

*Screenshots serão adicionados em breve*

## 🔧 Instalação e Configuração

### 1. Clonar o Repositório

```bash
git clone https://github.com/guilhermelippert/Task-Manager-2025.git
cd Task-Manager-2025
```

### 2. Instalar Dependências

```bash
npm install
```

### 3. Configuração do Supabase (Planejado)

1. Crie uma conta no [Supabase](https://supabase.com)
2. Crie um novo projeto
3. Configure as tabelas conforme definido na estrutura de banco de dados
4. Configure a autenticação com Google no Supabase

### 4. Configuração das Variáveis de Ambiente

Crie um arquivo `.env.local` com as seguintes variáveis:

```
NEXT_PUBLIC_SUPABASE_URL=sua-url-do-supabase
NEXT_PUBLIC_SUPABASE_ANON_KEY=sua-chave-anônima-do-supabase
```

### 5. Executar o Projeto

```bash
npm run dev
```

Acesse o projeto em [http://localhost:3000](http://localhost:3000).

## 📜 Licença

Este projeto está sob a licença MIT.

## 🤝 Contribuições

Contribuições são bem-vindas! Sinta-se à vontade para abrir issues ou enviar pull requests.