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

### Adding Components
- `npx shadcn@latest add [component-name]` - Add Shadcn/UI components

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
├── app/              # Next.js App Router (routes, layouts, pages)
├── components/       # Reusable React components
│   └── ui/          # Shadcn/UI components (auto-generated)
├── constants/        # Application constants
├── context/          # React Context providers
├── hooks/            # Custom React hooks
├── lib/              # Utilities and configurations
├── mocks/            # Mock data for development
├── store/            # Redux store
│   ├── features/     # Redux Toolkit slices
│   └── sagas/        # Redux Saga handlers
└── types/            # TypeScript type definitions
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

## Development Notes

### Next.js App Router
- This project uses the App Router (not Pages Router)
- Server Components are the default
- Client Components require `'use client'` directive

### TypeScript
- Strict mode enabled
- Target: ES2017

### Fonts
- Geist Sans and Geist Mono are pre-configured in `src/app/layout.tsx`
