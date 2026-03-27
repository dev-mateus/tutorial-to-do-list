[Voltar ao inicio](../README.md)

# Tutorial Passo 2 - Ponto de entrada
> Capítulo 2 de 11

## 1. Objetivo do passo
Entender como a aplicação nasce no navegador, do `HTML` até o componente `React`.

## 2. O que será aprendido
- Por que `React` ainda precisa de um arquivo `HTML`.
- Como o arquivo `main.tsx` conecta o `React` com a página.
- Como usar um `App` temporário para não pular etapas.

## 3. Código necessário
### Bloco de Arquivo — Editar `index.html`
> Tipo: `Arquivo`  
> Ação: `Editar`  
> Caminho completo: `to-do-app/index.html`.
> Observação: este arquivo fica na raiz do projeto, fora da pasta `src/`.
```html
<!doctype html>
<html lang="pt-BR">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>To-Do App</title>
  </head>
  <body>
    <div id="root"></div>
    <script type="module" src="/src/main.tsx"></script>
  </body>
</html>
```

### Bloco de Arquivo — Editar `src/main.tsx`
> Tipo: `Arquivo`  
> Ação: `Editar`  
> Caminho completo: `to-do-app/src/main.tsx`.
```tsx
import React from 'react';
import ReactDOM from 'react-dom/client';
import App from './App';
import './index.css';

ReactDOM.createRoot(document.getElementById('root') as HTMLElement).render(
  <React.StrictMode>
    <App />
  </React.StrictMode>,
);
```

### Bloco de Arquivo — Editar `src/App.tsx` (versão temporária)
> Tipo: `Arquivo`  
> Ação: `Editar`  
> Caminho completo: `to-do-app/src/App.tsx`.
> Observação: esta versão simples será substituída no Passo 8.
```tsx
function App() {
  return <h1>Projeto To-Do iniciado</h1>;
}

export default App;
```

## 4. Explicação linha a linha
- `index.html` define a estrutura mínima da página e contém a `div` com `id="root"`, que será o ponto de montagem do `React`.
- O script `type="module"` aponta para `src/main.tsx`, que é o arquivo de entrada da aplicação.
- `main.tsx` importa o `App` e o `CSS` global, criando a raiz do `React` com `ReactDOM.createRoot`.
- `document.getElementById('root')` localiza o elemento `HTML` onde a aplicação será renderizada.
- `React.StrictMode` ativa verificações extras em desenvolvimento.
- O `App` temporário retorna um `h1` simples para validar que a renderização do `React` está funcionando antes da montagem completa.

## 5. O que o aluno construiu
Um fluxo de inicialização funcionando de ponta a ponta: HTML, ReactDOM e App na tela.

## 6. Dicas
- Pense no arquivo `index.html` como a porta de entrada da aplicação.
- Mantenha o `App` temporário simples para testar o fluxo.

## 7. Erros comuns
- Remover a div com id root do HTML.
- Importar `App` com caminho errado no `main.tsx`.

## 8. Checkpoints de aprendizado
- Execute o comando abaixo e verifique no navegador se a página exibe o texto Projeto To-Do iniciado.

```bash
npm run dev
```

- Confirme que não há erro no console do navegador e que alterar o texto em `src/App.tsx` atualiza a tela ao salvar.

## 9. Resumo do capítulo
Você conectou HTML e React e confirmou que o app inicializa corretamente no navegador.

[Voltar ao inicio](../README.md)


