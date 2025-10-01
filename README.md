# Frontend Boilerplate

Boilerplate moderno para projetos frontend com Next.js 15, React 19 e uma stack completa de ferramentas de desenvolvimento.

## Stack Tecnológica

### Core
- **[Next.js 15](https://nextjs.org)** - Framework React com App Router e Turbopack
- **[React 19](https://react.dev)** - Biblioteca para interfaces de usuário
- **[TypeScript](https://www.typescriptlang.org)** - Superset JavaScript com tipagem estática

### Estilização
- **[Tailwind CSS v4](https://tailwindcss.com)** - Framework CSS utility-first
- **[Shadcn/UI](https://ui.shadcn.com)** - Componentes reutilizáveis e acessíveis
- **[Lucide React](https://lucide.dev)** - Ícones modernos

### Gerenciamento de Estado
- **[Redux Toolkit](https://redux-toolkit.js.org)** - Gerenciamento de estado global
- **[React-Redux](https://react-redux.js.org)** - Bindings oficiais do Redux para React
- **[Redux Saga](https://redux-saga.js.org)** - Middleware para side effects

### Data Fetching
- **[TanStack Query (React Query)](https://tanstack.com/query)** - Gerenciamento de estado do servidor
- **[Axios](https://axios-http.com)** - Cliente HTTP

### DevTools
- **[React Query Devtools](https://tanstack.com/query/latest/docs/react/devtools)** - Ferramentas de desenvolvimento para React Query
- **[ESLint](https://eslint.org)** - Linter para JavaScript/TypeScript

## Estrutura de Pastas

```
src/
├── app/              # App Router do Next.js (rotas e layouts)
├── components/       # Componentes React reutilizáveis
├── constants/        # Constantes da aplicação
├── context/          # React Context providers
├── hooks/            # Custom React hooks
├── lib/              # Utilitários e configurações (Shadcn/UI)
├── mocks/            # Dados mockados para desenvolvimento
├── store/            # Redux store
│   ├── features/     # Redux slices
│   └── sagas/        # Redux sagas
└── types/            # TypeScript types e interfaces
```

## Getting Started

### Instalação

```bash
npm install
```

### Desenvolvimento

```bash
npm run dev
```

Abra [http://localhost:3000](http://localhost:3000) no navegador para ver o resultado.

### Build

```bash
npm run build
```

### Produção

```bash
npm start
```

### Lint

```bash
npm run lint
```

## Configuração

### Redux Store

Configure sua store em `src/store/` seguindo o padrão Redux Toolkit:

- **features/** - Crie slices para cada domínio da aplicação
- **sagas/** - Implemente sagas para side effects assíncronos

### React Query

Configure o QueryClient no root da aplicação para gerenciar cache e requisições.

### Shadcn/UI

Adicione componentes usando:

```bash
npx shadcn@latest add [component-name]
```

Os componentes serão instalados em `src/lib/ui/`.

## Recursos

- **[Next.js Docs](https://nextjs.org/docs)** - Documentação oficial do Next.js
- **[React Docs](https://react.dev)** - Documentação oficial do React
- **[Redux Toolkit Docs](https://redux-toolkit.js.org)** - Documentação do Redux Toolkit
- **[TanStack Query Docs](https://tanstack.com/query)** - Documentação do React Query
- **[Shadcn/UI](https://ui.shadcn.com)** - Biblioteca de componentes
- **[Tailwind CSS](https://tailwindcss.com/docs)** - Documentação do Tailwind

## Deploy

Recomendado deploy na [Vercel Platform](https://vercel.com/new) para melhor integração com Next.js.

Veja a [documentação de deploy do Next.js](https://nextjs.org/docs/app/building-your-application/deploying) para mais detalhes.
