# Patch Log - Grimorio Vestibular

Registro de mudancas, decisoes e ajustes do Grimorio Vestibular.

## 0.1.3 - Regra de ativacao do projeto

Adicionado:
- Arquivo prompts/06_REGRA_DE_ATIVACAO_DO_PROJETO.md.
- Pergunta inicial para novos chats de estudo.
- Lista curta de comandos principais para ativacao do fluxo MVP1.

Decidido:
- A pergunta deve ser feita uma unica vez por chat quando a estudante iniciar estudo e ainda nao tiver indicado o modo de uso.
- Se o usuario usar qualquer comando iniciado por grimorio, o fluxo deve ser considerado ativado.
- O assistente nao deve alterar arquivos ou commitar sem aprovacao explicita.

Pendente:
- Testar a regra em um novo chat do projeto.
- Ajustar a frase inicial se ficar repetitiva ou confusa.

## 0.1.2 - Registro de estudo de matematica

Adicionado:
- Captura de aprendizado de matematica sobre porcentagem, proporcionalidade e interpretacao.
- Plano inicial de acompanhamento de matematica base para ENEM, Fuvest e Vunesp.
- Indice de estudos com absorcao estimada e absorcao medida pendente.
- Duvidas ativas observadas no estudo.

Decidido:
- O registro deve guardar o aprendido e os padroes observados, nao o texto bruto do chat.
- Absorcao sem quiz e gabarito claro deve ser marcada como estimada.
- Absorcao medida fica pendente ate aplicacao de quiz diagnostico.
- Planos de estudo podem ser armazenados no repositorio e atualizados conforme evolucao real da estudante.

Pendente:
- Aplicar quiz diagnostico de matematica.
- Atualizar absorcao medida.
- Ajustar plano conforme resultado do quiz.

## 0.1.1 - Roteiro operacional e pendencias de scripts

Adicionado:
- prompts/05_ROTEIRO_OPERACIONAL_MVP1.md com o fluxo operacional minimo do MVP1.
- Pendencia em futuro/00_FISHBOWL.md para melhorar e revisar scripts de fala do Grimorio.
- Pendencia para criar script recomendado de uso cobrindo inicio, perguntas, salvamento, quiz, correcao, absorcao e commit.

Decidido:
- Scripts completos de fala nao entram como regra rigida agora.
- O MVP1 deve validar primeiro o fluxo.
- A melhoria da linguagem e dos scripts fica registrada como pendencia.

Pendente:
- Testar o roteiro com a Gabi.
- Revisar se as frases de controle sao suficientes.
- Criar script recomendado completo depois do alpha.

## 0.1.0 - MVP1 inicial

Adicionado:
- Estrutura base do Grimorio Vestibular.
- Fluxo MVP1 em Markdown.
- Captura Grimorio.
- Quiz diagnostico.
- Absorcao estimada e medida de 0 a 100.
- Pasta futuro para ideias fora do MVP atual.

Decidido:
- Toda evolucao comeca por uma hipotese.
- O Grimorio deve permanecer preso a hipotese validada.
- Banco de dados e agente executor ficam para MVP2 e MVP3.
