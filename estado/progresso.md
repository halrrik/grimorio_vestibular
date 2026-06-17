---
id: grimorio_vestibular.estado.progresso
type: progress_state
status: v1
student: gabi
created_at: 2026-06-15
updated_at: 2026-06-17
backend_ready: true
human_review_required: false
---

# Progresso

Este arquivo registra o estado vivo de progresso da estudante Gabi com base nos registros já commitados.

## Leitura prática do progresso

O progresso abaixo separa quatro coisas diferentes:

```text
conteúdo praticado com evidência ≠ conteúdo apenas informado
conteúdo planejado ≠ conteúdo estudado
acerto no curto prazo ≠ retenção futura
lacuna ativa ≠ fracasso
```

Essa separação é importante para orientar a próxima sessão sem inflar domínio nem repetir conteúdo sem necessidade.

## Estudado com evidência de prática

```yaml
studied_with_evidence:
  geografia:
    - topic: cartografia
      status: practiced_with_active_gap
      notes:
        - erros iniciais em meridianos, fusos e tipos de mapas
        - tipos_de_mapas_tematicos ainda exige revisão curta antes de avançar demais
        - cartografia_completa deve voltar em revisão média
  quimica:
    - topic: estrutura_atomica
      status: short_term_absorbed
      notes:
        - erro inicial em numero de massa
        - revisão mista indicou consolidação de curto prazo
        - retenção futura ainda precisa ser verificada
  fisica:
    - topic: cinematica_basica
      status: reinforced_with_pending_review
      notes:
        - dificuldade inicial em referencial, MU, aceleração, deslocamento e unidades
        - melhorou após reforço
        - referencial, movimento_uniforme_e_aceleracao_zero e unidade_m_s_vs_m_s2 seguem como revisão curta prioritária
  literatura:
    - topic: trovadorismo_e_humanismo
      status: short_term_absorbed
      notes:
        - erros pontuais em cantigas de amigo e antropocentrismo
        - desempenho final alto
        - retenção futura ainda precisa de revisão posterior
  matematica:
    - topic: funcoes_basicas
      status: short_term_absorbed
      notes:
        - alto desempenho nas baterias registradas
        - retenção futura ainda precisa de revisão posterior
  biologia:
    - topic: citologia
      status: short_term_absorbed
      notes:
        - erro pontual em complexo golgiense corrigido depois
        - osmose_vs_difusao_vs_transporte_ativo ainda deve aparecer em revisão curta
```

## Lacunas ativas a validar

```yaml
active_gaps_to_validate:
  next_session:
    subject: geografia
    topic: tipos_de_mapas_tematicos
    status: pending_validation
    source:
      - estado/revisoes.md
      - estado/guia-sessao-hoje.md
    validation_task: 3_perguntas_rapidas_ou_questoes_objetivas
    if_success:
      action: seguir_para_climatologia_do_brasil
      new_status_candidate: short_term_reinforced
    if_errors:
      action: reforcar_cartografia_antes_de_climatologia
      new_status_candidate: active_gap
  other_priority_gaps:
    fisica:
      - referencial
      - movimento_uniforme_e_aceleracao_zero
      - unidade_m_s_vs_m_s2
    biologia:
      - osmose_vs_difusao_vs_transporte_ativo
    quimica:
      - numero_de_massa
```

## Informado como já estudado, mas sem validação suficiente

```yaml
reported_as_studied_not_validated:
  literatura:
    - trovadorismo
    - humanismo
  fisica:
    - unknown
  biologia:
    - ecologia
```

## Planejado ou pendente

```yaml
pending_or_planned:
  priority_for_next_content:
    geografia:
      - climatologia_do_brasil
  remaining:
    literatura:
      - quinhentismo
    portugues:
      - interpretacao_de_texto
    redacao:
      - estrutura_enem
    matematica:
      - funcao_quadratica
      - equacao_do_segundo_grau
      - formula_de_bhaskara
    biologia:
      - mitose
      - meiose
      - cromossomos
      - dna
      - genes
    sociologia:
      - cultura_e_etnocentrismo
    quimica:
      - ligacoes_quimicas
```

## Próxima ação operacional

```yaml
next_operational_action:
  step_1:
    type: revisao_curta
    subject: geografia
    topic: tipos_de_mapas_tematicos
    status_before_session: pending_validation
  step_2:
    type: novo_conteudo
    subject: geografia
    topic: climatologia_do_brasil
    status_before_session: not_practiced_yet
    condition: fazer_somente_se_revisao_curta_nao_mostrar_lacuna_forte
  step_3:
    type: save
    condition: registrar_apenas_depois_de_respostas_correcao_e_lacunas_observadas
```

## Observação importante

Os status acima indicam progresso operacional, não domínio definitivo. Retenção futura ainda precisa ser verificada por revisão espaçada ou nova prática em outro dia.

## Separação da atualização 2026-06-17

```yaml
update_2026_06_17:
  preserved:
    - estudado_com_evidencia_de_pratica
    - informado_como_estudado_sem_validacao
    - pendencias_de_conteudo
    - observacao_sobre_nao_haver_dominio_definitivo
  corrected_or_reorganized:
    - cartografia_passou_de_practiced_para_practiced_with_active_gap
    - fisica_passou_de_reinforced_para_reinforced_with_pending_review
    - climatologia_do_brasil_foi_destacada_como_proximo_conteudo_prioritario
    - lacunas_prioritarias_foram_separadas_de_conteudos_pendentes
  new_content:
    - leitura_pratica_do_progresso
    - active_gaps_to_validate
    - next_operational_action
  todos:
    - apos_a_proxima_sessao_atualizar_resultado_de_tipos_de_mapas_tematicos
    - se_climatologia_for_praticada_mover_para_studied_with_evidence_com_status_apropriado
```
