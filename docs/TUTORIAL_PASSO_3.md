[Voltar ao inicio](../README.md)

# Tutorial Passo 3 - Modelo de dados
> Capitulo 3 de 11

## 1. Objetivo do passo
Definir o formato padrao de uma tarefa para todo o projeto.

## 2. O que sera aprendido
- Por que tipar dados evita erros e confusao.
- Como criar um contrato de dados com TypeScript.

## 3. Codigo necessario
### src/types/Task.ts
```ts
export interface Task {
  id: string;
  title: string;
  completed: boolean;
}
```

## 4. Explicacao linha a linha
- Pense na interface como uma ficha de cadastro: toda tarefa precisa seguir esse formato.
- id: identificador unico da tarefa.
- title: texto da tarefa.
- completed: informa se a tarefa ja foi concluida.
- export permite reutilizar esse tipo em varios arquivos.

## 5. O que o aluno construiu
Um contrato unico para tarefas, deixando a comunicacao entre componentes mais segura e previsivel.

## 6. Dicas
- Use nomes claros nos campos do tipo para facilitar leitura.
- Mantenha o tipo em arquivo separado para reutilizar em varios componentes.

## 7. Erros comuns
- Definir campos com tipo incorreto, como completed em string.
- Criar tipos diferentes para a mesma entidade em arquivos distintos.

## 8. Checkpoints de aprendizado
- Consegue explicar cada campo de Task.
- Entende por que tipagem reduz erros na passagem de props.

## 9. Resumo do capitulo
Voce criou o contrato de dados da tarefa e padronizou a estrutura usada no projeto.

[Voltar ao inicio](../README.md)


