---
id: grimorio_vestibular.estado.riscos
type: risk_state
status: v1
student: gabi
created_at: 2026-06-15
updated_at: 2026-06-17
backend_ready: true
human_review_required: false
---

# Riscos

Este arquivo registra riscos operacionais, pedagógicos e humanos observados ou inferidos no GRIMORIO_VESTIBULAR.

## Leitura prática atual

A atualização recente tornou o Grimório mais executável, mas também deixa claro um risco central: se a IA voltar a entregar planos grandes ou avançar sem validação, o sistema perde o foco em aprendizagem real.

Para a próxima sessão, os riscos mais importantes são:

```yaml
current_priority_risks:
  - id: plano_grande_demais_para_pedido_simples
    severity: high
    description: A estudante pede o que estudar hoje e recebe muitas matérias, o que pode gerar organização aparente sem execução real.
    mitigation: usar_estado_guia_sessao_hoje_e_comecar_com_uma_revisao_curta
  - id: avancar_para_climatologia_sem_validar_cartografia
    severity: high
    description: Climatologia do Brasil está planejada, mas tipos_de_mapas_tematicos ainda precisa revisão curta.
    mitigation: aplicar_3_perguntas_rapidas_de_tipos_de_mapas_tematicos_antes_de_avancar
  - id: confundir_conteudo_visto_com_conteudo_aprendido
    severity: high
    description: Conteúdo informado ou planejado pode ser tratado como domínio validado sem evidência.
    mitigation: exigir_resposta_correcao_e_registro_de_lacunas
  - id: save_sem_evidencia
    severity: medium
    description: Salvar sessão sem respostas, correção ou lacunas observadas transforma intenção em progresso falso.
    mitigation: salvar_apenas_depois_de_pratica_e_correcao
```

## Riscos pedagógicos

```yaml
pedagogical_risks:
  - id: confundir_acerto_imediato_com_retencao
    description: Acertos no mesmo chat indicam consolidação curta, não domínio definitivo.
    mitigation: criar_revisao_espacada
  - id: tratar_questoes_do_chat_como_simulado_oficial
    description: Questões geradas no chat ajudam diagnóstico, mas não equivalem a prova oficial cronometrada.
    mitigation: incluir_questoes_oficiais_e_simulados_cronometrados_quando_houver_base
  - id: plano_amplo_demais
    description: Muitas matérias no plano podem gerar sensação de organização sem execução real.
    mitigation: limitar_ciclo_diario_e_registrar_execucao
  - id: conteudo_informado_como_estudado_sem_validacao
    description: A estudante pode informar que já estudou algo, mas isso não mede domínio.
    mitigation: registrar_como_informado_e_validar_depois
  - id: avancar_sem_corrigir_lacuna_ativa
    description: Avançar para conteúdo novo sem resolver erro recente pode acumular fragilidade.
    mitigation: reforcar_o_erro_e_testar_novamente_antes_de_avancar
```

## Riscos operacionais

```yaml
operational_risks:
  - id: commit_no_repositorio_errado
    description: Registros da aplicação não devem ir para o Grimório Pai.
    mitigation: validar_repository_halrrik_grimorio_vestibular
  - id: registros_nao_promovidos
    description: Arquivos backend-ready podem acumular sem atualizar o estado vivo.
    mitigation: criar_pipeline_de_auditoria_e_promocao
  - id: schema_inconsistente
    description: Campos como true/false/unknown e yes/no podem ficar inconsistentes.
    mitigation: padronizar_schema
  - id: inferencia_como_fato
    description: O sistema pode transformar hipótese em verdade operacional.
    mitigation: separar_fatos_inferencias_pontos_incertos
  - id: arquivos_de_estado_desalinhados
    description: Plano, progresso, revisões, metodologia e guia de sessão podem divergir entre si.
    mitigation: manter_referencias_cruzadas_e_atualizar_estado_em_conjunto
```

## Riscos humanos

```yaml
human_risks:
  - id: sobrecarga
    description: Plano ou sessão podem exigir mais do que a estudante consegue sustentar no momento.
    mitigation: reduzir_carga_ou_alternar_abordagem
  - id: gatilho_emocional
    description: Certos temas ou insistências podem gerar bloqueio ou desconforto.
    mitigation: proteger_estudante_e_mudar_rota
  - id: frustracao_por_repeticao
    description: Repetir matérias sem explicar motivo pode reduzir engajamento.
    mitigation: justificar_repeticao_ou_variar_materias
  - id: dependencia_de_conducao_externa
    description: Se a sessão não der uma ação clara, a estudante pode travar esperando orientação.
    mitigation: sempre_terminar_com_proximo_passo_pequeno_e_respondivel
```

## Regra de mitigação central

```text
O plano existe para servir ao aprendizado da estudante. Se o plano começa a prejudicar aprendizado, motivação ou segurança emocional, o plano deve mudar.
```

## Regra de proteção para a próxima sessão

```yaml
next_session_protection_rule:
  start_with: uma_revisao_curta
  max_initial_scope:
    - tipos_de_mapas_tematicos
    - climatologia_do_brasil_somente_se_a_revisao_for_suficiente
  avoid:
    - plano_com_muitas_materias
    - aula_longa_sem_questoes
    - avancar_sem_correcao
    - salvar_sem_evidencia
  must_end_with:
    - resultado_da_pratica
    - lacunas_observadas
    - proxima_acao
```

## Riscos ainda não avaliados

```yaml
unknown_risks:
  - retencao_apos_varios_dias
  - desempenho_em_questoes_oficiais
  - desempenho_em_simulado_cronometrado
  - carga_horaria_real_disponivel
  - condicoes_de_estudo_fora_do_chat
```

## Separação da atualização 2026-06-17

```yaml
update_2026_06_17:
  preserved:
    - riscos_pedagogicos_existentes
    - riscos_operacionais_existentes
    - riscos_humanos_existentes
    - regra_de_mitigacao_central
    - riscos_ainda_nao_avaliados
  corrected_or_reorganized:
    - plano_amplo_demais_foi_elevado_a_risco_prioritario_atual
    - avanco_sem_validacao_foi_explicitado_como_risco_pedagogico
    - desalinhamento_entre_arquivos_de_estado_foi_adicionado_como_risco_operacional
  new_content:
    - leitura_pratica_atual
    - current_priority_risks
    - dependencia_de_conducao_externa
    - next_session_protection_rule
  todos:
    - depois_da_proxima_sessao_verificar_se_a_carga_foi_pequena_o_suficiente
    - verificar_se_o_save_teve_evidencia_real_antes_de_promover_progresso
```
