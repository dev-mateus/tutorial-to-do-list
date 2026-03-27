[Voltar ao inicio](../README.md)

# Tutorial Passo 5 - Componente de entrada
> Capítulo 5 de 11

## 1. Objetivo do passo
Criar o formulário que recebe o texto da nova tarefa.

## 2. O que será aprendido
- Por que separar a entrada de dados em um componente próprio.
- Como funciona `input` controlado no `React`.
- Como tratar `submit` sem recarregar a página.

## 3. Código necessário
### Bloco de Arquivo — Criar `src/components/TaskInput.tsx`
> Tipo: `Arquivo`  
> Ação: `Criar`  
> Caminho completo: `to-do-app/src/components/TaskInput.tsx`.
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
- `FormEvent` e `useState` são importados para tipar o envio do formulário e controlar o valor do campo.
- `TaskInputProps` define que o componente precisa receber uma função `onAddTask`.
- `useState<string>('')` cria o estado `taskTitle` com valor inicial vazio.
- `handleSubmit` recebe o evento do formulário, chama `preventDefault` e impede o recarregamento da página.
- `onAddTask(taskTitle)` envia o texto digitado para o componente pai.
- `setTaskTitle('')` limpa o `input` após o envio.
- `value` liga o `input` ao estado atual e `onChange` atualiza esse estado a cada digitação.
- `placeholder` e `aria-label` melhoram a usabilidade e a acessibilidade do campo.

## 5. O que o aluno construiu
Um formulário tipado, reutilizável e pronto para adicionar tarefas.

## 6. Dicas
- Trate o `submit` com `preventDefault` para evitar recarga da página.
- Limpe o `input` após adicionar para melhorar a experiência do usuário.

## 7. Erros comuns
- Esquecer de controlar o valor do `input` com `useState`.
- Não tipar corretamente o evento do formulário.

## 8. Checkpoints de aprendizado
- Execute o comando abaixo e verifique no navegador se a tela continua igual ao passo anterior, porque TaskInput foi criado mas ainda não foi renderizado pelo App.

```bash
npm run dev
```

- Confirme no editor que o componente aceita a prop onAddTask sem erro de tipagem e que salvar o arquivo não quebra a compilação.

## 9. Resumo do capítulo
Você criou uma entrada de dados controlada, pronta para alimentar a lista de tarefas.

[Voltar ao inicio](../README.md)


