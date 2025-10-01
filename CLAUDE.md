# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a modern frontend boilerplate built with Next.js 15 (App Router), React 19, and TypeScript. It uses Turbopack for faster builds and includes a comprehensive state management setup.

## Commands

### Development
- `npm run dev` - Start development server with Turbopack
- `npm run build` - Build for production with Turbopack
- `npm start` - Start production server
- `npm run lint` - Run ESLint

### Stack Installation
- `/install-stack` - Custom command to install dependencies and create folder structure

## Architecture

### State Management Strategy

This project uses a **dual state management approach**:

1. **Redux Toolkit + Redux Saga** (`src/store/`)
   - Use for: Global application state, complex side effects, cross-cutting concerns
   - Structure:
     - `store/features/` - Redux slices for domain-specific state
     - `store/sagas/` - Side effect handlers for async operations
   - Redux Saga handles complex async flows and side effects

2. **TanStack Query (React Query)**
   - Use for: Server state, API caching, data fetching
   - React Query Devtools available in development
   - Handles cache invalidation, refetching, and optimistic updates

**When to use which:**
- Redux: UI state, user preferences, auth state, complex workflows
- React Query: API data, server-side state, remote data caching

### Project Structure

```
src/
├── app/              # Routes and pages (page.tsx, layout.tsx, loading.tsx, error.tsx)
├── components/       # Reusable UI components (buttons, cards, forms, etc)
│   └── ui/          # Shadcn/UI components (auto-generated via MCP)
├── constants/        # Static values (API URLs, config values, enums)
├── context/          # React Context providers (theme, auth, etc)
├── hooks/            # Custom React hooks (data fetching, form handling, side effects)
├── lib/              # Utilities and helpers (formatters, validators, API clients)
├── mocks/            # Mock data for development and testing
├── store/            # Redux store
│   ├── features/     # Redux slices (user state, app settings, UI state)
│   └── sagas/        # Side effects handlers (complex async flows, workflows)
└── types/            # TypeScript interfaces and types (API responses, entities, props)
```

### Path Aliases

TypeScript and Shadcn/UI are configured with the following aliases:
- `@/*` - Maps to `src/*`
- `@/components` - Components directory
- `@/lib` - Library utilities
- `@/hooks` - Custom hooks
- `@/ui` - Shadcn/UI components (`@/components/ui`)

### Styling

- **Tailwind CSS v4** with PostCSS
- **Shadcn/UI** components use the "new-york" style variant
- Base color: neutral
- CSS variables enabled for theming
- Icons: Lucide React

### HTTP Client

- **Axios** is installed for HTTP requests
- Consider creating an Axios instance in `src/lib/` with interceptors for auth/error handling

## Key Configuration Files

- `components.json` - Shadcn/UI configuration (style: new-york, RSC enabled)
- `tsconfig.json` - TypeScript with `@/*` path alias
- `next.config.ts` - Next.js configuration (currently minimal)
- `src/app/globals.css` - Global styles and Tailwind directives

## Shadcn/UI Component Management

- Use MCP tools (`mcp__shadcn__*`) to search, view, and install components
- Registry configurations are in `components.json` - MCP tools automatically access them
- Use MCP tools to get installation commands, then execute with Bash

## Development Notes

### Next.js App Router
- This project uses the App Router (not Pages Router)
- Server Components are the default
- Client Components require `'use client'` directive

### TypeScript
- Strict mode enabled
- Target: ES2017

### Fonts
- Inter is configured in `src/app/layout.tsx`