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
- Este passo revisa um arquivo já criado para garantir que o ambiente TypeScript continue configurado corretamente.
- A diretiva /// <reference types="vite/client" /> adiciona ao projeto os tipos fornecidos pelo Vite.
- Esses tipos permitem que imports de arquivos como CSS sejam reconhecidos sem erro pelo TypeScript.
- Manter esse conteúdo correto evita falhas de tipagem no editor, no dev server e no build.

## 5. O que o aluno construiu
Uma base de tipagem mais estável, com melhor suporte do editor e do compilador.

## 6. Dicas
- Use este arquivo mesmo quando parecer pequeno, ele evita erros chatos de tipo.
- Deixe o arquivo na raiz de src para o TypeScript encontrar automaticamente.

## 7. Erros comuns
- Criar vite-env.d.ts fora de src sem ajustar configuração.
- Apagar a referência vite/client e voltar a ter erro de import de CSS.

## 8. Checkpoints de aprendizado
- Rode npm run dev e verifique no navegador se a aplicação continua abrindo normalmente após revisar o arquivo.
- Confirme no editor que não existe erro de tipagem nos imports de CSS de src/main.tsx e src/App.tsx.

## 9. Resumo do capítulo
Você reforçou a estabilidade de tipagem do ambiente Vite no projeto.

[Voltar ao inicio](../README.md)


