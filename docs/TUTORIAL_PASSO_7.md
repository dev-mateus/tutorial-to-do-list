[Voltar ao inicio](../README.md)

# Tutorial Passo 7 - Componente de lista
> Capítulo 7 de 11

## 1. Objetivo do passo
Montar o componente que exibe todas as tarefas e trata o caso de lista vazia.

## 2. O que será aprendido
- Por que a lista deve ficar separada do App.
- Como renderizar vários itens com map.
- Como mostrar uma mensagem quando não houver tarefas.

## 3. Código necessário
### 📄 Criar — `src/components/TaskList.tsx`
> Caminho completo: `to-do-app/src/components/TaskList.tsx`.  
> **Ação:** a pasta `src/components/` já existe dos Passos 5 e 6. Crie o arquivo `TaskList.tsx` dentro dela.
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

## 4. Explicação linha a linha
- Analogia: TaskList é a prancheta que organiza todos os TaskItem.
- tasks recebe o conjunto de tarefas.
- O if evita tela vazia sem explicação para o usuário.
- map percorre a lista e cria um TaskItem para cada tarefa.
- key ajuda o React a identificar cada item de forma única.
- As funções de concluir e remover são repassadas para cada item.

## 5. O que o aluno construiu
Uma lista dinâmica e reutilizável, com boa experiência mesmo quando não há tarefas.

## 6. Dicas
- Sempre trate o estado de lista vazia para não deixar tela sem contexto.
- Use key estável para cada item renderizado.

## 7. Erros comuns
- Usar key com índice do array em listas que mudam.
- Renderizar TaskItem sem repassar callbacks necessários.

## 8. Checkpoints de aprendizado
- Mensagem de vazio aparece quando não há tarefas.
- Com tarefas, a lista renderiza todos os itens corretamente.

## 9. Resumo do capítulo
Você organizou a renderização da lista com boa experiência para cenários vazios e preenchidos.

[Voltar ao inicio](../README.md)


