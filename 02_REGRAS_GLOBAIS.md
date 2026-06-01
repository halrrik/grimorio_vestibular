# 02 — Regras Globais

## Hipótese primeiro

Todo Grimório novo ou evolução de Grimório começa por uma hipótese.

O desenvolvimento deve buscar o resultado esperado da hipótese atual. Ideias fora do escopo devem ser registradas em `futuro/00_FISHBOWL.md`.

## Passo a passo

Não expandir escopo sem aprovação explícita.

Não transformar MVP1 em MVP2 ou MVP3.

## Ordem de leitura obrigatória

Todo Grimório deve usar arquivos numerados com o padrão `##_NOME_DO_ARQUIVO.md`.

A numeração serve para:

- indicar prioridade de leitura;
- facilitar navegação humana;
- orientar a IA sobre o que deve ser lido primeiro;
- manter consistência entre diferentes Grimórios.

Arquivos essenciais devem começar por:

1. `00_LER_PRIMEIRO.md`
2. `01_INDICE_GERAL.md`
3. `02_REGRAS_GLOBAIS.md`
4. `03_HIPOTESE.md`
5. `04_PATCH_LOG.md`

## Métricas

Não inventar fórmula definitiva sem validação.

No MVP1, a absorção deve usar escala de 0 a 100.

Existem dois tipos:

- absorção estimada: leitura qualitativa do estudo;
- absorção medida: resultado obtido após quiz diagnóstico.

## Commit com aprovação

Quando houver acesso de escrita ao repositório, o Grimório pode preparar e executar commits.

Antes de commitar, deve mostrar:

- arquivos criados;
- arquivos alterados;
- resumo da mudança;
- mensagem sugerida de commit.

Só pode commitar após aprovação explícita.

## Patch Log obrigatório

Toda mudança relevante deve atualizar `04_PATCH_LOG.md`.

Mudanças relevantes incluem:

- alteração de fluxo;
- alteração de comando;
- mudança de métrica;
- mudança de estrutura;
- nova hipótese;
- decisão de escopo;
- correção de comportamento do Grimório.
