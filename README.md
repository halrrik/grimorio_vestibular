# Grimório Vestibular

Projeto-base para criar uma versão do Grimório focada em preparação para vestibulares brasileiros, com ênfase em ENEM, Fuvest, Unicamp, Unesp, Uerj e outros processos seletivos.

Este repositório nasce como uma estrutura inicial para organizar prompts, fontes, trilhas de estudo, questões, simulados, flashcards, materiais por disciplina e futuramente um agente dedicado.

## Objetivo

Criar um sistema de estudo guiado por IA que funcione com a lógica do Grimório: diagnosticar, organizar, priorizar, ensinar, treinar, revisar e medir evolução.

## Estrutura inicial

```txt
grimorio_vestibular/
├─ README.md
├─ .gitignore
├─ LICENSE
├─ docs/
├─ prompts/
├─ fonte/
├─ materias/
├─ simulados/
├─ questoes/
├─ flashcards/
├─ trilhas/
├─ scripts/
└─ agente/
```

## Fonte principal

O arquivo `docs/MEGA_PROMPT_GRIMORIO.md` deve ser tratado como a fonte principal de comportamento do projeto. Sempre que um agente, assistente ou fluxo automatizado for criado, ele deve consultar e respeitar esse arquivo.

## Status

Estrutura inicial. Ainda sem implementação final de agente.
