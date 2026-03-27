[Voltar ao inicio](../README.md)

# Tutorial Passo 1 - Criar base do projeto
> Capítulo 1 de 11

## 1. Objetivo do passo
Criar o projeto do zero com React, Vite e TypeScript, deixando tudo pronto para os próximos passos.

## 2. O que será aprendido
- Por que começar pela base evita dor de cabeça depois.
- Como criar o projeto e validar se ele está funcionando.
- Como organizar as pastas principais para estudar com clareza.

## 3. Código necessário
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

## 4. Explicação linha a linha
- Pense no projeto como uma casa: antes de decorar, você precisa da fundação.
- npm create vite cria essa fundação pronta para React + TypeScript.
- cd to-do-app entra na pasta do projeto.
- npm install baixa os pacotes necessários.
- npm run dev liga o servidor local para você testar no navegador.
- A separação em components, hooks e types é como separar cômodos da casa: cada coisa no seu lugar.
- O arquivo vite-env.d.ts ensina ao TypeScript como entender recursos do Vite, como import de CSS.

## 5. O que o aluno construiu
Uma base profissional e organizada, pronta para receber as funcionalidades da To-Do App sem improviso.

## 6. Dicas
- Rode npm run dev logo após criar o projeto para validar a base.
- Crie as pastas components, hooks e types no início para evitar bagunça depois.

## 7. Erros comuns
- Esquecer de executar npm install antes do npm run dev.
- Criar o projeto sem template TypeScript, usando react em vez de react-ts.

## 8. Checkpoints de aprendizado
- Consegue abrir o projeto no navegador sem erro.
- Entende para que servem package.json e vite.config.ts.

## 9. Resumo do capítulo
Você montou a fundação do projeto e preparou o terreno para construir funcionalidades com segurança.

[Voltar ao inicio](../README.md)


