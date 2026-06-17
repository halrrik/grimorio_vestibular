---
id: grimorio_vestibular.estado.guia_sessao_hoje
type: practical_study_session_guide
status: v0
student: gabi
created_at: 2026-06-17
updated_at: 2026-06-17
backend_ready: true
human_review_required: false
---

# Guia de Sessao de Hoje

Este arquivo existe para permitir continuidade pratica dos estudos da Gabi sem depender de um plano grande ou de uma aula generica.

O objetivo e orientar a proxima sessao de estudo com passos pequenos, corrigiveis e registraveis.

## Regra principal

Nao transformar a sessao em lista enorme de materias.

A sessao deve seguir este ciclo:

```text
revisao curta -> tema principal -> questoes -> correcao -> reforco de erros -> proximo passo -> save
```

## Sessao recomendada para continuidade imediata

```yaml
session_today_recommended:
  status: practical_ready
  goal: continuar_estudos_sem_sobrecarga
  student: gabi
  sequence:
    step_1:
      type: revisao_curta
      subject: geografia
      topic: tipos_de_mapas_tematicos
      duration: 10_min
      reason: lacuna_recente_em_cartografia
    step_2:
      type: tema_principal
      subject: geografia
      topic: climatologia_do_brasil
      duration: 35_to_45_min
      reason: conteudo_planejado_e_ainda_nao_praticado
    step_3:
      type: pratica_objetiva
      task: 8_a_12_questoes_de_diagnostico
      correction: imediata
    step_4:
      type: reforco
      task: revisar_apenas_erros_e_confusoes
    step_5:
      type: save
      task: registrar_desempenho_lacunas_revisoes_e_proxima_acao
```

## Como a IA deve iniciar a sessao

Quando a estudante pedir o que estudar hoje, responder de forma curta e conduzida:

```text
Vamos fazer uma sessao guiada.

Hoje vou comecar por uma revisao curta de Geografia e depois entrar em Climatologia do Brasil.

Primeiro passo: responda 3 perguntas rapidas sobre tipos de mapas tematicos. Depois eu corrijo e digo o proximo passo.
```

## O que nao fazer

- Nao entregar 5 ou 6 materias de uma vez.
- Nao entregar resumo longo antes de diagnosticar.
- Nao marcar conteudo como aprendido apenas porque foi planejado.
- Nao tratar acerto imediato como retencao definitiva.
- Nao avancar sem corrigir erros importantes.

## Conteudo novo, correcao e reorganizacao

```yaml
update_2026_06_17:
  new_content:
    - guia_pratico_para_sessao_de_hoje
    - sequencia_executavel_de_revisao_tema_principal_pratica_correcao_save
    - resposta_modelo_para_inicio_de_sessao
  corrections:
    - evita_plano_grande_demais_para_pedido_simples_de_estudo
    - separa_conteudo_planejado_de_conteudo_realmente_estudado
    - reforca_que_acerto_imediato_nao_e_retencao_definitiva
  reorganization:
    - transforma_prioridades_do_estado_em_acao_estudavel_hoje
    - preserva_estado_vivo_em_estado_sem_mover_regras_de_produto
  todos:
    - confirmar_disponibilidade_semanal_da_estudante
    - validar_fontes_oficiais_de_ENEM_FUVEST_VUNESP_antes_de_montar_calendario_maior
```
