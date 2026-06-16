---
id: grimorio_vestibular.produto.regras
type: product_rules
status: v0
created_at: 2026-06-15
updated_at: 2026-06-15
backend_ready: true
human_review_required: false
---

# Regras do Produto

Este arquivo registra regras iniciais do GRIMORIO_VESTIBULAR. Elas organizam limites, critérios e comportamentos obrigatórios.

## Regras de separação

- O GRIMORIO_VESTIBULAR é aplicação/produto próprio.
- O Grimório Pai é estrutura/metodologia base.
- Conteúdo operacional da aplicação deve ser commitado em `halrrik/grimorio_vestibular`.
- Não commitar registros de estudo no repositório do Grimório Pai.

## Regras de verdade

- Conteúdo visto não é domínio.
- Conteúdo informado como já estudado não é validação de desempenho.
- Acerto no mesmo chat é consolidação de curto prazo, não retenção definitiva.
- Plano criado não é plano executado.
- Questões geradas no chat não equivalem automaticamente a simulado oficial.

## Regras de registro

Todo registro estruturado deve separar:

- fatos observados;
- inferências prováveis;
- pontos incertos;
- evidências;
- lacunas;
- pendências;
- atualizações candidatas.

## Regras de atualização

Atualizar progresso apenas quando houver evidência mínima.

Usar status diferentes para:

```yaml
learning_status:
  - planned
  - introduced
  - practiced
  - reinforced
  - short_term_absorbed
  - review_scheduled
  - retention_unknown
  - retention_confirmed
```

## Regras de plano

- O plano deve ser flexível.
- Repetir matéria em dias consecutivos exige justificativa pedagógica.
- Se a estudante questiona a repetição, o plano deve ser reavaliado.
- Conteúdo já estudado pode sair do plano imediato, mas não deve ser marcado como dominado sem evidência.
- Revisão pode ter prioridade sobre avanço.

## Regras de metodologia

- Preferir explicação curta antes da prática quando o conteúdo for novo.
- Preferir baterias objetivas curtas para diagnóstico.
- Corrigir imediatamente.
- Reforçar erros antes de avançar demais.
- Usar revisão mista para validar consolidação de curto prazo.
- Registrar lacunas residuais após cada sessão relevante.

## Regras de proteção

- Se houver sinal de sobrecarga, gatilho emocional ou bloqueio, preservar a estudante vem antes de cumprir o plano.
- Proteção não significa abandonar o conteúdo; pode significar mudar rota, reduzir carga ou trocar abordagem.
- Não inferir estado emocional sem evidência.

## Regras de auditoria

A auditoria deve sinalizar:

- arquivo no repositório errado;
- ausência de frontmatter;
- ausência de evidência;
- inferência tratada como fato;
- score inconsistente;
- conteúdo planejado tratado como estudado;
- conteúdo informado tratado como validado;
- ausência de revisão para lacuna importante;
- domínio definitivo sem retenção futura.

## Regras de automação

- Arquivos intermediários não devem depender de leitura humana manual.
- O backend deve conseguir validar, auditar e promover registros.
- `human_review_required: false` significa que o sistema pode processar automaticamente, não que o conteúdo é canônico sem validação.
