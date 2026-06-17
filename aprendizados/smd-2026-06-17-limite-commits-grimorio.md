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

# SMD — Limite operacional de commits no Grimorio Vestibular

## Contexto

Durante a atualização prática do GRIMORIO_VESTIBULAR em 2026-06-17, vários arquivos de estado vivo foram atualizados e commitados individualmente.

Isso permitiu avançar, mas expôs um limite operacional importante: atualizar o Grimório arquivo por arquivo não é sustentável quando a mudança envolve muitos arquivos ou vários blocos de texto.

## Problema observado

O fluxo atual de commit individual gera custo alto quando há muitas atualizações pequenas.

Exemplo do problema:

```text
1 arquivo alterado -> 1 commit
10 arquivos alterados -> 10 commits
varios textos por arquivo -> explosao operacional
```

Esse padrão não escala para manutenção frequente do Grimório Vestibular.

## Decisão operacional

A partir desta decisão, atualizações maiores do GRIMORIO_VESTIBULAR não devem ser feitas arquivo por arquivo no chat comum.

Quando houver mudança em vários arquivos, o fluxo correto deve ser:

```text
1. identificar prioridade real
2. agrupar mudanças relacionadas
3. gerar pacote de arquivos ou diff conjunto
4. auditar consistência
5. fazer um commit único por lote coerente
6. registrar resumo objetivo do lote
```

## Regra nova

```yaml
commit_batch_policy:
  avoid:
    - um_commit_por_arquivo_quando_houver_varios_arquivos_relacionados
    - atualizacoes_grandes_em_chat_de_estudo_normal
    - manutencao_extensa_do_repositorio_durante_sessao_da_estudante
  prefer:
    - commits_em_lote
    - arquivos_smd_de_decisao_operacional
    - prioridade_antes_de_execucao
    - auditoria_antes_do_commit
    - automacao_dedicada_para_manutencao_do_repositorio
```

## Prioridade prática

A prioridade agora não é continuar atualizando todos os arquivos restantes do Grimório Vestibular.

A prioridade é criar um fluxo operacional ou automação dedicada para manutenção do repositório, com capacidade de:

```yaml
automation_requirements:
  purpose: manutencao_em_lote_do_grimorio_vestibular
  must_do:
    - ler_estrutura_atual_do_repositorio
    - identificar_arquivos_afetados
    - aplicar_mudancas_em_lote
    - evitar_commit_por_arquivo
    - gerar_resumo_das_mudancas
    - listar_arquivos_modificados
    - sugerir_ou_aplicar_mensagem_de_commit
    - verificar_resultado_apos_commit
  must_not_do:
    - reinventar_estrutura_existente
    - misturar_sessao_de_estudo_com_manutencao_de_repositorio
    - transformar_ideia_nao_aprovada_em_regra_canonica
    - marcar_conteudo_planejado_como_estudado
```

## Nota sobre chave e permissão

A automação futura deve usar acesso ao repositório com permissão suficiente para escrita e commit.

O ponto crítico não é apenas gerar texto. O ponto crítico é garantir que a automação consiga efetivamente escrever, commitar e verificar o resultado no GitHub.

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

## Arquivos possivelmente restantes

Ainda podem restar arquivos a revisar, mas eles não devem ser atualizados impulsivamente arquivo por arquivo.

Candidatos prováveis:

```text
aprendizados/operacional.md
aprendizados/planejamento.md
produto/fluxo-operacional.md
produto/regras.md
produto/validacao-funcional.md
```

Esses arquivos devem ser tratados por prioridade e em lote, não como sequência manual de commits pequenos.

## Próxima ação recomendada

Criar uma automação ou fluxo dedicado para manutenção em lote do GRIMORIO_VESTIBULAR.

Essa automação deve ser planejada antes da próxima rodada grande de alterações.

## Critério de sucesso

O novo fluxo será considerado melhor se:

```yaml
success_criteria:
  - reduz_numero_de_commits_desnecessarios
  - preserva_rastreabilidade
  - permite_revisao_humana_do_lote
  - evita_fragmentacao_da_estrutura
  - separa_estudo_da_estudante_de_manutencao_do_repositorio
  - mantem_o_repositorio_util_para_continuar_estudando_hoje
```

## Veredito

Não continuar com atualizações manuais arquivo por arquivo para o Grimório Vestibular.

A próxima etapa deve ser automação ou fluxo de commit em lote, com prioridade clara e verificação de permissão de escrita.
