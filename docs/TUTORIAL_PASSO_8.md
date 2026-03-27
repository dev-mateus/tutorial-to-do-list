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
- Os imports carregam o CSS da tela principal, os componentes de interface e o hook com as regras da feature.
- useTasks() retorna o estado tasks, os contadores stats e as funções addTask, toggleTask e removeTask.
- main.app-shell e section.todo-card organizam a estrutura principal da página.
- O header exibe o título e o texto descritivo da aplicação.
- TaskInput recebe addTask para encaminhar novas tarefas ao hook.
- section.task-stats exibe os valores derivados de stats.total, stats.completed e stats.pending.
- TaskList recebe a lista atual e as funções necessárias para marcar ou remover tarefas.
- export default App mantém o componente disponível para renderização em `src/main.tsx`.

## 5. O que o aluno construiu
A primeira versão completa da To-Do App, conectando interface, lógica e contadores.

## 6. Dicas
- Mantenha o App como orquestrador: ele conecta peças, não concentra regras.
- Leia o retorno do hook como uma API local da feature.

## 7. Erros comuns
- Colocar lógica de negócio extra dentro do App.
- Passar props com nomes diferentes dos esperados nos componentes.

## 8. Checkpoints de aprendizado
- Execute o comando abaixo e verifique no navegador se a interface completa da lista de tarefas aparece, com título, campo de entrada, contadores e área da lista.

```bash
npm run dev
```

- Adicione uma tarefa, marque como concluída e remova o item para confirmar que o hook e os componentes estão integrados corretamente.

## 9. Resumo do capítulo
Você integrou componentes e hook em uma tela completa e funcional.

[Voltar ao inicio](../README.md)


