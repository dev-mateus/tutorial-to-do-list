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
- O arquivo importa o tipo Task para tipar a lista recebida e importa TaskItem para renderizar cada elemento.
- TaskListProps define que o componente recebe o array tasks e duas funções para alterar ou remover uma tarefa.
- if (tasks.length === 0) faz um retorno antecipado quando não existem itens.
- A mensagem Nenhuma tarefa cadastrada ainda. trata explicitamente o estado vazio da interface.
- tasks.map(...) percorre o array e renderiza um TaskItem para cada objeto Task.
- key={task.id} fornece uma chave estável para o React identificar corretamente cada item.
- onToggleTask e onRemoveTask são repassadas para cada TaskItem com os nomes esperados pelo componente filho.

## 5. O que o aluno construiu
Uma lista dinâmica e reutilizável, com boa experiência mesmo quando não há tarefas.

## 6. Dicas
- Sempre trate o estado de lista vazia para não deixar tela sem contexto.
- Use key estável para cada item renderizado.

## 7. Erros comuns
- Usar key com índice do array em listas que mudam.
- Renderizar TaskItem sem repassar callbacks necessários.

## 8. Checkpoints de aprendizado
- Execute o comando abaixo e verifique no navegador se a tela ainda não mudou visualmente, porque TaskList foi criado mas ainda será conectado no Passo 8.

```bash
npm run dev
```

- Confirme no editor que o componente aceita um array de tarefas e callbacks sem erro de tipagem.

## 9. Resumo do capítulo
Você organizou a renderização da lista com boa experiência para cenários vazios e preenchidos.

[Voltar ao inicio](../README.md)


