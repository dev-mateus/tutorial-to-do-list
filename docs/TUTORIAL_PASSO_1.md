[Voltar ao inicio](../README.md)

# Tutorial Passo 1 - Criar base do projeto

## Objetivo do passo
Criar o projeto do zero com React + Vite + TypeScript e preparar a estrutura inicial de pastas.

## O que sera aprendido
- Por que comecar pelo bootstrap economiza tempo e evita erros de configuracao.
- Como criar e validar a base tecnica antes de implementar funcionalidades.

## Codigo necessario
### Comandos iniciais (do zero)
```bash
npm create vite@latest to-do-app -- --template react-ts
cd to-do-app
npm install
npm run dev
```

### Estrutura de pastas a criar agora
```txt
src/
  components/
  hooks/
  types/
```

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
    "useDefineForClassFields": true,
    "lib": ["ES2020", "DOM", "DOM.Iterable"],
    "module": "ESNext",
    "skipLibCheck": true,
    "moduleResolution": "bundler",
    "allowImportingTsExtensions": false,
    "resolveJsonModule": true,
    "isolatedModules": true,
    "noEmit": true,
    "jsx": "react-jsx",
    "strict": true,
    "noUnusedLocals": true,
    "noUnusedParameters": true,
    "noFallthroughCasesInSwitch": true
  },
  "include": ["src"]
}
```

### tsconfig.node.json
```json
{
  "compilerOptions": {
    "composite": true,
    "skipLibCheck": true,
    "module": "ESNext",
    "moduleResolution": "bundler",
    "allowSyntheticDefaultImports": true,
    "types": ["node"],
    "strict": true
  },
  "include": ["vite.config.ts"]
}
```

### src/vite-env.d.ts
```ts
/// <reference types="vite/client" />
```

## Explicacao linha a linha
- Primeiro, os comandos criam a base oficial do Vite com React e TypeScript.
- npm install baixa as dependencias necessarias para rodar o projeto.
- npm run dev valida se o ambiente inicial esta funcionando.
- A criacao de components, hooks e types prepara a organizacao didatica da feature.
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
- vite-env.d.ts adiciona os tipos do Vite desde o inicio, evitando erro com import de CSS.

## O que o aluno construiu
Um projeto criado do zero, com estrutura inicial organizada e configuracao alinhada ao resultado final.

[Voltar ao inicio](../README.md)

