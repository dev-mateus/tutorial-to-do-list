[Voltar ao inicio](../README.md)

# Tutorial Passo 10 - Tipos do ambiente Vite

## Objetivo do passo
Garantir que TypeScript reconheca corretamente recursos do Vite, como imports de CSS.

## O que sera aprendido
- Por que arquivos de declaracao evitam erros de tipagem.
- Como habilitar tipos do cliente Vite no projeto.

## Observacao de sequencia didatica
Se voce ja criou este arquivo no Passo 1, aqui voce apenas valida e entende melhor o motivo dele existir.

Se ainda nao criou, este e o momento de adicionar o arquivo para evitar erros de import de CSS.

## Codigo necessario
### src/vite-env.d.ts
```ts
/// <reference types="vite/client" />
```

## Explicacao linha a linha
- A diretiva triple-slash adiciona tipos do pacote vite/client.
- Esses tipos incluem suporte para importacao de recursos como CSS.
- Com isso, o editor e o build entendem melhor o ambiente do projeto.

## O que o aluno construiu
Uma configuracao de tipos estavel e consciente, entendendo quando e por que usar vite-env.d.ts.

[Voltar ao inicio](../README.md)

