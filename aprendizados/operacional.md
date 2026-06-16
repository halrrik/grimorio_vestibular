---
id: grimorio_vestibular.aprendizados.operacional
type: operational_learning
status: consolidado_parcial
source: brainstorm_chat_voz
created_at: 2026-06-15
updated_at: 2026-06-15
repository: halrrik/grimorio_vestibular
backend_ready: true
human_review_required: false
canonical_layer: aprendizados
---

# Aprendizados operacionais

Este arquivo registra aprendizados operacionais do GRIMORIO_VESTIBULAR. O objetivo é descrever como o sistema deve funcionar na prática, quais caminhos devem existir, onde entram loops, decisões, validações e atualizações automáticas.

## 1. Princípio operacional central

O GRIMORIO_VESTIBULAR deve operar como um sistema de apoio contínuo ao aprendizado. Ele recebe objetivos, contexto e desempenho; transforma isso em plano, prática e acompanhamento; depois usa os resultados para ajustar o próprio funcionamento.

A operação não deve depender de uma pessoa lendo todos os arquivos intermediários. O fluxo ideal é automatizável e backend-ready.

```text
Objetivo -> Mapeamento -> Plano -> Estudo -> Prática -> Correção -> Extração -> Commit -> Auditoria -> Atualização -> Novo plano
```

## 2. Fluxo operacional macro

### Etapa 1 — Entrada de objetivos

A estudante informa o que precisa ou deseja alcançar.

Exemplos:

- vestibulares ou faculdades de interesse;
- prova escolar próxima;
- matéria em dificuldade;
- conteúdo que precisa revisar;
- prazo relevante;
- rotina disponível;
- preferência ou restrição momentânea.

Saída esperada:

```yaml
student_goal:
  target_type: vestibular | escola | revisao | reforco | prova_pontual | unknown
  targets: []
  deadline: unknown
  context: unknown
```

### Etapa 2 — Mapeamento de exigência

Quando o alvo for vestibular, o sistema deve buscar ou registrar quais conteúdos são cobrados pelas provas-alvo e quais estilos de questão aparecem com frequência.

Quando o alvo for escola/reforço, o sistema deve mapear o conteúdo informado, a matéria e o nível esperado.

Saída esperada:

```yaml
content_map:
  subjects: []
  topics: []
  source_type: edital | prova_anterior | plano_escolar | estudante | unknown
  priority: unknown
```

### Etapa 3 — Questões, exemplos e evidências

O sistema deve procurar ou gerar prática compatível com o objetivo. A prática pode vir de provas anteriores, questões similares, exercícios guiados ou baterias diagnósticas.

A prática precisa servir para medir aprendizado, não apenas ocupar tempo.

Saída esperada:

```yaml
practice_source:
  type: prova_anterior | questao_similar | exercicio_gerado | revisao_mista | diagnostico
  subject: unknown
  topic: unknown
  expected_skill: unknown
```

### Etapa 4 — Plano de estudo com participação da estudante

O plano deve ser montado com base nos objetivos, conteúdos, prazos e contexto da estudante. A estudante participa do ajuste porque pode informar o que já estudou, o que não quer repetir, onde está cansada, o que precisa priorizar e o que faz sentido naquele momento.

O plano deve ser flexível.

Saída esperada:

```yaml
study_plan:
  horizon: daily | weekly | monthly | ciclo | unknown
  items: []
  rationale: []
  flexibility: true
```

### Etapa 5 — Sessão de estudo

Uma sessão pode conter explicação curta, prática, correção, reforço e revisão mista. O fluxo que mostrou melhor resultado até agora foi:

```text
explicação curta -> bateria objetiva -> correção imediata -> reforço focado nos erros -> nova bateria -> revisão mista -> save
```

Esse fluxo não precisa ser obrigatório em todas as sessões, mas deve ser tratado como padrão operacional promissor.

### Etapa 6 — Correção e diagnóstico

Toda prática deve gerar diagnóstico. O diagnóstico precisa separar:

- acerto;
- erro;
- erro recorrente;
- lacuna conceitual;
- lacuna de memória;
- problema de interpretação;
- possível cansaço ou contexto;
- tema ainda não praticado;
- consolidação de curto prazo;
- retenção futura desconhecida.

### Etapa 7 — Registro estruturado

Ao final de uma sessão ou chat relevante, o sistema deve gerar arquivo estruturado em Markdown com dados legíveis por backend.

O arquivo deve conter:

- identificação;
- conteúdos estudados;
- atividades realizadas;
- desempenho;
- absorção estimada;
- lacunas;
- perfil de aprendizagem observado;
- pendências;
- atualizações candidatas;
- riscos de interpretação.

Esses registros podem ficar em:

```text
registros/chats/*.md
estudantes/gabi/sessoes/*.md
```

A diferença operacional precisa ser definida com mais precisão depois, mas a hipótese atual é:

```text
registros/chats = extrações estruturadas de conversas inteiras.
estudantes/gabi/sessoes = saves de sessões de estudo já consolidadas durante a operação.
```

### Etapa 8 — Commit no repositório correto

Todo arquivo do GRIMORIO_VESTIBULAR deve ser commitado no repositório:

```text
halrrik/grimorio_vestibular
```

Não deve ser commitado no repositório do Grimório Pai.

Mensagem de commit deve indicar tipo e conteúdo:

```text
registro: adiciona extracao de estudo AAAA-MM-DD slug
save: registra sessao de estudo AAAA-MM-DD slug
docs: atualiza aprendizados operacionais
```

### Etapa 9 — Auditoria automática

Depois do commit, o sistema deve auditar:

- arquivo no repositório correto;
- caminho correto;
- frontmatter presente;
- tipo de arquivo coerente;
- `backend_ready: true` quando aplicável;
- se existem campos `unknown` aceitáveis;
- se há conflito de nota ou correção;
- se há inferência tratada como fato;
- se há domínio definitivo inferido sem retenção futura;
- se o arquivo sugere atualizações candidatas.

### Etapa 10 — Promoção para arquivos vivos

Depois da auditoria, o sistema deve atualizar arquivos vivos. Essa etapa deve ser automatizável.

Arquivos vivos prováveis:

```text
estado/progresso.md
estado/plano-atual.md
estado/metodologia.md
estado/perfil-aprendizagem.md
estado/revisoes.md
estado/riscos.md
```

Esses caminhos ainda são candidatos. Antes de criar muitos arquivos canônicos, a estrutura deve ser validada para não gerar dispersão.

## 3. Loops operacionais

### Loop de aprendizagem

```text
estudar -> praticar -> corrigir -> reforçar erro -> revisar -> registrar -> ajustar plano
```

### Loop de planejamento

```text
objetivo -> plano -> execução -> evidência -> ajuste -> novo plano
```

### Loop de diagnóstico

```text
erro -> perguntar por quê -> identificar causa provável -> escolher intervenção -> testar de novo
```

### Loop de revisão espaçada

```text
erro ou consolidação curta -> revisão em 3 a 5 dias -> revisão em 10 a 14 dias -> reclassificação de retenção
```

### Loop de proteção

```text
gatilho ou risco -> reduzir pressão -> mudar abordagem -> explicar motivo -> preservar vínculo com o estudo
```

## 4. Pontos de decisão

### Quando um conteúdo deve ser marcado como estudado?

Deve ser marcado como estudado quando houver evidência de exposição ou prática registrada.

Mas o sistema precisa diferenciar:

```text
informado como já estudado != validado por desempenho
visto em aula != praticado
praticado uma vez != consolidado
acertado no mesmo dia != retido no futuro
```

### Quando marcar absorção alta?

Apenas quando houver evidência de desempenho consistente em mais de uma atividade ou após reforço. Mesmo assim, deve ser descrita como absorção de curto prazo se não houver revisão em outro dia.

### Quando criar revisão?

Criar revisão quando houver:

- erro recorrente;
- erro pontual em conceito importante;
- acerto após reforço, mas ainda sem retenção futura;
- tema novo com alto peso;
- conteúdo visto sem prática suficiente.

### Quando ajustar plano?

Ajustar plano quando:

- estudante questiona repetição sem sentido;
- conteúdo planejado já foi estudado;
- desempenho mostra lacuna maior que o esperado;
- prazo muda;
- prova alvo muda;
- tema emocionalmente sensível aparece;
- o plano fica amplo demais para execução real.

### Quando proteger a estudante?

Proteger quando houver sinais de sobrecarga, gatilho emocional, bloqueio, confusão persistente, frustração excessiva ou risco de insistir em uma abordagem que prejudica o aprendizado.

Proteção não significa abandonar o conteúdo. Pode significar mudar a rota.

## 5. Regras operacionais candidatas

Estas regras ainda não são a camada final de regras, mas devem orientar a operação:

```yaml
candidate_operational_rules:
  - nunca_confundir_registro_bruto_com_memoria_canonica
  - nunca_confundir_desempenho_imediato_com_retencao_futura
  - nunca_commitar_conteudo_do_grimorio_vestibular_no_grimorio_pai
  - sempre_separar_fato_de_inferencia
  - sempre_registrar_lacunas_e_pendencias
  - sempre_diferenciar_conteudo_informado_de_conteudo_validado
  - sempre_explicitamente_justificar_repeticao_de_materia_em_dias_consecutivos
  - sempre_priorizar_protecao_da_estudante_em_caso_de_gatilho_ou_sobrecarga
  - preferir_baterias_curtas_com_correcao_imediata_quando_o_objetivo_for_diagnostico
  - usar_revisao_mista_para_validar_consolidacao_de_curto_prazo
```

## 6. Operação por estudante

O sistema deve suportar múltiplos estudantes futuramente, mas agora o caso real é Gabi.

A estrutura deve permitir personalização por estudante:

```text
estudantes/gabi/
  sessoes/
  progresso/
  plano/
  perfil/
  revisoes/
  riscos/
```

Essa estrutura ainda precisa ser validada. O princípio importante é que regras gerais do produto não devem apagar a individualidade da estudante.

## 7. Gamificação operacional

A gamificação deve operar sobre dados reais, não sobre sensação genérica de progresso.

Possíveis unidades:

```yaml
gamification_units:
  subject_level: materia
  topic_level: topico
  skill_level: habilidade
  xp_sources:
    - questoes_respondidas
    - revisao_concluida
    - erro_corrigido
    - retencao_confirmada
    - simulado_finalizado
  status_examples:
    - not_started
    - introduced
    - practiced
    - reinforced
    - short_term_absorbed
    - review_scheduled
    - retention_confirmed
```

O sistema não deve premiar apenas volume. Deve valorizar correção de erro, revisão e retenção.

## 8. Auditoria de qualidade

A auditoria deve procurar principalmente estes problemas:

- score inconsistente;
- arquivo no repositório errado;
- status canônico indevido;
- `human_review_required` marcado como true sem necessidade operacional;
- ausência de evidência;
- inferência forte demais;
- conteúdo planejado tratado como estudado;
- conteúdo informado pela estudante tratado como validado;
- ausência de próximos passos;
- ausência de revisão para lacuna relevante;
- repetição de matéria sem justificativa.

## 9. Estado atual dos aprendizados operacionais

Com base nos registros recentes, o sistema já demonstrou valor em:

- gerar plano ajustável;
- responder a questionamento da estudante;
- aplicar baterias de questões;
- corrigir imediatamente;
- reforçar erros;
- gerar revisão mista;
- salvar sessões;
- commitar registros;
- auditar aprendizados.

Ainda falta transformar isso em fluxo automatizado completo.

## 10. Próximos arquivos recomendados

Próximos arquivos prováveis:

```text
produto/hipotese.md
produto/fluxo-operacional.md
produto/regras.md
estado/progresso.md
estado/plano-atual.md
estado/metodologia.md
estado/perfil-aprendizagem.md
estado/revisoes.md
estado/riscos.md
```

Antes de criar todos, é recomendável decidir a árvore canônica do repositório para evitar fragmentação prematura.
