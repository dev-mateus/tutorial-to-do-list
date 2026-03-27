[Voltar ao inicio](../README.md)

# Tutorial Passo 5 - Componente de entrada
> Capítulo 5 de 11

## 1. Objetivo do passo
Criar o formulário que recebe o texto da nova tarefa.

## 2. O que será aprendido
- Por que separar a entrada de dados em um componente próprio.
- Como funciona input controlado no React.
- Como tratar submit sem recarregar a página.

## 3. Código necessário
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

## 4. Explicação linha a linha
- Pense nesse componente como a porta de entrada das tarefas.
- useState guarda o que o usuário digita.
- value + onChange deixam o input controlado pelo React.
- handleSubmit intercepta o envio para não recarregar a página.
- onAddTask envia o texto para a lógica principal.
- setTaskTitle limpa o campo para facilitar a próxima entrada.

## 5. O que o aluno construiu
Um formulário tipado, reutilizável e pronto para adicionar tarefas.

## 6. Dicas
- Trate o submit com preventDefault para evitar recarga da página.
- Limpe o input após adicionar para melhorar a experiência do usuário.

## 7. Erros comuns
- Esquecer de controlar o valor do input com useState.
- Não tipar corretamente o evento do formulário.

## 8. Checkpoints de aprendizado
- O input atualiza o estado enquanto você digita.
- Ao enviar, onAddTask é chamado e o campo é limpo.

## 9. Resumo do capítulo
Você criou uma entrada de dados controlada, pronta para alimentar a lista de tarefas.

[Voltar ao inicio](../README.md)


