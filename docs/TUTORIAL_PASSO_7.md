[Voltar ao inicio](../README.md)

# Tutorial Passo 7 - Componente de lista

## Objetivo do passo
Renderizar todas as tarefas de forma organizada e tratar o estado de lista vazia.

## O que sera aprendido
- Por que separar a lista do item simplifica o App.
- Como usar map com key e condicao de renderizacao.

## Codigo necessario
### src/components/TaskList.tsx
```tsx
import type { Task } from '../types/Task';
import { TaskItem } from './TaskItem';

interface TaskListProps {
  tasks: Task[];
  onToggleTask: (taskId: string) => void;
  onRemoveTask: (taskId: string) => void;
}

export const TaskList = ({ tasks, onToggleTask, onRemoveTask }: TaskListProps) => {
  if (tasks.length === 0) {
    return <p className="empty-list">Nenhuma tarefa cadastrada ainda.</p>;
  }

  return (
    <ul className="task-list">
      {tasks.map((task) => (
        <TaskItem key={task.id} task={task} onToggle={onToggleTask} onRemove={onRemoveTask} />
      ))}
    </ul>
  );
};
```

## Explicacao linha a linha
- TaskListProps tipa os dados e funcoes que entram no componente.
- tasks.length === 0 trata o caso sem tarefas.
- A ul sera exibida somente quando houver itens.
- map percorre o array tasks e gera um TaskItem por tarefa.
- key usa task.id para o React rastrear cada item da lista.
- onToggleTask e onRemoveTask sao repassados para cada TaskItem.

## O que o aluno construiu
Um componente de listagem completo, com estado vazio e renderizacao dinamica dos itens.

[Voltar ao inicio](../README.md)

