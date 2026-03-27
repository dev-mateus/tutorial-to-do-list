[Voltar ao inicio](../README.md)

# Tutorial Passo 4 - Hook com regras de negócio
> Capítulo 4 de 11

## 1. Objetivo do passo
Criar o hook useTasks para guardar estado, regras de negócio e persistência.

## 2. O que será aprendido
- Por que separar lógica da tela deixa o projeto mais limpo.
- Como usar useState, useEffect e useMemo juntos.
- Como salvar e recuperar dados no localStorage.

## 3. Código necessário
### src/hooks/useTasks.ts
```ts
import { useEffect, useMemo, useState } from 'react';
import type { Task } from '../types/Task';

const STORAGE_KEY = 'todo-app:tasks';

const createTask = (title: string): Task => ({
  id: crypto.randomUUID(),
  title,
  completed: false,
});

export const useTasks = () => {
  const [tasks, setTasks] = useState<Task[]>(() => {
    const storedTasks = localStorage.getItem(STORAGE_KEY);

    if (!storedTasks) {
      return [];
    }

    try {
      return JSON.parse(storedTasks) as Task[];
    } catch {
      return [];
    }
  });

  useEffect(() => {
    localStorage.setItem(STORAGE_KEY, JSON.stringify(tasks));
  }, [tasks]);

  const addTask = (title: string) => {
    const normalizedTitle = title.trim();
    if (!normalizedTitle) return;
    setTasks((previousTasks) => [createTask(normalizedTitle), ...previousTasks]);
  };

  const toggleTask = (taskId: string) => {
    setTasks((previousTasks) =>
      previousTasks.map((task) =>
        task.id === taskId ? { ...task, completed: !task.completed } : task,
      ),
    );
  };

  const removeTask = (taskId: string) => {
    setTasks((previousTasks) => previousTasks.filter((task) => task.id !== taskId));
  };

  const stats = useMemo(() => {
    const total = tasks.length;
    const completed = tasks.filter((task) => task.completed).length;
    const pending = total - completed;
    return { total, completed, pending };
  }, [tasks]);

  return { tasks, stats, addTask, toggleTask, removeTask };
};
```

## 4. Explicação linha a linha
- Analogia: este hook é o motor da aplicação; os componentes serão a lataria.
- useState guarda a lista de tarefas em memória.
- A inicialização tenta carregar tarefas salvas no localStorage.
- try/catch protege o app se o dado salvo estiver inválido.
- useEffect salva novamente sempre que tasks muda.
- addTask cria nova tarefa e impede entrada vazia.
- toggleTask alterna concluída/pendente pelo id.
- removeTask exclui tarefa pelo id.
- useMemo calcula total, concluídas e pendentes de forma organizada.

## 5. O que o aluno construiu
Um motor completo da feature To-Do, com regras claras e persistência automática.

## 6. Dicas
- Separe lógica de negócio da interface sempre que possível.
- Teste os casos de adicionar, concluir e remover antes de codar.

## 7. Erros comuns
- Salvar no localStorage fora do useEffect, gerando código confuso.
- Esquecer de tratar JSON inválido no carregamento inicial.

## 8. Checkpoints de aprendizado
- Consegue explicar quando o useEffect é executado.
- Consegue descrever o papel de addTask, toggleTask e removeTask.

## 9. Resumo do capítulo
Você construiu o motor da aplicação, com estado, regras e persistência local.

[Voltar ao inicio](../README.md)


