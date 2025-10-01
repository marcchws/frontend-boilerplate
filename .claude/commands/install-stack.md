---
description: Instala a stack de frontend padrão e cria a estrutura de pastas.
allowed-tools: run_shell_command
---

**Sua tarefa é instalar a stack de frontend padrão e criar a estrutura de pastas recomendada neste projeto, seguindo estritamente os comandos definidos.**

Execute os seguintes passos em sequência, usando um comando para cada passo:

1.  **Criar Estrutura de Pastas:**
    - Cria a estrutura de pastas padrão em `src/` de forma idempotente (não falha se já existir).
    - `node -e "['components', 'constants', 'context', 'hooks', 'lib', 'mocks', 'store/features', 'store/sagas', 'types'].forEach(d => require('fs').mkdirSync('src/' + d, { recursive: true }))"`

2.  **Criar Arquivo de Mock de Exemplo:**
    - Cria um arquivo `index.ts` em `src\mocks` com um array de exemplo, somente se o arquivo não existir.
    - `if not exist src\mocks\index.ts (echo "export const exampleMocks = [];" > src\mocks\index.ts)`

3.  **Redux Toolkit e React-Redux:**
    - `npm install @reduxjs/toolkit react-redux`

4.  **Redux Saga:**
    - `npm install redux-saga`

5.  **React Query:**
    - `npm i @tanstack/react-query`

6.  **Axios:**
    - `npm install axios`

7.  **React Query Devtools (como dependência de desenvolvimento):**
    - `npm install @tanstack/react-query-devtools --save-dev`

8.  **Shadcn/UI:**
    - Avise o usuário que o próximo passo requer interação manual para responder às perguntas da CLI.
    - `npx shadcn@latest init`
