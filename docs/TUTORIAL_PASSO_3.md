[Voltar ao inicio](../README.md)

# Tutorial Passo 3 - Modelo de dados
> Capítulo 3 de 11

## 1. Objetivo do passo
Definir o formato padrão de uma tarefa para todo o projeto.

## 2. O que será aprendido
- Por que tipar dados evita erros e confusão.
- Como criar um contrato de dados com TypeScript.

## 3. Código necessário
### 📄 Criar — `src/types/Task.ts`
> Caminho completo: `to-do-app/src/types/Task.ts`.  
> **Ação:** a pasta `src/types/` foi criada no Passo 1. Crie o arquivo `Task.ts` dentro dela.
```ts
export interface Task {
  id: string;
  title: string;
  completed: boolean;
}
```

## 4. Explicação linha a linha
- export disponibiliza a interface para importação em outros arquivos do projeto.
- interface Task define o formato obrigatório de uma tarefa no TypeScript.
- id: string representa o identificador único de cada item.
- title: string representa o texto exibido para a tarefa.
- completed: boolean representa o estado da tarefa, concluída ou pendente.

## 5. O que o aluno construiu
Um contrato único para tarefas, deixando a comunicação entre componentes mais segura e previsível.

## 6. Dicas
- Use nomes claros nos campos do tipo para facilitar leitura.
- Mantenha o tipo em arquivo separado para reutilizar em vários componentes.

## 7. Erros comuns
- Definir campos com tipo incorreto, como completed em string.
- Criar tipos diferentes para a mesma entidade em arquivos distintos.

## 8. Checkpoints de aprendizado
- Rode npm run dev e verifique no navegador se a tela continua exibindo Projeto To-Do iniciado, sem mudanças visuais neste passo.
- Confirme no editor que a interface Task foi criada sem erro de sintaxe e que o projeto continua compilando normalmente.

## 9. Resumo do capítulo
Você criou o contrato de dados da tarefa e padronizou a estrutura usada no projeto.

[Voltar ao inicio](../README.md)


