---
id: grimorio_vestibular.aprendizados.smd_2026_06_17_limite_commits_grimorio
type: smd_operational_decision
status: aprovado
created_at: 2026-06-17
updated_at: 2026-06-17
repository: halrrik/grimorio_vestibular
backend_ready: true
human_review_required: false
canonical_layer: aprendizados
source: conversa_operacional_com_responsavel
---

# SMD — Atualização diária do estado de aprendizagem e commits em lote

## Contexto

Durante a atualização prática do GRIMORIO_VESTIBULAR em 2026-06-17, vários arquivos de estado vivo foram atualizados e commitados individualmente.

Esses commits não eram manutenção genérica do repositório. Eram atualização necessária do estado de aprendizagem da estudante Gabi, derivada do uso real do Grimório Vestibular em sessões de estudo.

Pela hipótese do Grimório Vestibular, o que a estudante faz no estudo deve voltar para o repositório para atualizar plano, progresso, revisões, lacunas e próximos passos.

## Problema observado

O problema não é atualizar o Grimório. Atualizar é obrigatório para o sistema funcionar.

O problema é fazer essa atualização manualmente, arquivo por arquivo, commit por commit.

Exemplo do problema:

```text
1 sessão de estudo -> vários fatos observados
vários fatos observados -> vários arquivos vivos afetados
5 a 10 arquivos afetados -> 5 a 10 commits se feito manualmente
2 ou 3 chats atrasados -> explosão de tempo, custo e tokens
```

Esse padrão não escala para uso diário por uma estudante real.

## Decisão operacional

A atualização diária do GRIMORIO_VESTIBULAR deve continuar existindo.

O que deve mudar é o modo de atualização.

A partir desta decisão, atualizações de estado de aprendizagem não devem ser feitas como sequência manual de commits por arquivo.

Quando houver uma ou mais sessões de estudo para promover ao estado vivo, o fluxo correto deve ser:

```text
1. extrair fatos observados da sessão
2. separar fatos, inferências, lacunas e próximos passos
3. identificar todos os arquivos vivos afetados
4. gerar pacote de alterações em lote
5. auditar consistência entre os arquivos
6. fazer um commit único por lote coerente
7. verificar o resultado no GitHub
```

## Regra nova

```yaml
daily_learning_state_update_policy:
  required:
    - atualizar_o_grimorio_a_partir_do_uso_real_da_estudante
    - preservar_evidencia_de_aprendizagem
    - atualizar_plano_progresso_revisoes_lacunas_e_proximas_acoes
    - separar_conteudo_estudado_de_conteudo_planejado
    - separar_conteudo_informado_de_conteudo_validado
  avoid:
    - um_commit_por_arquivo_quando_houver_varios_arquivos_relacionados
    - atualizar_estado_vivo_manualmente_em_cadeia_longa
    - deixar_dias_de_estudo_sem_promocao_para_o_repositorio
    - tratar_atualizacao_diaria_como_manutencao_opcional
  prefer:
    - commits_em_lote
    - save_de_sessao_com_promocao_para_estado_vivo
    - auditoria_antes_do_commit
    - automacao_dedicada_para_atualizacao_diaria
    - resumo_objetivo_do_lote_commitado
```

## Prioridade prática

A prioridade não é parar de atualizar o Grimório Vestibular.

A prioridade é criar um fluxo ou automação diária para atualização em lote do estado de aprendizagem da Gabi.

A automação deve rodar no final do dia ou quando houver sessões pendentes, com capacidade de:

```yaml
automation_requirements:
  purpose: atualizacao_diaria_em_lote_do_estado_de_aprendizagem
  must_do:
    - ler_estrutura_atual_do_repositorio
    - localizar_sessoes_ou_extracoes_pendentes_do_dia
    - identificar_arquivos_vivos_afetados
    - aplicar_mudancas_em_lote
    - evitar_commit_por_arquivo
    - gerar_resumo_das_mudancas
    - listar_arquivos_modificados
    - aplicar_mensagem_de_commit_clara
    - verificar_resultado_apos_commit
  must_not_do:
    - reinventar_estrutura_existente
    - misturar_conteudo_planejado_com_conteudo_estudado
    - transformar_ideia_nao_aprovada_em_regra_canonica
    - marcar_conteudo_planejado_como_estudado
    - tratar_acerto_imediato_como_retencao_definitiva
```

## Nota sobre chave, permissão e execução

A automação futura deve usar acesso ao repositório com permissão suficiente para escrita e commit.

O ponto crítico não é apenas gerar texto. O ponto crítico é garantir que a automação consiga escrever, commitar e verificar o resultado no GitHub.

A operação precisa funcionar com uso real diário, não apenas em testes pontuais.

## Arquivos já atualizados nesta rodada

```text
estado/guia-sessao-hoje.md
INDICE.md
estado/plano-atual.md
estado/revisoes.md
estado/progresso.md
estado/metodologia.md
estado/riscos.md
estado/perfil-aprendizagem.md
```

## Arquivos possivelmente restantes desta atualização

Ainda podem restar arquivos a revisar para consolidar o fluxo atual, mas eles não devem ser atualizados impulsivamente arquivo por arquivo.

Candidatos prováveis:

```text
aprendizados/operacional.md
aprendizados/planejamento.md
produto/fluxo-operacional.md
produto/regras.md
produto/validacao-funcional.md
```

Esses arquivos devem ser tratados por prioridade e, quando possível, em lote.

## Próxima ação recomendada

1. Terminar a atualização do chat atual com o menor número possível de commits.
2. Processar os outros chats pendentes de estudo da Gabi com extração objetiva.
3. Promover cada dia ou conjunto coerente de sessões em lote.
4. Criar automação diária para atualização do estado de aprendizagem no final do dia.

## Critério de sucesso

O novo fluxo será considerado melhor se:

```yaml
success_criteria:
  - reduz_numero_de_commits_desnecessarios
  - preserva_rastreabilidade_do_que_gabi_estudou
  - atualiza_o_plano_para_o_proximo_uso
  - distingue_aprendido_visto_planejado_e_pendente
  - permite_revisao_humana_do_lote
  - evita_fragmentacao_da_estrutura
  - separa_sessao_de_estudo_da_rotina_de_promocao_para_estado
  - mantem_o_repositorio_util_para_continuar_estudando_no_dia_seguinte
```

## Veredito

Não parar as atualizações do Grimório Vestibular.

Parar apenas o padrão manual de atualização arquivo por arquivo.

A próxima etapa deve ser atualização diária em lote do estado de aprendizagem, com automação, prioridade clara e verificação de permissão de escrita.
