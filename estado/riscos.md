---
id: grimorio_vestibular.estado.riscos
type: risk_state
status: v0
student: gabi
created_at: 2026-06-15
updated_at: 2026-06-15
backend_ready: true
human_review_required: false
---

# Riscos

Este arquivo registra riscos operacionais, pedagógicos e humanos observados ou inferidos no GRIMORIO_VESTIBULAR.

## Riscos pedagógicos

```yaml
pedagogical_risks:
  - id: confundir_acerto_imediato_com_retencao
    description: Acertos no mesmo chat indicam consolidação curta, não domínio definitivo.
    mitigation: criar_revisao_espacada
  - id: tratar_questoes_do_chat_como_simulado_oficial
    description: Questões geradas no chat ajudam diagnóstico, mas não equivalem a prova oficial cronometrada.
    mitigation: incluir_questoes_oficiais_e_simulados_cronometrados
  - id: plano_amplo_demais
    description: Muitas matérias no plano podem gerar sensação de organização sem execução real.
    mitigation: limitar_ciclo_diario_e_registrar_execucao
  - id: conteudo_informado_como_estudado_sem_validacao
    description: A estudante pode informar que já estudou algo, mas isso não mede domínio.
    mitigation: registrar_como_informado_e_validar_depois
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
```

## Regra de mitigação central

```text
O plano existe para servir ao aprendizado da estudante. Se o plano começa a prejudicar aprendizado, motivação ou segurança emocional, o plano deve mudar.
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
