[Voltar ao inicio](../README.md)

# Tutorial Passo 8 - Montar App principal
> Capitulo 8 de 11

## 1. Objetivo do passo
Conectar todos os componentes e o hook para formar a versao funcional da aplicacao.

## 2. O que sera aprendido
- Por que o App deve ser um orquestrador, nao um deposito de logica.
- Como conectar dados e acoes entre hook e componentes.

## 3. Codigo necessario
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

## 4. Explicacao linha a linha
- Pense no App como um maestro: ele coordena, mas nao toca todos os instrumentos.
- useTasks entrega estado e funcoes prontas.
- TaskInput recebe addTask para incluir novas tarefas.
- task-stats mostra os contadores calculados no hook.
- TaskList recebe tarefas e as funcoes de acao.
- Assim, cada parte tem responsabilidade clara.

## 5. O que o aluno construiu
A primeira versao completa da To-Do App, conectando interface, logica e contadores.

## 6. Dicas
- Mantenha o App como orquestrador: ele conecta pecas, nao concentra regras.
- Leia o retorno do hook como uma API local da feature.

## 7. Erros comuns
- Colocar logica de negocio extra dentro do App.
- Passar props com nomes diferentes dos esperados nos componentes.

## 8. Checkpoints de aprendizado
- Consegue mapear quem fornece e quem consome cada prop.
- Contadores e acoes funcionam juntos na tela principal.

## 9. Resumo do capitulo
Voce integrou componentes e hook em uma tela completa e funcional.

[Voltar ao inicio](../README.md)


