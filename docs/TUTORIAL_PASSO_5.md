[Voltar ao inicio](../README.md)

# Tutorial Passo 5 - Componente de entrada
> Capitulo 5 de 11

## 1. Objetivo do passo
Criar o formulario que recebe o texto da nova tarefa.

## 2. O que sera aprendido
- Por que separar a entrada de dados em um componente proprio.
- Como funciona input controlado no React.
- Como tratar submit sem recarregar a pagina.

## 3. Codigo necessario
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

## 4. Explicacao linha a linha
- Pense nesse componente como a porta de entrada das tarefas.
- useState guarda o que o usuario digita.
- value + onChange deixam o input controlado pelo React.
- handleSubmit intercepta o envio para nao recarregar a pagina.
- onAddTask envia o texto para a logica principal.
- setTaskTitle limpa o campo para facilitar a proxima entrada.

## 5. O que o aluno construiu
Um formulario tipado, reutilizavel e pronto para adicionar tarefas.

## 6. Dicas
- Trate o submit com preventDefault para evitar recarga da pagina.
- Limpe o input apos adicionar para melhorar a experiencia do usuario.

## 7. Erros comuns
- Esquecer de controlar o valor do input com useState.
- Nao tipar corretamente o evento do formulario.

## 8. Checkpoints de aprendizado
- O input atualiza o estado enquanto voce digita.
- Ao enviar, onAddTask e chamado e o campo limpa.

## 9. Resumo do capitulo
Voce criou uma entrada de dados controlada, pronta para alimentar a lista de tarefas.

[Voltar ao inicio](../README.md)


