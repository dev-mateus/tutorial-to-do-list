[Voltar ao inicio](../README.md)

# Tutorial Passo 4 - Hook com regras de negócio
> Capítulo 4 de 11

## 1. Objetivo do passo
Criar o `hook` `useTasks` para guardar estado, regras de negócio e persistência.

## 2. O que será aprendido
- Por que separar lógica da tela deixa o projeto mais limpo.
- Como usar `useState`, `useEffect` e `useMemo` juntos.
- Como salvar e recuperar dados no `localStorage`.

## 3. Código necessário
### Bloco de Arquivo — Criar `src/hooks/useTasks.ts`
> Tipo: `Arquivo`  
> Ação: `Criar`  
> Caminho completo: `to-do-app/src/hooks/useTasks.ts`.
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
- Os `imports` carregam os `hooks` do `React` e o tipo `Task` usado para tipar estado e funções.
- `STORAGE_KEY` define a chave fixa usada para salvar e recuperar as tarefas no `localStorage`.
- `createTask` cria um objeto `Task` padronizado com `id` único, título recebido e `completed` iniciado como `false`.
- `useState<Task[]>(() => ...)` cria o estado `tasks` e usa uma função inicializadora para ler o `localStorage` apenas na primeira renderização.
- `localStorage.getItem(STORAGE_KEY)` busca tarefas salvas anteriormente.
- O bloco `if` retorna uma lista vazia quando ainda não existe dado salvo.
- `try/catch` tenta converter o `JSON` salvo em array de tarefas e evita quebrar a aplicação caso o conteúdo esteja inválido.
- `useEffect` sincroniza o estado `tasks` com o `localStorage` sempre que a lista muda.
- `addTask` normaliza o texto com `trim`, ignora entrada vazia e adiciona a nova tarefa no início da lista.
- `toggleTask` percorre a lista e inverte o campo `completed` apenas da tarefa com o `id` recebido.
- `removeTask` filtra a lista e remove a tarefa correspondente ao `id` informado.
- `useMemo` calcula `total`, `completed` e `pending` a partir do estado atual, recalculando apenas quando `tasks` muda.
- O retorno final expõe estado e ações para os componentes que consumirem o `hook`.

## 5. O que o aluno construiu
Um motor completo da feature To-Do, com regras claras e persistência automática.

## 6. Dicas
- Separe lógica de negócio da interface sempre que possível.
- Teste os casos de adicionar, concluir e remover antes de codar.

## 7. Erros comuns
- Salvar no `localStorage` fora do `useEffect`, gerando código confuso.
- Esquecer de tratar `JSON` inválido no carregamento inicial.

## 8. Checkpoints de aprendizado
- Execute o comando abaixo e verifique no navegador se a tela ainda mostra Projeto To-Do iniciado, porque o `hook` foi criado mas ainda não está conectado ao `App`.

```bash
npm run dev
```

- Confirme no editor que o arquivo `src/hooks/useTasks.ts` não apresenta erro e que o projeto continua compilando sem avisos de importação ou tipagem.

## 9. Resumo do capítulo
Você construiu o motor da aplicação, com estado, regras e persistência local.

[Voltar ao inicio](../README.md)


