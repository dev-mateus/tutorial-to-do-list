[Voltar ao inicio](../README.md)

# Tutorial Passo 8 - Montar App principal
> Capítulo 8 de 11

## 1. Objetivo do passo
Conectar todos os componentes e o hook para formar a versão funcional da aplicação.

## 2. O que será aprendido
- Por que o App deve ser um orquestrador, não um depósito de lógica.
- Como conectar dados e ações entre hook e componentes.

## 3. Código necessário
### ✏️ Editar — `src/App.tsx`
> Caminho completo: `to-do-app/src/App.tsx`.  
> **Ação:** este arquivo já existe com o conteúdo temporário do Passo 2. Substitua **todo** o conteúdo pelo código abaixo.
```tsx
import './App.css';
import { TaskInput } from './components/TaskInput';
import { TaskList } from './components/TaskList';
import { useTasks } from './hooks/useTasks';

function App() {
  const { tasks, stats, addTask, toggleTask, removeTask } = useTasks();

  return (
    <main className="app-shell">
      <section className="todo-card">
        <header className="todo-header">
          <p className="badge">Estudo React + TypeScript</p>
          <h1>Lista de Tarefas</h1>
          <p>Organize seu dia com uma lista simples e objetiva.</p>
        </header>

        <TaskInput onAddTask={addTask} />

        <section className="task-stats" aria-label="Contadores de tarefas">
          <article>
            <strong>{stats.total}</strong>
            <span>Total</span>
          </article>
          <article>
            <strong>{stats.completed}</strong>
            <span>Concluídas</span>
          </article>
          <article>
            <strong>{stats.pending}</strong>
            <span>Pendentes</span>
          </article>
        </section>

        <TaskList tasks={tasks} onToggleTask={toggleTask} onRemoveTask={removeTask} />
      </section>
    </main>
  );
}

export default App;
```

## 4. Explicação linha a linha
- Pense no App como um maestro: ele coordena, mas não toca todos os instrumentos.
- useTasks entrega estado e funções prontas.
- TaskInput recebe addTask para incluir novas tarefas.
- task-stats mostra os contadores calculados no hook.
- TaskList recebe tarefas e as funções de ação.
- Assim, cada parte tem responsabilidade clara.

## 5. O que o aluno construiu
A primeira versão completa da To-Do App, conectando interface, lógica e contadores.

## 6. Dicas
- Mantenha o App como orquestrador: ele conecta peças, não concentra regras.
- Leia o retorno do hook como uma API local da feature.

## 7. Erros comuns
- Colocar lógica de negócio extra dentro do App.
- Passar props com nomes diferentes dos esperados nos componentes.

## 8. Checkpoints de aprendizado
- Consegue mapear quem fornece e quem consome cada prop.
- Contadores e ações funcionam juntos na tela principal.

## 9. Resumo do capítulo
Você integrou componentes e hook em uma tela completa e funcional.

[Voltar ao inicio](../README.md)


