[Voltar ao inicio](../README.md)

# Tutorial Passo 5 - Componente de entrada

## Objetivo do passo
Criar o formulario para digitar e adicionar novas tarefas.

## O que sera aprendido
- Por que separar entrada de dados em componente proprio.
- Como controlar input e envio de formulario no React.

## Codigo necessario
### src/components/TaskInput.tsx
```tsx
import { FormEvent, useState } from 'react';

interface TaskInputProps {
  onAddTask: (title: string) => void;
}

export const TaskInput = ({ onAddTask }: TaskInputProps) => {
  const [taskTitle, setTaskTitle] = useState<string>('');

  const handleSubmit = (event: FormEvent<HTMLFormElement>) => {
    event.preventDefault();
    onAddTask(taskTitle);
    setTaskTitle('');
  };

  return (
    <form className="task-input" onSubmit={handleSubmit}>
      <input
        type="text"
        value={taskTitle}
        onChange={(event) => setTaskTitle(event.target.value)}
        placeholder="Digite uma tarefa..."
        aria-label="Nova tarefa"
      />
      <button type="submit">Adicionar</button>
    </form>
  );
};
```

## Explicacao linha a linha
- A interface TaskInputProps define o contrato de props do componente.
- onAddTask sera recebido do componente pai.
- useState cria estado local para controlar o texto digitado.
- handleSubmit evita recarregar a pagina com preventDefault.
- onAddTask envia o texto atual para a logica principal.
- setTaskTitle limpa o campo apos enviar.
- value e onChange tornam o input controlado.

## O que o aluno construiu
Um formulario reutilizavel e tipado para cadastrar tarefas na aplicacao.

[Voltar ao inicio](../README.md)

