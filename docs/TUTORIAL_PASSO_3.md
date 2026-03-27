[Voltar ao inicio](../README.md)

# Tutorial Passo 3 - Modelo de dados

## Objetivo do passo
Definir o formato padrao de uma tarefa para evitar inconsistencias no projeto.

## O que sera aprendido
- Por que tipar dados desde o inicio facilita manutencao.
- Como criar um contrato de dados reutilizavel no TypeScript.

## Codigo necessario
### src/types/Task.ts
```ts
export interface Task {
  id: string;
  title: string;
  completed: boolean;
}
```

## Explicacao linha a linha
- export permite usar o tipo Task em varios arquivos.
- interface cria um contrato que descreve a estrutura obrigatoria do objeto.
- id identifica cada tarefa de forma unica.
- title guarda o texto da tarefa.
- completed informa se a tarefa esta concluida ou nao.

## O que o aluno construiu
Um modelo de dados unico e padronizado para toda a funcionalidade de tarefas.

[Voltar ao inicio](../README.md)

