[Voltar ao inicio](../README.md)

# Tutorial Passo 7 - Componente de lista
> Capitulo 7 de 11

## 1. Objetivo do passo
Montar o componente que exibe todas as tarefas e trata o caso de lista vazia.

## 2. O que sera aprendido
- Por que a lista deve ficar separada do App.
- Como renderizar varios itens com map.
- Como mostrar uma mensagem quando nao houver tarefas.

## 3. Codigo necessario
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

## 4. Explicacao linha a linha
- Analogia: TaskList e a prancheta que organiza todos os TaskItem.
- tasks recebe o conjunto de tarefas.
- O if evita tela vazia sem explicacao para o usuario.
- map percorre a lista e cria um TaskItem para cada tarefa.
- key ajuda o React a identificar cada item de forma unica.
- As funcoes de concluir e remover sao repassadas para cada item.

## 5. O que o aluno construiu
Uma lista dinamica e reutilizavel, com boa experiencia mesmo quando nao ha tarefas.

## 6. Dicas
- Sempre trate o estado de lista vazia para nao deixar tela sem contexto.
- Use key estavel para cada item renderizado.

## 7. Erros comuns
- Usar key com indice do array em listas que mudam.
- Renderizar TaskItem sem repassar callbacks necessarios.

## 8. Checkpoints de aprendizado
- Mensagem de vazio aparece quando nao ha tarefas.
- Com tarefas, a lista renderiza todos os itens corretamente.

## 9. Resumo do capitulo
Voce organizou a renderizacao da lista com boa experiencia para cenarios vazio e preenchido.

[Voltar ao inicio](../README.md)


