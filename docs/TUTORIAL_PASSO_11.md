[Voltar ao inicio](../README.md)

# Tutorial Passo 11 - Rodar e validar o projeto
> Capítulo 11 de 11

## 1. Objetivo do passo
Executar a aplicação e confirmar que ela funciona em desenvolvimento e em produção.

## 2. O que será aprendido
- Por que validar em mais de um modo evita surpresas.
- Como usar os três comandos principais do fluxo `front-end`.

## 3. Código necessário
### Bloco de Comando — Validar desenvolvimento e produção
> Tipo: `Comando`  
> Ação: `Executar` na pasta raiz `to-do-app/`.
```bash
npm run dev
npm run build
npm run preview
```

## 4. Explicação linha a linha
- O comando abaixo inicia o `servidor de desenvolvimento` com recarga automática a cada alteração salva.

```bash
npm run dev
```

- O comando abaixo executa a checagem de tipos configurada pelo `TypeScript` e gera os arquivos finais de produção.

```bash
npm run build
```

- O comando abaixo sobe um servidor local usando o resultado gerado em `dist` para simular a aplicação publicada.

```bash
npm run preview
```

- Quando os três comandos funcionam sem erro, o projeto está consistente tanto para desenvolvimento quanto para entrega.

## 5. O que o aluno construiu
Um ciclo completo de validação do projeto, do desenvolvimento ao teste final de produção.

## 6. Dicas
- Sempre valide em `dev` e em `build` antes de considerar o projeto concluído.
- Use `preview` para simular melhor o comportamento de produção.

## 7. Erros comuns
- Testar apenas no `dev` e ignorar erros que aparecem no `build`.
- Parar no primeiro comando e não validar o fluxo completo.

## 8. Checkpoints de aprendizado
- Execute o comando abaixo e verifique no navegador se a aplicação abre e permite adicionar, concluir e remover tarefas normalmente.

```bash
npm run dev
```

- Depois execute os comandos abaixo e confirme no navegador que a versão de produção também abre com o mesmo comportamento da versão de desenvolvimento.

```bash
npm run build
npm run preview
```

## 9. Resumo do capítulo
Você concluiu o ciclo profissional básico: desenvolver, compilar e validar o projeto final.

[Voltar ao inicio](../README.md)


