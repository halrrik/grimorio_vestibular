---
id: grimorio_vestibular.estado.metodologia
type: methodology_state
status: v1
student: gabi
created_at: 2026-06-15
updated_at: 2026-06-17
backend_ready: true
human_review_required: false
---

# Metodologia Atual

Este arquivo registra a metodologia operacional atualmente recomendada para a Gabi no GRIMORIO_VESTIBULAR.

## Objetivo da metodologia

A metodologia deve impedir que o estudo vire apenas leitura passiva ou lista grande de matérias.

A sessão precisa produzir evidência mínima de aprendizagem:

```text
resposta da estudante -> correção -> erro identificado -> reforço -> próxima decisão
```

Sem resposta e correção, o conteúdo deve permanecer como planejado ou visto, não como aprendido.

## Fluxo preferencial

```text
orientar -> revisar ponto curto -> explicar o mínimo necessário -> propor prática -> esperar resposta -> corrigir -> reforçar erro -> testar de novo se necessário -> decidir próximo passo -> save
```

Esse fluxo substitui a entrega de plano grande. A estudante não precisa conduzir tudo; a IA deve guiar a sessão em blocos pequenos.

## Fluxo operacional da próxima sessão

```yaml
next_session_method:
  source:
    - estado/plano-atual.md
    - estado/revisoes.md
    - estado/progresso.md
    - estado/guia-sessao-hoje.md
  start:
    action: propor_3_perguntas_rapidas
    subject: geografia
    topic: tipos_de_mapas_tematicos
    reason: validar_lacuna_ativa_antes_de_climatologia
  after_answers:
    action: corrigir_imediatamente
    must_identify:
      - acertos
      - erros
      - tipo_de_erro
      - conceito_a_reforcar
  decision:
    if_good_result:
      next: iniciar_climatologia_do_brasil_com_explicaçao_curta_e_questoes
    if_many_errors:
      next: reforcar_cartografia_e_nao_avancar_ainda
  save:
    condition: somente_depois_de_respostas_correcao_e_lacunas_observadas
```

## Práticas recomendadas

```yaml
recommended_practices:
  orientation:
    - dizer_o_que_vai_ser_estudado_agora
    - explicar_por_que_em_uma_frase
    - pedir_uma_acao_clara_da_estudante
    - nao_entregar_todo_o_plano_de_uma_vez
  explanation:
    - curta
    - direta
    - focada_no_erro_ou_no_conceito_base
    - acompanhada_de_um_exemplo_simples_quando_necessario
  practice:
    - perguntas_rapidas_para_validacao
    - baterias_de_multipla_escolha
    - questoes_curta_para_diagnostico
    - revisao_mista_apos_blocos_de_conteudo
  correction:
    - imediata
    - separando_acerto_erro_lacuna
    - explicando_por_que_a_alternativa_correta_e_correta
    - explicando_por_que_o_erro_aconteceu_quando_possivel
  reinforcement:
    - focado_nos_erros
    - curto
    - testado_novamente_apos_explicaçao
    - sem_transformar_erro_em_sermao
  save:
    - gerar_save_quando_houver_progresso_relevante
    - registrar_lacunas_residuais
    - registrar_proxima_missao
    - separar_fato_observado_de_inferencia
```

## Diagnóstico por erro

Quando houver erro, classificar operacionalmente:

```yaml
error_diagnosis:
  possible_types:
    - falta_de_conceito
    - confusao_entre_conceitos
    - interpretacao_da_questao
    - memoria
    - pressa_ou_atencao
    - formula_ou_unidade
    - carga_emocional_ou_cansaco
    - questao_mal_formulada
    - unknown
  required_action:
    - explicar_o_ponto_exato
    - fazer_uma_nova_pergunta_curta_se_o_erro_for_importante
    - nao_avancar_automaticamente_quando_houver_erro_recorrente
```

## Quando avançar

```yaml
advance_rule:
  can_advance_when:
    - estudante_respondeu
    - correcao_foi_feita
    - erros_importantes_foram_reforcados
    - nao_ha_sinal_forte_de_bloqueio_ou_cansaco
    - proxima_etapa_e_pequena_e_clara
  should_not_advance_when:
    - estudante_ainda_nao_respondeu
    - houve_erro_conceitual_importante_sem_reforco
    - ha_muitos_erros_no_mesmo_pre_requisito
    - estudante_mostra_cansaco_ou_frustracao
```

## Quando reduzir a carga

```yaml
reduce_load_when:
  signs:
    - cansaco
    - frustracao
    - muitas_respostas_erradas_seguidas
    - pedido_para_pular
    - confusao_em_pre_requisito
  action:
    - diminuir_quantidade_de_questoes
    - trocar_aula_longa_por_exemplo_guiado
    - manter_tema_como_pendente_se_for_pulado
    - priorizar_revisao_curta_em_vez_de_conteudo_novo
```

## Regras metodológicas

- Não despejar conteúdo sem prática.
- Não avançar demais sem corrigir lacunas recentes.
- Usar reforço focado antes de considerar um erro resolvido.
- Usar revisão mista para testar consolidação de curto prazo.
- Registrar retenção futura como `unknown` até haver revisão posterior.
- Não declarar domínio definitivo por acerto no mesmo chat.
- Não tratar conteúdo informado pela estudante como validado sem perguntas de checagem.
- Não transformar pedido simples de estudo em plano gigante.

## Indicadores de funcionamento

```yaml
method_signals:
  positive:
    - estudante_pede_mais_questoes
    - estudante_pede_revisao_antes_de_avancar
    - desempenho_melhora_apos_reforco
    - erros_recorrentes_diminuem
    - estudante_consegue_justificar_resposta
  warning:
    - repeticao_de_materia_sem_justificativa
    - acerto_imediato_sem_revisao_futura
    - questoes_sem_correcao
    - plano_amplo_sem_execucao
    - conteudo_visto_sendo_tratado_como_aprendido
    - avanco_sem_validar_lacuna_ativa
```

## Separação da atualização 2026-06-17

```yaml
update_2026_06_17:
  preserved:
    - explicacao_curta
    - questoes_objetivas
    - correcao_imediata
    - reforco_dos_erros
    - revisao_mista
    - save_quando_houver_progresso
  corrected_or_reorganized:
    - fluxo_preferencial_foi_transformado_em_ciclo_de_tutoria
    - diagnostico_por_erro_foi_estruturado_em_yaml_operacional
    - regras_de_avanco_e_reducao_de_carga_foram_explicitadas
  new_content:
    - objetivo_da_metodologia
    - fluxo_operacional_da_proxima_sessao
    - advance_rule
    - reduce_load_when
    - separacao_entre_resposta_correcao_erro_reforco_e_decisao
  todos:
    - apos_a_proxima_sessao_verificar_se_o_fluxo_pequeno_funcionou_para_gabi
    - registrar_no_save_se_a_estudante_avancou_para_climatologia_ou_precisou_reforcar_cartografia
```
