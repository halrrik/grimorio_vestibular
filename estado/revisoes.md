---
id: grimorio_vestibular.estado.revisoes
type: review_state
status: v1
student: gabi
created_at: 2026-06-15
updated_at: 2026-06-17
backend_ready: true
human_review_required: false
---

# Revisões

Este arquivo registra revisões pendentes e recomendadas para a Gabi.

## Uso prático imediato

A revisão não deve virar uma lista longa. Para a próxima sessão, usar apenas uma revisão curta antes do tema principal.

A revisão ativa para continuidade imediata é:

```yaml
active_review_for_next_session:
  source: estado/guia-sessao-hoje.md
  subject: geografia
  topic: tipos_de_mapas_tematicos
  duration: 10_min
  purpose: destravar_lacuna_recente_de_cartografia_antes_de_climatologia_do_brasil
  validation:
    mode: 3_perguntas_rapidas_ou_questoes_objetivas
    result_status_before_response: pending
```

## Revisão curta — 3 a 5 dias

```yaml
short_review_3_to_5_days:
  geografia:
    high_priority:
      - tipos_de_mapas_tematicos
    normal_priority:
      - fusos_horarios
  quimica:
    normal_priority:
      - numero_de_massa
  fisica:
    high_priority:
      - referencial
      - movimento_uniforme_e_aceleracao_zero
      - unidade_m_s_vs_m_s2
    normal_priority:
      - distancia_percorrida_vs_deslocamento
  biologia:
    normal_priority:
      - complexo_golgiense
      - osmose_vs_difusao_vs_transporte_ativo
  literatura:
    normal_priority:
      - antropocentrismo_no_humanismo
      - cantigas_de_amigo
```

## Revisão média — 10 a 14 dias

```yaml
medium_review_10_to_14_days:
  - cartografia_completa
  - estrutura_atomica_completa
  - cinematica_basica
  - trovadorismo_e_humanismo
  - funcoes_basicas
  - citologia_basica
```

## Conteúdos ainda não praticados

```yaml
not_practiced_yet:
  priority_for_next_content:
    - climatologia_do_brasil
  remaining:
    - quinhentismo
    - interpretacao_de_texto
    - estrutura_de_redacao_enem
    - funcao_quadratica
    - mitose
    - meiose
    - dna_e_genes
    - ligacoes_quimicas
    - cultura_e_etnocentrismo
```

## Como usar este arquivo durante a sessão

```yaml
review_session_rule:
  before_new_content:
    do: escolher_uma_revisao_curta
    max_duration: 10_min
    preferred_active_item: tipos_de_mapas_tematicos
  after_student_answers:
    if_many_errors:
      action: reforcar_conceito_e_nao_avancar_ainda
      status: lacuna_ativa
    if_good_result:
      action: seguir_para_climatologia_do_brasil
      status: short_term_reinforced
    save_required_if:
      - houve_respostas
      - houve_correcao
      - houve_erro_relevante_ou_avanco_claro
```

## Regras de revisão

- Revisão curta deve atacar erro recente ou ponto frágil.
- Revisão média deve verificar retenção, não apenas repetição.
- Conteúdo com acerto no mesmo chat ainda precisa de revisão futura.
- Se a estudante errar novamente, reclassificar o tópico como lacuna ativa.
- Se acertar em outro dia sem ajuda, pode subir para retenção mais confiável.
- Revisão planejada não conta como revisão feita.
- Tema informado como já estudado não conta como domínio validado.

## Separação da atualização 2026-06-17

```yaml
update_2026_06_17:
  preserved:
    - revisoes_curtas_existentes
    - revisoes_medias_existentes
    - conteudos_nao_praticados
    - regras_originais_de_revisao
  corrected_or_reorganized:
    - geografia_tipos_de_mapas_tematicos_foi_marcado_como_revisao_ativa
    - fisica_foi_separada_por_prioridade_alta_e_normal
    - climatologia_do_brasil_foi_destacada_como_proximo_conteudo_principal
  new_content:
    - uso_pratico_imediato
    - active_review_for_next_session
    - review_session_rule
    - separacao_explicita_entre_revisao_planejada_e_revisao_realizada
  todos:
    - apos_a_proxima_sessao_atualizar_result_status_de_tipos_de_mapas_tematicos
    - se_climatologia_for_praticada_mover_de_not_practiced_yet_para_progresso_com_evidencia
```
