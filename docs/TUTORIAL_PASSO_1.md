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

### Estrutura completa do projeto final
> Use este mapa para saber onde cada arquivo fica. Ao longo do tutorial, cada passo indicará se o arquivo deve ser **criado** ou **editado**.

```
to-do-app/                   ← pasta raiz do projeto
├── index.html               ← editado no Passo 2
├── package.json             ← gerado automaticamente pelo Vite
├── tsconfig.json            ← gerado automaticamente pelo Vite
├── vite.config.ts           ← gerado automaticamente pelo Vite
└── src/
    ├── main.tsx             ← editado no Passo 2
    ├── App.tsx              ← editado nos Passos 2 e 8
    ├── App.css              ← editado no Passo 9
    ├── index.css            ← editado no Passo 9
    ├── vite-env.d.ts        ← criado neste Passo 1, verificado no Passo 10
    ├── components/
    │   ├── TaskInput.tsx    ← criado no Passo 5
    │   ├── TaskItem.tsx     ← criado no Passo 6
    │   └── TaskList.tsx     ← criado no Passo 7
    ├── hooks/
    │   └── useTasks.ts      ← criado no Passo 4
    └── types/
        └── Task.ts          ← criado no Passo 3
```

### 📄 Criar — `src/vite-env.d.ts`
> Caminho completo: `to-do-app/src/vite-env.d.ts`.  
> **Ação:** crie este arquivo na raiz da pasta `src/`.
```ts
/// <reference types="vite/client" />
```

## 4. Explicação linha a linha
- O comando abaixo gera um projeto React com TypeScript já configurado pelo Vite.

```bash
npm create vite@latest to-do-app -- --template react-ts
```

- O comando abaixo muda o terminal para a pasta raiz do projeto, onde os próximos comandos serão executados.

```bash
cd to-do-app
```

- O comando abaixo instala as dependências listadas no `package.json`.

```bash
npm install
```

- O comando abaixo inicia o servidor de desenvolvimento local.

```bash
npm run dev
```

- As pastas components, hooks e types preparam a organização do código por responsabilidade.
- O arquivo `src/vite-env.d.ts` registra os tipos do Vite para que o TypeScript reconheça recursos do ambiente, como importação de CSS.

## 5. O que o aluno construiu
Uma base profissional e organizada, pronta para receber as funcionalidades da To-Do App sem improviso.

## 6. Dicas
- Execute o comando abaixo logo após criar o projeto para validar a base.

```bash
npm run dev
```

- Crie as pastas components, hooks e types no início para evitar bagunça depois.

## 7. Erros comuns
- Esquecer de executar os comandos abaixo na ordem correta.

```bash
npm install
npm run dev
```

- Criar o projeto sem template TypeScript, usando react em vez de react-ts.

## 8. Checkpoints de aprendizado
- Execute o comando abaixo e verifique no navegador se a aplicação padrão do Vite abre sem tela em branco ou erro de compilação.

```bash
npm run dev
```

- Confirme que a estrutura base do projeto existe na pasta to-do-app e que a pasta src já contém os arquivos principais gerados pelo Vite.

## 9. Resumo do capítulo
Você montou a fundação do projeto e preparou o terreno para construir funcionalidades com segurança.

[Voltar ao inicio](../README.md)


