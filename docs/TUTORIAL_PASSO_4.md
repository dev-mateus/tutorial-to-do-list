[Voltar ao inicio](../README.md)

# Tutorial Passo 4 - Hook com regras de negocio

## Objetivo do passo
Criar um hook para concentrar estado, acoes e persistencia das tarefas.

## O que sera aprendido
- Por que separar logica de negocio do componente App.
- Como usar useState, useEffect e useMemo em conjunto.

## Codigo necessario
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

## Explicacao linha a linha
- useState guarda a lista de tarefas em memoria.
- A inicializacao do useState ja tenta carregar dados do localStorage.
- O bloco try/catch evita quebrar a aplicacao se o JSON estiver invalido.
- useEffect salva no localStorage sempre que tasks muda.
- addTask normaliza texto e impede tarefas vazias.
- toggleTask altera apenas a tarefa clicada, mantendo as outras.
- removeTask remove a tarefa pelo id.
- useMemo calcula estatisticas com base na lista atual.
- O retorno do hook entrega dados e funcoes para o App.

## O que o aluno construiu
A camada central de logica da To-Do App, com estado organizado e persistencia automatica.

[Voltar ao inicio](../README.md)

