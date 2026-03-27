[Voltar ao inicio](../README.md)

# Tutorial Passo 3 - Modelo de dados
> Capítulo 3 de 11

## 1. Objetivo do passo
Definir o formato padrão de uma tarefa para todo o projeto.

## 2. O que será aprendido
- Por que tipar dados evita erros e confusão.
- Como criar um contrato de dados com TypeScript.

## 3. Código necessário
### src/types/Task.ts
```ts
export interface Task {
  id: string;
  title: string;
  completed: boolean;
}
```

## 4. Explicação linha a linha
- Pense na interface como uma ficha de cadastro: toda tarefa precisa seguir esse formato.
- id: identificador único da tarefa.
- title: texto da tarefa.
- completed: informa se a tarefa já foi concluída.
- export permite reutilizar esse tipo em vários arquivos.

## 5. O que o aluno construiu
Um contrato único para tarefas, deixando a comunicação entre componentes mais segura e previsível.

## 6. Dicas
- Use nomes claros nos campos do tipo para facilitar leitura.
- Mantenha o tipo em arquivo separado para reutilizar em vários componentes.

## 7. Erros comuns
- Definir campos com tipo incorreto, como completed em string.
- Criar tipos diferentes para a mesma entidade em arquivos distintos.

## 8. Checkpoints de aprendizado
- Consegue explicar cada campo de Task.
- Entende por que tipagem reduz erros na passagem de props.

## 9. Resumo do capítulo
Você criou o contrato de dados da tarefa e padronizou a estrutura usada no projeto.

[Voltar ao inicio](../README.md)


