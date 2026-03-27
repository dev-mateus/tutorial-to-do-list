[Voltar ao inicio](../README.md)

# Tutorial Passo 1 - Criar base do projeto

## Objetivo do passo
Criar a estrutura tecnica minima para desenvolver uma aplicacao React com TypeScript usando Vite.

## O que sera aprendido
- Por que todo projeto precisa de uma base de build e execucao.
- Como scripts e configuracoes conectam desenvolvimento, compilacao e preview.

## Codigo necessario
### package.json
```json
{
  "name": "to-do-app",
  "private": true,
  "version": "0.0.0",
  "type": "module",
  "scripts": {
    "dev": "vite",
    "build": "tsc -b && vite build",
    "preview": "vite preview"
  },
  "dependencies": {
    "react": "^18.3.1",
    "react-dom": "^18.3.1"
  },
  "devDependencies": {
    "@types/node": "^22.10.1",
    "@types/react": "^18.3.12",
    "@types/react-dom": "^18.3.1",
    "@vitejs/plugin-react": "^4.3.4",
    "typescript": "^5.6.3",
    "vite": "^5.4.10"
  }
}
```

### vite.config.ts
```ts
import { defineConfig } from 'vite';
import react from '@vitejs/plugin-react';

export default defineConfig({
  plugins: [react()],
});
```

### tsconfig.json
```json
{
  "files": [],
  "references": [
    { "path": "./tsconfig.app.json" },
    { "path": "./tsconfig.node.json" }
  ]
}
```

### tsconfig.app.json
```json
{
  "compilerOptions": {
    "target": "ES2020",
    "module": "ESNext",
    "moduleResolution": "bundler",
    "jsx": "react-jsx",
    "strict": true,
    "noEmit": true
  },
  "include": ["src"]
}
```

### tsconfig.node.json
```json
{
  "compilerOptions": {
    "composite": true,
    "module": "ESNext",
    "moduleResolution": "bundler",
    "types": ["node"],
    "strict": true
  },
  "include": ["vite.config.ts"]
}
```

## Explicacao linha a linha
- Em package.json, o bloco scripts define os comandos principais do projeto.
- O script dev inicia o servidor local com Vite para desenvolvimento rapido.
- O script build valida TypeScript e gera versao de producao.
- O script preview abre localmente a versao final compilada.
- Em dependencies ficam bibliotecas usadas no app em execucao.
- Em devDependencies ficam ferramentas usadas apenas para desenvolver.
- Em vite.config.ts, defineConfig organiza a configuracao do Vite.
- O plugin react habilita suporte a JSX e recursos do React.
- Em tsconfig.json, references divide a configuracao em duas partes.
- tsconfig.app.json cobre o codigo da pasta src.
- tsconfig.node.json cobre arquivos que rodam no ambiente Node.

## O que o aluno construiu
Uma base profissional para iniciar o app com React, TypeScript e Vite, pronta para rodar, compilar e evoluir com seguranca.

[Voltar ao inicio](../README.md)

