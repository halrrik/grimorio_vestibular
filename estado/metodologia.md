---
id: grimorio_vestibular.estado.metodologia
type: methodology_state
status: v0
student: gabi
created_at: 2026-06-15
updated_at: 2026-06-15
backend_ready: true
human_review_required: false
---

# Metodologia Atual

Este arquivo registra a metodologia operacional atualmente recomendada para a Gabi no GRIMORIO_VESTIBULAR.

## Fluxo preferencial

```text
explicação curta -> questões objetivas -> correção imediata -> reforço dos erros -> nova bateria -> revisão mista -> save
```

Esse fluxo mostrou bons sinais na sessão registrada: a estudante melhorou após reforços, pediu revisões antes de avançar e respondeu bem a baterias mistas.

## Práticas recomendadas

```yaml
recommended_practices:
  explanation:
    - curta
    - direta
    - focada_no_erro_ou_no_conceito_base
  practice:
    - baterias_de_multipla_escolha
    - questoes_curta_para_diagnostico
    - revisao_mista_apos_blocos_de_conteudo
  correction:
    - imediata
    - separando_acerto_erro_lacuna
    - explicando_por_que_a_alternativa_correta_e_correta
  reinforcement:
    - focado_nos_erros
    - curto
    - testado_novamente_apos_explicaçao
  save:
    - gerar_save_quando_houver_progresso_relevante
    - registrar_lacunas_residuais
    - registrar_proxima_missao
```

## Diagnóstico por erro

Quando houver erro, perguntar operacionalmente:

```text
Foi falta de conceito?
Foi confusão entre conceitos parecidos?
Foi interpretação da questão?
Foi memória?
Foi pressa ou atenção?
Foi carga emocional/cansaço?
Foi questão mal formulada?
```

## Regras metodológicas

- Não despejar conteúdo sem prática.
- Não avançar demais sem corrigir lacunas recentes.
- Usar reforço focado antes de considerar um erro resolvido.
- Usar revisão mista para testar consolidação de curto prazo.
- Registrar retenção futura como `unknown` até haver revisão posterior.

## Indicadores de funcionamento

```yaml
method_signals:
  positive:
    - estudante_pede_mais_questoes
    - estudante_pede_revisao_antes_de_avancar
    - desempenho_melhora_apos_reforco
    - erros_recorrentes_diminuem
  warning:
    - repeticao_de_materia_sem_justificativa
    - acerto_imediato_sem_revisao_futura
    - questoes_sem_correcao
    - plano_amplo_sem_execucao
```
