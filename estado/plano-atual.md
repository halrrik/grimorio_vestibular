---
id: grimorio_vestibular.estado.plano_atual
type: current_study_plan
status: v1
student: gabi
created_at: 2026-06-15
updated_at: 2026-06-17
backend_ready: true
human_review_required: false
---

# Plano Atual

Este arquivo registra o plano operacional atual da estudante Gabi. Ele é flexível e deve ser atualizado conforme desempenho, lacunas, prazos e contexto.

## Objetivos ativos

```yaml
active_targets:
  - ENEM
  - FUVEST
  - VUNESP
```

## Uso prático imediato

O plano atual deve ajudar a decidir o que estudar hoje sem virar um calendário gigante.

A sessão recomendada de continuidade está detalhada em:

```text
estado/guia-sessao-hoje.md
```

Esse guia deve ser lido junto com este plano quando a estudante pedir:

```text
o que estudar hoje
quero estudar agora
me passa o plano de hoje
vamos continuar
```

## Princípios do plano

- Variar matérias quando não houver motivo pedagógico para repetição.
- Priorizar revisão antes de avançar quando houver lacunas recentes.
- Alternar prática objetiva, correção e reforço.
- Não transformar conteúdo planejado em conteúdo estudado.
- Não tratar acerto imediato como retenção de longo prazo.
- Não marcar como dominado um tema apenas porque a estudante disse que já estudou.
- Se a estudante quiser pular um tema, adaptar a sessão e manter o tema como pendente.

## Sessão recomendada agora

```yaml
current_recommended_session:
  status: practical_ready
  source: estado/guia-sessao-hoje.md
  goal: continuar_estudos_com_execucao_pequena_e_corrigivel
  sequence:
    - revisao_curta: tipos_de_mapas_tematicos
    - tema_principal: climatologia_do_brasil
    - pratica: 8_a_12_questoes_objetivas
    - correcao: imediata
    - reforco: somente_erros_e_confusoes
    - save: se_houver_respostas_e_correcao
```

## Próximas prioridades sugeridas

```yaml
next_priorities:
  revisao_curta:
    alta:
      - tipos_de_mapas_tematicos
      - referencial_em_fisica
      - movimento_uniforme_e_aceleracao_zero
      - unidade_m_s2_como_aceleracao
    media:
      - complexo_golgiense
      - osmose_vs_difusao_vs_transporte_ativo
      - numero_de_massa
      - cantigas_de_amigo
      - antropocentrismo_no_humanismo
  novos_conteudos:
    geografia:
      - climatologia_do_brasil
    quimica:
      - ligacoes_quimicas
    literatura:
      - quinhentismo
    matematica:
      - funcao_quadratica
      - equacao_do_segundo_grau
      - formula_de_bhaskara
    biologia:
      - mitose
      - meiose
      - dna_e_genes
    portugues:
      - interpretacao_de_texto
    redacao:
      - estrutura_enem
    sociologia:
      - cultura_e_etnocentrismo
```

## Ciclo diário recomendado

```text
1. Revisão curta de lacuna recente
2. Conteúdo novo ou aprofundamento
3. Bateria objetiva curta
4. Correção imediata
5. Reforço de erros
6. Revisão mista curta
7. Save da sessão quando houver progresso relevante
```

## Regra de escolha do tema do dia

```yaml
selection_rule:
  if_student_asks_generic_plan:
    choose:
      - one_short_review_from_high_priority
      - one_main_topic_from_not_practiced
  if_student_asks_specific_subject:
    do:
      - check_pending_review_related_to_subject
      - start_with_small_review_if_needed
      - continue_to_requested_subject
  if_student_says_already_studied:
    mark_as_reported_not_validated
    run_short_validation_questions: true
  if_student_is_tired_or_blocked:
    reduce_session_size: true
    prefer_review_or_guided_practice: true
```

## Critérios de ajuste

O plano deve mudar quando:

- a estudante informa conteúdo já estudado;
- desempenho mostra lacuna inesperada;
- há repetição de matérias sem justificativa;
- há cansaço, bloqueio ou risco emocional;
- uma prova ou tarefa escolar muda prioridade;
- uma revisão pendente vence;
- a estudante acerta em outro dia sem ajuda e mostra retenção melhor.

## Separação da atualização 2026-06-17

```yaml
update_2026_06_17:
  preserved:
    - objetivos_ativos_ENEM_FUVEST_VUNESP
    - principios_de_revisao_pratica_correcao
    - fila_de_prioridades_anterior
    - ciclo_diario_recomendado
  corrected_or_reorganized:
    - prioridades_foram_separadas_por_alta_e_media
    - plano_foi_alinhado_ao_guia_pratico_de_sessao
    - conteudos_nao_praticados_foram_mantidos_como_pendentes
  new_content:
    - uso_pratico_imediato
    - sessao_recomendada_agora
    - regra_de_escolha_do_tema_do_dia
    - referencia_ao_arquivo_estado_guia_sessao_hoje_md
  todos:
    - confirmar_datas_reais_das_provas_e_disponibilidade_semanal_da_estudante
    - validar_fontes_oficiais_de_ENEM_FUVEST_VUNESP_antes_de_priorizacao_fina_por_prova
```
