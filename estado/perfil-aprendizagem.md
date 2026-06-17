---
id: grimorio_vestibular.estado.perfil_aprendizagem
type: learning_profile_state
status: v1
student: gabi
created_at: 2026-06-15
updated_at: 2026-06-17
backend_ready: true
human_review_required: false
confidence: medium
---

# Perfil de Aprendizagem

Este arquivo registra padrões observados sobre como a Gabi parece responder ao estudo. O conteúdo deve ser tratado como hipótese operacional, não como diagnóstico fixo.

## Leitura prática atual

A Gabi parece responder melhor quando a sessão tem condução clara, carga pequena e correção rápida. O sistema não deve exigir que ela organize toda a sessão sozinha.

A hipótese operacional atual é:

```text
sessão pequena + pergunta objetiva + correção imediata + reforço curto = melhor continuidade de estudo
```

Essa hipótese ainda precisa ser validada em mais dias e matérias diferentes.

## Responde bem a

```yaml
responds_well_to:
  - baterias_objetivas_curtas
  - correcao_imediata
  - reforco_focado_nos_erros
  - revisao_mista
  - explicacoes_curta_apos_erro
  - contraste_entre_conceitos_parecidos
  - exemplo_numerico_simples
  - sessao_guiada_com_proximo_passo_claro
  - validacao_rapida_antes_de_avancar
```

## Preferências observadas

```yaml
observed_preferences:
  - prefere_variar_materias
  - questiona_repeticao_sem_proposito_claro
  - pede_revisao_antes_de_avancar
  - aceita_sequencia_de_pratica_e_correcao
  - demonstra_engajamento_quando_ve_progresso
  - tende_a_funcionar_melhor_com_tarefa_pequena_e_respondivel
```

## Pontos de atenção

```yaml
attention_points:
  - nao_confundir_preferencia_por_avancar_com_dominio_real
  - nao_assumir_retencao_de_longo_prazo_por_acertos_no_mesmo_chat
  - nao_inferir_estado_emocional_sem_evidencia
  - monitorar_reacao_a_repeticao_de_materias
  - evitar_plano_grande_demais_quando_o_pedido_for_estudar_hoje
  - validar_conteudo_informado_como_ja_estudado_antes_de_marcar_como_firme
```

## Estratégia recomendada para próxima sessão

```yaml
recommended_next_session_strategy:
  start:
    type: revisao_curta
    subject: geografia
    topic: tipos_de_mapas_tematicos
    format: 3_perguntas_rapidas
  then:
    if_review_is_sufficient:
      action: iniciar_climatologia_do_brasil
      style: explicacao_curta_mais_questoes_objetivas
    if_review_has_many_errors:
      action: reforcar_cartografia_e_nao_avancar_ainda
  communication:
    - dizer_o_que_vai_fazer_agora
    - explicar_o_motivo_em_uma_frase
    - pedir_resposta_em_formato_simples
    - corrigir_antes_de_propor_novo_bloco
```

## Sinais de boa sessão para Gabi

```yaml
good_session_signals:
  - ela_responde_as_perguntas_sem_precisar_reorganizar_o_plano
  - os_erros_sao_corrigidos_antes_de_avancar
  - a_quantidade_de_questoes_nao_gera_sobrecarga
  - a_proxima_acao_fica_clara
  - ha_save_somente_quando_houver_evidencia_real
```

## Estado atual de confiança

A confiança neste perfil é média. Há evidências suficientes para orientar a metodologia, mas ainda faltam registros em dias diferentes, com temas diferentes e revisões espaçadas.

## Como usar este perfil

O perfil deve orientar o plano, mas não prender a estudante a uma única forma de estudar. Se uma abordagem parar de funcionar, o sistema deve ajustar.

Em caso de dúvida, priorizar:

```text
menos conteúdo por vez, mais correção e melhor registro da lacuna
```

## Separação da atualização 2026-06-17

```yaml
update_2026_06_17:
  preserved:
    - responde_bem_a_baterias_objetivas_curtas
    - correcao_imediata
    - reforco_focado_nos_erros
    - revisao_mista
    - confianca_media_do_perfil
  corrected_or_reorganized:
    - perfil_foi_alinhado_ao_modo_tutor_de_sessao
    - preferencias_foram_conectadas_a_execucao_pequena_e_respondivel
    - pontos_de_atencao_passaram_a_incluir_plano_grande_demais_e_validacao
  new_content:
    - leitura_pratica_atual
    - estrategia_recomendada_para_proxima_sessao
    - sinais_de_boa_sessao_para_gabi
    - regra_menos_conteudo_por_vez_mais_correcao
  todos:
    - validar_se_a_sessao_guiada_com_3_perguntas_funciona_melhor_na_proxima_execucao
    - atualizar_confianca_do_perfil_apenas_apos_mais_sessoes_com_evidencia
```
