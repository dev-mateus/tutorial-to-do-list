# To-Do App com React + Vite + TypeScript

## Introdução
Este repositório é um tutorial guiado para construir uma aplicação front-end de Lista de Tarefas (To-Do App), saindo do nível básico e evoluindo para um nível iniciante-intermediário.

A proposta é aprender conceitos fundamentais de `React` com `TypeScript` em um projeto pequeno, realista e organizado, usando apenas `CSS` puro.

## Objetivo do projeto
Ensinar, passo a passo, como criar uma aplicação web aplicando boas práticas de front-end:
- Componentes funcionais e reutilizáveis
- `Hooks` para estado e efeitos
- Tipagem com `TypeScript`
- Separação entre lógica, interface e estilos

## Resumo do que o projeto faz
A aplicação final permite:
- Adicionar novas tarefas
- Exibir lista de tarefas
- Marcar tarefas como concluídas
- Remover tarefas
- Exibir contadores de total, concluídas e pendentes
- Salvar os dados no `localStorage` para manter as tarefas após recarregar a página

## Para quem é este material
- Quem está começando em `React`
- Quem quer praticar `TypeScript` na prática
- Quem quer aprender organização de projeto sem usar bibliotecas extras de estilo

## Stack
- React
- Vite
- TypeScript
- CSS puro

## Pré-requisitos recomendados
- Saber o básico de HTML e CSS
- Saber o básico de JavaScript (variáveis, funções e arrays)
- Ter `Node.js` instalado

## Como estudar este tutorial
O README funciona como esqueleto e guia principal.

Cada etapa detalhada está em arquivos separados na pasta `docs/`, seguindo o mesmo padrão didático:
- Objetivo do passo
- O que será aprendido
- Código necessário
- Explicação linha a linha
- O que o aluno construiu

Cada tutorial também inclui:
- Dicas
- Erros comuns
- Checkpoints de aprendizado
- Resumo do capítulo

## Índice do passo a passo
1. [Passo 1 - Criar base do projeto](docs/TUTORIAL_PASSO_1.md)
2. [Passo 2 - Ponto de entrada](docs/TUTORIAL_PASSO_2.md)
3. [Passo 3 - Modelo de dados](docs/TUTORIAL_PASSO_3.md)
4. [Passo 4 - Hook com regras de negócio](docs/TUTORIAL_PASSO_4.md)
5. [Passo 5 - Componente de entrada](docs/TUTORIAL_PASSO_5.md)
6. [Passo 6 - Componente de item](docs/TUTORIAL_PASSO_6.md)
7. [Passo 7 - Componente de lista](docs/TUTORIAL_PASSO_7.md)
8. [Passo 8 - Montar App principal](docs/TUTORIAL_PASSO_8.md)
9. [Passo 9 - Estilização com CSS puro](docs/TUTORIAL_PASSO_9.md)
10. [Passo 10 - Tipos do Vite](docs/TUTORIAL_PASSO_10.md)
11. [Passo 11 - Rodar e validar](docs/TUTORIAL_PASSO_11.md)

## Checklist de execução por passo
Para cada tutorial, siga sempre esta ordem:
1. Ler o passo completo.
2. Aplicar o código do passo.
3. Rodar e validar localmente.

### Bloco de Comando — Validar localmente
> Tipo: `Comando`  
> Ação: `Executar` na pasta raiz do projeto.

```bash
npm run dev
```

4. Confirmar que não há erros.
5. Avançar para o próximo passo.

## Regra de progresso
Não avance com dúvidas acumuladas.

Se um passo não estiver claro:
1. Releia o objetivo do passo
2. Revise a explicação linha a linha
3. Use os checkpoints para validar entendimento
4. Só depois avance

## Resultado esperado ao final
Ao concluir os 11 passos, você terá uma To-Do App completa, tipada com TypeScript, organizada por responsabilidade e pronta para servir como base de estudos e evolução.

Você também terá praticado um fluxo profissional básico de desenvolvimento:
- Implementar por etapas
- Validar cada etapa
- Corrigir erros no caminho
- Finalizar com os comandos abaixo para gerar e validar a versão de produção

### Bloco de Comando — Validar produção
> Tipo: `Comando`  
> Ação: `Executar` na pasta raiz do projeto.

```bash
npm run build
npm run preview
```
