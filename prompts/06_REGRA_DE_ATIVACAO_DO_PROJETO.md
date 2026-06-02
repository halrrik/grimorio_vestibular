# 06 - Regra de Ativacao do Projeto

Esta regra orienta novos chats dentro do Projeto Grimorio Vestibular.

## Ponto critico

Guardar esta regra no repositorio nao basta para ativar o comportamento em todos os chats.

Para funcionar em novos chats, a instrucao deve estar tambem nas instrucoes do Projeto Grimorio Vestibular ou ser chamada explicitamente pelo usuario com um gatilho.

## Objetivo

Permitir que a estudante escolha se aquele chat vai usar o fluxo do Grimorio ou seguir como conversa comum.

## Gatilhos aceitos

O Grimorio deve ser considerado ativado quando o usuario escrever qualquer uma das formas abaixo:

- grimorio
- grimorio ler primeiro
- usar grimorio
- consultar grimorio
- usar o repositorio grimorio vestibular
- consulta repositorio grimorio vestibular antes de responder
- /g
- @g
- @grimorio

## Pergunta inicial

Quando a estudante iniciar uma sessao de estudo em um novo chat e ainda nao tiver indicado o modo de uso, o assistente deve perguntar uma unica vez:

Vai usar o Grimorio neste chat?

## Se a resposta for sim

Ativar o fluxo Grimorio MVP1 e lembrar os comandos principais:

- grimorio ler primeiro
- grimorio salvar
- grimorio quiz
- grimorio corrigir
- grimorio commit

Depois disso, seguir o estudo normalmente, mantendo o padrao Grimorio.

## Se a resposta for nao

Continuar o chat normalmente, sem tentar salvar, estruturar ou commitar no Grimorio.

## Se o usuario ja usar comando Grimorio

Se a estudante usar qualquer gatilho listado acima, considerar o Grimorio ativado e nao fazer a pergunta inicial.

## Regra de seguranca

O assistente nao deve criar arquivo, alterar arquivo ou commitar sem aprovacao explicita.

## Observacao

Esta regra e um ponto de controle do MVP1. Ela pode ser ajustada apos testes reais com a Gabi.
