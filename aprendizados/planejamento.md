---
id: grimorio_vestibular.aprendizados.planejamento
type: planning_learning
status: consolidado_parcial
source: brainstorm_chat_voz
created_at: 2026-06-15
updated_at: 2026-06-15
repository: halrrik/grimorio_vestibular
backend_ready: true
human_review_required: false
canonical_layer: aprendizados
---

# Aprendizados de planejamento

Este arquivo registra aprendizados de planejamento do GRIMORIO_VESTIBULAR. Ele não é um plano de estudo diário nem uma regra final; é uma camada de entendimento sobre como o produto deve ser pensado, desenhado e evoluído.

## 1. Camadas de compreensão de produto

Um produto, projeto ou aplicação deve ser compreendido por pelo menos três camadas complementares:

1. Hipótese
2. Fluxo operacional
3. Regras

A hipótese explica por que o produto existe e qual promessa ele deve cumprir. O fluxo operacional mostra como o produto funciona na prática, incluindo caminho ideal, condições, decisões, exceções e loops. As regras definem limites, critérios, validações e comportamentos obrigatórios.

Esse modelo deve ser considerado um padrão reutilizável para outros projetos, porque facilita entendimento, teste, evolução e auditoria. A hipótese evita que o produto vire apenas uma coleção de funcionalidades soltas. O fluxo evita que o sistema dependa de interpretação subjetiva. As regras evitam que o comportamento mude sem controle.

## 2. Hipótese original do GRIMORIO_VESTIBULAR

O GRIMORIO_VESTIBULAR nasceu como uma ferramenta para apoiar a Gabi na preparação para vestibulares. A ideia inicial era simples: a estudante informaria quais faculdades ou vestibulares pretendia fazer; o sistema pesquisaria quais conteúdos eram cobrados por essas provas; depois buscaria exemplos de questões, provas antigas e gabaritos; em seguida, montaria um plano de estudos com apoio, opinião e participação da estudante.

A hipótese inicial pode ser formulada assim:

```text
Ajudar a estudante a se preparar para vestibulares específicos, conectando os conteúdos cobrados pelas provas com um plano de estudos praticável, acompanhamento de progresso e adaptação contínua conforme desempenho e necessidade.
```

## 3. Evolução da hipótese

Durante o brainstorm, a hipótese se ampliou. O GRIMORIO_VESTIBULAR não deve ser apenas uma ferramenta para vestibular no sentido restrito. Ele pode continuar atendendo vestibulares, mas deve também funcionar como apoio mais amplo ao ensino médio, aos estudos cotidianos e à construção de aprendizagem real.

A evolução importante é esta: o sistema não deve ser apenas uma fábrica de conteúdo. Ele não existe para despejar matéria, gerar aulas indefinidamente ou empurrar exercícios sem contexto. Ele deve facilitar o aprendizado, entendendo o perfil da estudante, seu contexto, seus objetivos, suas lacunas, seu ritmo e sua resposta aos métodos usados.

A hipótese evoluída passa a ser:

```text
O GRIMORIO_VESTIBULAR existe para facilitar o aprendizado da estudante no ensino médio e na preparação para vestibulares, conectando objetivos de prova, conteúdos escolares, prática orientada, acompanhamento de desempenho, adaptação do plano e personalização do caminho de estudo.
```

## 4. Produto centrado na estudante

O centro do sistema não é o conteúdo isolado nem a lista de matérias. O centro é a estudante em relação aos objetivos que precisa cumprir.

Isso muda o planejamento. Em vez de perguntar apenas "qual conteúdo falta?", o sistema também deve perguntar:

- o que a estudante quer alcançar?
- que provas ou contextos importam agora?
- o que já foi estudado?
- o que foi apenas visto, mas ainda não absorvido?
- quais erros se repetem?
- que tipo de explicação funciona melhor?
- que tipo de exercício gera progresso?
- quando o plano precisa mudar?

O plano deixa de ser uma tabela fixa e passa a ser um organismo adaptável.

## 5. Estudar não é necessariamente aprender

Um aprendizado central do brainstorm é que o sistema precisa diferenciar estudo executado de aprendizagem absorvida.

A estudante não precisa saber explicar teoricamente essa diferença. Ela não precisa pensar em termos de metodologia, metacognição ou diagnóstico. Mas o sistema precisa operar com essa distinção internamente.

Portanto:

```text
Conteúdo visto não é igual a conteúdo aprendido.
Questão respondida não é igual a domínio definitivo.
Acerto no mesmo dia não é igual a retenção futura.
Plano seguido não é igual a progresso real.
```

O acompanhamento deve sempre tentar separar exposição, prática, acerto, correção, reforço, consolidação de curto prazo e retenção futura.

## 6. Planejamento flexível

O plano de estudos deve funcionar como norte, não como roteiro rígido. Ele precisa orientar a estudante, mas deve se adaptar quando aparecem mudanças de prioridade, lacunas, prazos, cansaço, gatilhos, repetição excessiva de matérias ou avanço inesperado.

Um plano bom não é aquele que nunca muda. Um plano bom é aquele que muda por bons motivos e deixa rastros claros do motivo da mudança.

Exemplos de motivos válidos para ajuste:

- prova alvo mudou;
- conteúdo escolar urgente apareceu;
- desempenho mostrou lacuna inesperada;
- estudante questionou repetição sem sentido;
- conteúdo estava planejado, mas já foi estudado;
- revisão precisa entrar antes de novo conteúdo;
- risco emocional ou cognitivo apareceu;
- prazo exige reordenação.

## 7. Gamificação como visibilidade de progresso

A gamificação não deve ser pensada como decoração, estética ou distração. Ela deve tornar o progresso visível, motivador e granular.

A ideia é quebrar o conhecimento em unidades menores, com evolução por níveis, experiência, domínio parcial, domínio temporário, revisão necessária e consolidação. Isso permite que a estudante veja avanço mesmo quando a matéria é grande ou abstrata.

O sistema pode futuramente usar conceitos como:

- nível por matéria;
- experiência por tópico;
- progresso por habilidade;
- conquistas por revisão concluída;
- alertas de lacuna;
- recuperação de pontos frágeis;
- ranking pessoal contra o próprio histórico, não contra outras pessoas.

O objetivo da gamificação é aumentar clareza, motivação e continuidade, não transformar estudo em jogo superficial.

## 8. Diagnóstico por PDCA e porquês

O GRIMORIO_VESTIBULAR deve aprender com o ciclo de execução. O PDCA se encaixa naturalmente:

- Plan: definir o plano de estudo.
- Do: estudar, praticar e responder.
- Check: corrigir, medir, comparar e identificar lacunas.
- Act: ajustar plano, metodologia, revisão ou abordagem.

Além disso, quando uma dificuldade aparece, o sistema não deve parar no sintoma. Deve buscar causa provável. A dificuldade não é apenas "errou física" ou "não entendeu cartografia". Pode haver causas como conceito base ausente, linguagem da questão, memória, ansiedade, cansaço, falta de prática, explicação inadequada ou tema emocionalmente sensível.

Os "porquês" ajudam a separar sintoma de causa.

## 9. Proteção emocional e limites humanos

Se o sistema detectar risco emocional, psicológico, cognitivo ou contextual, a prioridade deve ser proteger a estudante. Isso não significa abandonar o objetivo de estudo, mas ajustar o caminho.

Pode ser necessário evitar um tema temporariamente, mudar abordagem, reduzir carga, explicar o motivo ou trocar o tipo de exercício. O sistema deve ser capaz de dizer, em termos operacionais: "não vamos insistir nesse caminho agora porque há um motivo humano de cuidado".

Esse ponto deve futuramente virar regra específica, mas já fica registrado como aprendizado de planejamento.

## 10. Automação como destino natural

O MVP inicial pode depender de commits manuais ou assistidos, mas o desenho do produto não deve depender de leitura humana permanente dos arquivos intermediários.

O destino natural é backend automático:

- extrair informação do chat;
- salvar registro estruturado;
- validar schema;
- auditar consistência;
- promover aprendizados para arquivos vivos;
- atualizar progresso, plano, metodologia, perfil e riscos;
- gerar próximos passos.

Arquivos intermediários existem como rastros operacionais, não como documentos que alguém precisa ler manualmente para o sistema funcionar.

## 11. Aprendizado de naming e separação de repositórios

O GRIMORIO_VESTIBULAR é uma aplicação/produto próprio. Ele pode usar conceitos do Grimório Pai, mas não deve ser confundido com o repositório estrutural do Grimório Pai.

A separação precisa ser explícita:

```text
Grimório Pai = estrutura, metodologia base, contratos gerais.
GRIMORIO_VESTIBULAR = aplicação educacional concreta, focada em estudante, estudo e vestibular/ensino médio.
```

Essa separação evita commits errados, inferências erradas e confusão entre arquitetura geral e operação real do produto.

## 12. Pontos ainda não fechados

Ainda precisam ser detalhados em arquivos futuros:

- hipótese oficial v1;
- fluxo operacional completo;
- regras de atualização automática;
- regras de proteção emocional;
- modelo de gamificação;
- modelo de progresso por matéria/tópico/habilidade;
- schema definitivo dos registros de estudo;
- critérios para promover registro bruto para memória operacional;
- política de revisão espaçada;
- separação entre vestibular, escola e reforço geral.
