[Voltar ao inicio](../README.md)

# Tutorial Passo 6 - Componente de item

## Objetivo do passo
Representar cada tarefa com acoes de concluir e remover.

## O que sera aprendido
- Por que quebrar lista em componentes menores melhora manutencao.
- Como aplicar eventos por item com props tipadas.

## Codigo necessario
### src/components/TaskItem.tsx
```tsx
import type { Task } from '../types/Task';

interface TaskItemProps {
  task: Task;
  onToggle: (taskId: string) => void;
  onRemove: (taskId: string) => void;
}

export const TaskItem = ({ task, onToggle, onRemove }: TaskItemProps) => {
  return (
    <li className={`task-item ${task.completed ? 'is-completed' : ''}`}>
      <label>
        <input
          type="checkbox"
          checked={task.completed}
          onChange={() => onToggle(task.id)}
          aria-label={`Marcar tarefa ${task.title}`}
        />
        <span>{task.title}</span>
      </label>

      <button type="button" onClick={() => onRemove(task.id)}>
        Remover
      </button>
    </li>
  );
};
```

## Explicacao linha a linha
- O tipo Task garante formato correto da tarefa recebida.
- onToggle e onRemove sao callbacks passados pelo componente pai.
- A classe is-completed e aplicada quando task.completed for true.
- O checkbox mostra o estado atual da tarefa.
- onChange do checkbox chama onToggle com o id certo.
- O botao chama onRemove com o id da tarefa.

## O que o aluno construiu
Um componente de item reutilizavel, com comportamento individual para cada tarefa.

[Voltar ao inicio](../README.md)

