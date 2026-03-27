[Voltar ao inicio](../README.md)

# Tutorial Passo 2 - Ponto de entrada
> Capítulo 2 de 11

## 1. Objetivo do passo
Entender como a aplicação nasce no navegador, do HTML até o componente React.

## 2. O que será aprendido
- Por que React ainda precisa de um arquivo HTML.
- Como o arquivo main.tsx conecta o React com a página.
- Como usar um App temporário para não pular etapas.

## 3. Código necessário
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

### src/App.tsx (temporário)
```tsx
function App() {
  return <h1>Projeto To-Do iniciado</h1>;
}

export default App;
```

## 4. Explicação linha a linha
- Imagine que o HTML é o palco, e o React é o ator.
- A div root é o local do palco onde o ator vai aparecer.
- main.tsx pega o componente App e coloca dentro da root.
- React.StrictMode ajuda a detectar problemas cedo.
- O App temporário funciona como um teste rápido para garantir que tudo está conectado.
- Mais adiante, no Passo 8, você troca esse App simples pela versão completa.

## 5. O que o aluno construiu
Um fluxo de inicialização funcionando de ponta a ponta: HTML, ReactDOM e App na tela.

## 6. Dicas
- Pense no index.html como a porta de entrada da aplicação.
- Mantenha o App temporário simples para testar o fluxo.

## 7. Erros comuns
- Remover a div com id root do HTML.
- Importar App com caminho errado no main.tsx.

## 8. Checkpoints de aprendizado
- Consegue explicar o fluxo index.html para main.tsx para App.tsx.
- A tela mostra o texto temporário sem erro.

## 9. Resumo do capítulo
Você conectou HTML e React e confirmou que o app inicializa corretamente no navegador.

[Voltar ao inicio](../README.md)


