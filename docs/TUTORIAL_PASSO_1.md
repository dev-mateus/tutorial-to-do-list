[Voltar ao inicio](../README.md)

# Tutorial Passo 1 - Criar base do projeto
> Capitulo 1 de 11

## 1. Objetivo do passo
Criar o projeto do zero com React, Vite e TypeScript, deixando tudo pronto para os proximos passos.

## 2. O que sera aprendido
- Por que comecar pela base evita dor de cabeca depois.
- Como criar o projeto e validar se ele esta funcionando.
- Como organizar as pastas principais para estudar com clareza.

## 3. Codigo necessario
### Comandos iniciais
```bash
npm create vite@latest to-do-app -- --template react-ts
cd to-do-app
npm install
npm run dev
```

### Pastas que vamos usar no tutorial
```txt
src/
  components/
  hooks/
  types/
```

### src/vite-env.d.ts
```ts
/// <reference types="vite/client" />
```

## 4. Explicacao linha a linha
- Pense no projeto como uma casa: antes de decorar, voce precisa da fundacao.
- npm create vite cria essa fundacao pronta para React + TypeScript.
- cd to-do-app entra na pasta do projeto.
- npm install baixa os pacotes necessarios.
- npm run dev liga o servidor local para voce testar no navegador.
- A separacao em components, hooks e types e como separar comodos da casa: cada coisa no seu lugar.
- O arquivo vite-env.d.ts ensina ao TypeScript como entender recursos do Vite, como import de CSS.

## 5. O que o aluno construiu
Uma base profissional e organizada, pronta para receber as funcionalidades da To-Do App sem improviso.

## 6. Dicas
- Rode npm run dev logo apos criar o projeto para validar a base.
- Crie as pastas components, hooks e types no inicio para evitar bagunca depois.

## 7. Erros comuns
- Esquecer de executar npm install antes do npm run dev.
- Criar o projeto sem template TypeScript, usando react em vez de react-ts.

## 8. Checkpoints de aprendizado
- Consegue abrir o projeto no navegador sem erro.
- Entende para que servem package.json e vite.config.ts.

## 9. Resumo do capitulo
Voce montou a fundacao do projeto e preparou o terreno para construir funcionalidades com seguranca.

[Voltar ao inicio](../README.md)


