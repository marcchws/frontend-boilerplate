# Instalação - Shadcn/UI

Shadcn/UI não é uma biblioteca de componentes tradicional. Em vez de instalar um pacote, você usa a CLI para adicionar componentes reutilizáveis diretamente ao seu projeto.

**Nota:** Este processo irá instalar e configurar o Tailwind CSS, que é um pré-requisito.

## 1. Inicialização

Execute o comando `init` na raiz do seu projeto. Ele fará algumas perguntas para configurar o `components.json`.

```bash
npx shadcn@latest init
```

## 2. Adicionando Componentes

Após a inicialização, você pode adicionar componentes individualmente conforme a necessidade.

```bash
npx shadcn@latest add [nome-do-componente]
```

**Exemplo:**

```bash
npx shadcn@latest add button
npx shadcn@latest add card
npx shadcn@latest add dialog
```

---

*Fonte: [Documentação do Shadcn/UI](https://ui.shadcn.com/docs/installation/next)*
