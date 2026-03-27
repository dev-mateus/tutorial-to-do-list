[Voltar ao inicio](../README.md)

# Tutorial Passo 9 - Estilização com CSS puro
> Capítulo 9 de 11

## 1. Objetivo do passo
Aplicar o visual final do projeto com CSS puro, incluindo responsividade.

## 2. O que será aprendido
- Por que separar CSS global de CSS da tela principal.
- Como usar flexbox para layout.
- Como destacar tarefas concluídas visualmente.

## 3. Código necessário
### ✏️ Editar — `src/index.css`
> Caminho completo: `to-do-app/src/index.css`.  
> **Ação:** o Vite criou este arquivo com estilos padrão. Substitua **todo** o conteúdo pelo código abaixo.
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

### ✏️ Editar — `src/App.css`
> Caminho completo: `to-do-app/src/App.css`.  
> **Ação:** o Vite criou este arquivo com estilos padrão. Substitua **todo** o conteúdo pelo código abaixo.
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
  box-shadow: 0 20px 40px rgba(40, 30, 10, 0.08);
}

.todo-header {
  margin-bottom: 18px;
}

.badge {
  display: inline-block;
  background: #f4e8cf;
  color: #6d4d1f;
  border-radius: 999px;
  padding: 4px 12px;
  font-size: 0.82rem;
  margin-bottom: 8px;
}

.todo-header h1 {
  font-size: 1.9rem;
  color: #1f2f36;
  margin-bottom: 4px;
}

.todo-header p {
  color: #54656d;
}

.task-input {
  display: flex;
  gap: 10px;
  margin: 20px 0;
}

.task-input input {
  flex: 1;
  border: 1px solid #d8cab8;
  border-radius: 12px;
  padding: 12px 14px;
  outline: none;
  transition: border-color 0.2s ease;
}

.task-input input:focus {
  border-color: #567c71;
}

.task-input button {
  border: 0;
  border-radius: 12px;
  padding: 12px 18px;
  background: #356859;
  color: #fff;
  cursor: pointer;
  transition: filter 0.2s ease;
}

.task-input button:hover {
  filter: brightness(1.1);
}

.task-stats {
  display: flex;
  gap: 12px;
  flex-wrap: wrap;
  margin-bottom: 18px;
}

.task-stats article {
  flex: 1;
  min-width: 120px;
  background: #f9f4ea;
  border: 1px solid #ecdfcb;
  border-radius: 12px;
  padding: 12px;
  display: flex;
  align-items: baseline;
  justify-content: space-between;
}

.task-stats strong {
  font-size: 1.2rem;
  color: #2e4f45;
}

.task-stats span {
  color: #6d7669;
}

.task-list {
  list-style: none;
  display: flex;
  flex-direction: column;
  gap: 10px;
}

.task-item {
  border: 1px solid #e7dcca;
  border-radius: 12px;
  padding: 12px 14px;
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 12px;
  background: #fffcf3;
}

.task-item label {
  display: flex;
  align-items: center;
  gap: 10px;
  flex: 1;
  color: #2f3f45;
}

.task-item input[type='checkbox'] {
  width: 18px;
  height: 18px;
  accent-color: #356859;
}

.task-item button {
  border: 1px solid #c84747;
  background: transparent;
  color: #c84747;
  border-radius: 10px;
  padding: 8px 12px;
  cursor: pointer;
  transition: all 0.2s ease;
}

.task-item button:hover {
  background: #c84747;
  color: #fff;
}

.task-item.is-completed {
  border-color: #b9d2c8;
  background: #edf7f2;
}

.task-item.is-completed span {
  text-decoration: line-through;
  color: #648176;
}

.empty-list {
  border: 1px dashed #cebfa8;
  border-radius: 12px;
  padding: 18px;
  color: #6c6d61;
  text-align: center;
}

@media (max-width: 640px) {
  .todo-card {
    padding: 20px;
  }

  .task-input {
    flex-direction: column;
  }

  .task-input button {
    width: 100%;
  }

  .task-item {
    flex-direction: column;
    align-items: flex-start;
  }

  .task-item button {
    width: 100%;
  }
}
```

## 4. Explicação linha a linha
- Analogia: o CSS é a roupa da aplicação.
- index.css cuida das regras globais (base da roupa).
- App.css cuida do visual da página de tarefas (detalhes da roupa).
- flexbox organiza elementos em linha e coluna de forma simples.
- hover melhora o feedback quando o usuário passa o mouse.
- is-completed sinaliza visualmente tarefa concluída.
- media query ajusta o layout para celular.

## 5. O que o aluno construiu
A interface final, limpa e responsiva, igual ao resultado esperado do projeto.

## 6. Dicas
- Separe estilo global de estilo da página para manter organização.
- Teste responsividade reduzindo a largura da janela.

## 7. Erros comuns
- Misturar classes sem correspondência com o JSX.
- Remover estilos de estados e perder feedback visual.

## 8. Checkpoints de aprendizado
- Layout fica legível em desktop e mobile.
- Tarefa concluída aparece com visual diferente.

## 9. Resumo do capítulo
Você finalizou a camada visual da aplicação com CSS puro e responsivo.

[Voltar ao inicio](../README.md)


