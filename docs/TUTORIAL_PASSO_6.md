[Voltar ao inicio](../README.md)

# Tutorial Passo 6 - Componente de item
> Capítulo 6 de 11

## 1. Objetivo do passo
Criar o componente que representa uma tarefa individual.

## 2. O que será aprendido
- Por que dividir em componentes pequenos facilita manutenção.
- Como cada item pode ter suas próprias ações.

## 3. Código necessário
### 📄 Criar — `src/components/TaskItem.tsx`
> Caminho completo: `to-do-app/src/components/TaskItem.tsx`.  
> **Ação:** a pasta `src/components/` já existe do Passo 5. Crie o arquivo `TaskItem.tsx` dentro dela.
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

## 4. Explicação linha a linha
- Analogia: cada TaskItem é como uma linha de caderno da sua lista.
- task traz os dados daquela linha específica.
- onToggle muda o status da tarefa (feita ou pendente).
- onRemove remove a linha da lista.
- A classe is-completed permite estilo diferente para tarefa concluída.
- O checkbox reflete o estado atual da tarefa.

## 5. O que o aluno construiu
Um item de tarefa completo, com interação individual e visual adaptado ao status.

## 6. Dicas
- Use props tipadas para deixar as ações do item previsíveis.
- Aplique classe condicional para refletir visualmente o estado da tarefa.

## 7. Erros comuns
- Usar índice do array no lugar do id para operar itens.
- Esquecer de repassar o id para onToggle e onRemove.

## 8. Checkpoints de aprendizado
- Checkbox altera o status da tarefa correta.
- Botão remove o item certo da lista.

## 9. Resumo do capítulo
Você montou a unidade visual e funcional de cada tarefa individual.

[Voltar ao inicio](../README.md)


