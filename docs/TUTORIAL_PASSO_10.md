[Voltar ao inicio](../README.md)

# Tutorial Passo 10 - Tipos do ambiente Vite
> Capítulo 10 de 11

## 1. Objetivo do passo
Garantir que o TypeScript entenda o ambiente do Vite sem gerar erros de import.

## 2. O que será aprendido
- O que é um arquivo de declaração de tipos.
- Por que esse arquivo evita erros de CSS importado no TypeScript.

## 3. Código necessário
### ✅ Verificar — `src/vite-env.d.ts`
> Caminho completo: `to-do-app/src/vite-env.d.ts`.  
> **Ação:** este arquivo foi criado no Passo 1. Confirme que o conteúdo está exatamente como abaixo.
```ts
/// <reference types="vite/client" />
```

## 4. Explicação linha a linha
- Se no Passo 1 você já criou esse arquivo, aqui o foco é entender o motivo.
- A linha triple-slash importa os tipos do cliente do Vite.
- Com isso, o TypeScript reconhece melhor recursos de front-end, como import de CSS.
- Resultado: menos erros de editor e mais previsibilidade no build.

## 5. O que o aluno construiu
Uma base de tipagem mais estável, com melhor suporte do editor e do compilador.

## 6. Dicas
- Use este arquivo mesmo quando parecer pequeno, ele evita erros chatos de tipo.
- Deixe o arquivo na raiz de src para o TypeScript encontrar automaticamente.

## 7. Erros comuns
- Criar vite-env.d.ts fora de src sem ajustar configuração.
- Apagar a referência vite/client e voltar a ter erro de import de CSS.

## 8. Checkpoints de aprendizado
- Projeto reconhece imports de CSS sem erro de tipagem.
- Você entende por que esse arquivo existe.

## 9. Resumo do capítulo
Você reforçou a estabilidade de tipagem do ambiente Vite no projeto.

[Voltar ao inicio](../README.md)


