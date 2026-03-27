[Voltar ao inicio](../README.md)

# Tutorial Passo 2 - Ponto de entrada

## Objetivo do passo
Entender e montar o fluxo de inicializacao da aplicacao no navegador.

## O que sera aprendido
- Por que existe um arquivo HTML base mesmo em projeto React.
- Como React entra na pagina e renderiza o App.

## Codigo necessario
### index.html
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

### src/main.tsx
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

## Explicacao linha a linha
- Em index.html, a div root e o ponto onde o React vai desenhar a tela.
- O script module chama o arquivo main.tsx como inicio da aplicacao.
- Em main.tsx, ReactDOM.createRoot encontra a div root.
- O metodo render envia o componente App para a tela.
- React.StrictMode ajuda a identificar problemas comuns no desenvolvimento.
- O import de index.css aplica estilo global desde o inicio.

## O que o aluno construiu
A inicializacao completa do projeto: do HTML ate o primeiro componente React na tela.

[Voltar ao inicio](../README.md)

