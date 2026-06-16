---
id: grimorio_vestibular.produto.fluxo_operacional
type: operational_flow
status: v0
created_at: 2026-06-15
updated_at: 2026-06-15
backend_ready: true
human_review_required: false
---

# Fluxo Operacional

Este arquivo descreve o fluxo operacional do GRIMORIO_VESTIBULAR. Ele mostra o caminho ideal, loops principais e pontos de decisão.

## Fluxo macro

```text
1. Entrada de objetivo
2. Mapeamento de prova/conteúdo
3. Planejamento com participação da estudante
4. Sessão de estudo
5. Prática orientada
6. Correção imediata
7. Reforço focado nos erros
8. Revisão mista
9. Registro estruturado
10. Commit no repositório
11. Auditoria automática
12. Promoção para arquivos vivos
13. Ajuste do próximo plano
```

## Entrada de objetivo

A estudante informa vestibulares, faculdades, prova escolar, conteúdo em dificuldade, rotina, prazo ou necessidade de revisão.

## Mapeamento

O sistema identifica conteúdos cobrados, temas relevantes, exemplos de questões, provas anteriores, gabaritos ou conteúdos escolares informados.

## Planejamento

O plano é criado com a estudante. Ele deve ser flexível e permitir ajustes por desempenho, repetição excessiva, prazo, lacuna, cansaço ou prioridade.

## Sessão de estudo

Fluxo preferencial quando o objetivo for diagnóstico e consolidação:

```text
explicação curta -> bateria objetiva -> correção imediata -> reforço dos erros -> nova bateria -> revisão mista -> save
```

## Registro e commit

Registros de chat vão para:

```text
registros/chats/*.md
```

Saves consolidados de sessão vão para:

```text
estudantes/gabi/sessoes/*.md
```

Todos os commits devem ocorrer no repositório:

```text
halrrik/grimorio_vestibular
```

## Auditoria

A auditoria verifica destino, schema, evidências, inferências, conflitos, lacunas, revisões e atualizações candidatas.

## Promoção para arquivos vivos

Quando um registro é confiável, ele deve atualizar arquivos vivos em `estado/`:

- progresso;
- plano atual;
- metodologia;
- perfil de aprendizagem;
- revisões;
- riscos.

## Loops

### Loop de aprendizagem

```text
estudar -> praticar -> corrigir -> reforçar -> revisar -> registrar -> ajustar
```

### Loop de planejamento

```text
objetivo -> plano -> execução -> evidência -> ajuste -> novo plano
```

### Loop de diagnóstico

```text
erro -> causa provável -> intervenção -> novo teste
```

### Loop de revisão espaçada

```text
erro ou acerto recente -> revisão 3-5 dias -> revisão 10-14 dias -> reclassificação
```

### Loop de proteção

```text
risco humano -> reduzir pressão -> mudar abordagem -> preservar aprendizado
```
