[Voltar ao inicio](../README.md)

# Tutorial Passo 9 - Estilizacao com CSS puro

## Objetivo do passo
Aplicar um layout limpo, legivel e responsivo usando apenas CSS puro.

## O que sera aprendido
- Por que separar CSS global de CSS da pagina.
- Como usar flexbox, hover e estilo visual para tarefa concluida.

## Codigo necessario
### src/index.css
```css
:root {
  font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
  color: #102026;
  background-color: #f6f4ef;
  line-height: 1.5;
  font-weight: 400;
}

* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

body {
  min-height: 100vh;
  background:
    radial-gradient(circle at 10% 10%, #dff3ea 0%, transparent 40%),
    radial-gradient(circle at 90% 90%, #ffe6cc 0%, transparent 40%),
    #f6f4ef;
}

button,
input {
  font: inherit;
}
```

### src/App.css
```css
.app-shell {
  min-height: 100vh;
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 24px;
}

.todo-card {
  width: 100%;
  max-width: 760px;
  background: #fffdf8;
  border: 1px solid #eadfce;
  border-radius: 20px;
  padding: 28px;
}

.task-input {
  display: flex;
  gap: 10px;
  margin: 20px 0;
}

.task-input button:hover {
  filter: brightness(1.1);
}

.task-item.is-completed span {
  text-decoration: line-through;
  color: #648176;
}
```

## Explicacao linha a linha
- index.css define padroes globais para toda aplicacao.
- O reset com * evita variacoes inesperadas entre navegadores.
- body recebe fundo e altura minima para ocupar a tela.
- Em App.css, app-shell centraliza o card com flexbox.
- task-input organiza input e botao em linha com gap.
- button:hover melhora feedback visual para o usuario.
- is-completed destaca visualmente tarefa finalizada.

## O que o aluno construiu
Uma interface clara e responsiva com CSS puro, sem depender de frameworks.

[Voltar ao inicio](../README.md)

