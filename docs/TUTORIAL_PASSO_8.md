[Voltar ao inicio](../README.md)

# Tutorial Passo 8 - Montar App principal

## Objetivo do passo
Conectar componentes visuais com a logica do hook useTasks.

## O que sera aprendido
- Por que o App deve orquestrar, e nao concentrar toda a logica.
- Como compor componentes e passar props entre eles.

## Codigo necessario
### src/App.tsx
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
            <span>Concluidas</span>
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

## Explicacao linha a linha
- O import de useTasks traz a logica da feature sem poluir o App.
- O hook retorna lista, contadores e funcoes de acao.
- TaskInput recebe addTask para cadastrar novas tarefas.
- O bloco task-stats mostra total, concluidas e pendentes.
- TaskList recebe tarefas e callbacks para concluir e remover.
- export default App torna este componente o principal da aplicacao.

## O que o aluno construiu
A tela principal funcional da To-Do App, conectando interface e regras de negocio.

[Voltar ao inicio](../README.md)

